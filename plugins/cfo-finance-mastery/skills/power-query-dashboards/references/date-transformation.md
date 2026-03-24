---
name: Date Transformation & Month-End Standardization
description: Convert text dates to actual dates, standardize to month-end, and handle misaligned reporting periods.
---

# Date Transformation & Month-End Standardization

## The Date Problem

**Many GL systems export dates in problematic formats:**

```
Bad Format 1: Text, not date
  "Jan 2024", "Feb 2024", "Mar 2024" (column headers, not values)

Bad Format 2: Wrong date type
  01/01/2024 (year-start, not month-end)

Bad Format 3: Inconsistent periods
  1/31/2024, 2/15/2024, 3/31/2024 (some mid-month, some month-end)

Bad Format 4: Missing year
  "01-Jan", "01-Feb" (which year?)
```

**Dashboards need:**
- Actual date values (not text)
- Consistent month-end standardization
- Clear year information

## Date Parsing in Power Query

### Scenario 1: Text Dates ("Jan 2024", "Feb 2024")

**Problem:** Dates are column headers (wide format), not values.

**Solution: During unpivoting in Power Query**

**Step 1: After unpivoting, "Date" column shows text like "Jan 2024"**

**Step 2: In Power Query, right-click Date column**

**Step 3: Select "Change Type" → Date**

**Step 4: If Excel can't parse automatically, use custom formula**
- Add Column → Custom Column
- Name: "DateConverted"
- Formula: `=Date.FromText([Date], "MMM yyyy")`
  - MMM = 3-letter month (Jan, Feb, Mar)
  - yyyy = 4-digit year

**Step 5: Delete original Date column, rename DateConverted to Date**

**Result:**
```
Before:  "Jan 2024" (text)
After:   1/1/2024 (actual date)
```

### Scenario 2: Full Dates (01/01/2024 Type)

**Problem:** Dates exist but are wrong type (text, not date).

**Solution in Power Query:**

```
Right-click Date column → Change Type → Date

If format is MM/DD/YYYY:
  Power Query auto-detects → done

If format is DD/MM/YYYY (European):
  Right-click → Change Type → Using Locale...
  Select "English (United Kingdom)"
  Format updates to DD/MM/YYYY
```

**Result:** Text becomes actual date type.

## Month-End Standardization

**Why?** Accounting periods are always month-end (1/31, 2/28/29, 3/31, etc.), not random dates.

### Converting Any Date to Month-End

**In Power Query Custom Column:**

```
Custom Column Name: DateMonthEnd
Formula: =Date.EndOfMonth([Date])
```

**Examples:**
```
Input: 1/15/2024  (mid-month) → Output: 1/31/2024
Input: 1/31/2024  (month-end)  → Output: 1/31/2024 (unchanged)
Input: 2/01/2024  (month-start) → Output: 2/29/2024 (leap year handled)
```

### Alternative: Manual Month-End Mapping

**If Power Query Date functions unavailable:**

**In Excel, before Power Query:**

```
Column A: Original Date (text or misaligned)
Column B: Month-End Date (formula)

Formula: =DATE(YEAR([Date]), MONTH([Date])+1, 0)
Explanation: Year & Month, then "day 0 of next month" = last day of current month
```

**Then in Power Query, unpivot the standardized column.**

## Handling Multi-Year Data

**Problem:** Data spans 2022-2024; dates could be ambiguous ("01-Jan" without year).

**Solution in Power Query:**

```
Custom Column Name: DateWithYear
Formula:
= try Date.FromText([Month] & " " & [Year])
  otherwise null
```

**Example input:**
```
Month   Year    Result
Jan     2024    1/1/2024
Feb     2024    2/1/2024
Jan     2023    1/1/2023
```

**Then apply month-end standardization on top.**

## Handling Different Reporting Calendars

**Problem 1: Company uses 4-4-5 calendar (some months 4 weeks, some 5)**

**Solution:**
```
In Drivers tab or Power Query, create Calendar table:
Period  StartDate   EndDate
2024-1  1/1/2024    1/31/2024 (or 1/29/2024 if 4-week period)
2024-2  2/1/2024    2/28/2024

Then in Power Query:
Custom Column: PeriodKey = VLOOKUP([TransactionDate], Calendar, 1)
Result: Dates grouped into company's defined periods
```

**Problem 2: Company closes books on different day (15th, not 31st)**

**Solution:**
```
Custom Column: PeriodEnd
Formula: =DATE(YEAR([Date]), MONTH([Date])+1, 14)
(Results in 15th of next month = 14th of current, approximately)

Or more precisely: = DATE(YEAR([Date]), MONTH([Date]), 15)
```

## Real Example: Multi-Source Date Cleanup

**Scenario:** Importing from three GL systems with different date formats.

```
System 1 (QuickBooks):
  Format: MM/DD/YYYY (1/31/2024) ✓ Good
  Action: Change Type → Date

System 2 (NetSuite):
  Format: Text "Jan-24" (need year)
  Custom Column: Date.FromText([Month] & " " & [Year], "MMM yy")

System 3 (Xero):
  Format: 1/15/2024 (mid-month, not month-end)
  Custom Column: Date.EndOfMonth([Date])

Result table (all standardized):
Account    Date        Amount
Revenue    1/31/2024   100,000  ✓ Month-end
Revenue    2/29/2024   105,000  ✓ Month-end (leap year)
COGS       1/31/2024    40,000  ✓ Month-end
```

## Dashboard Impact: Why Date Matters

**If dates aren't month-end or standardized, dashboard filters break:**

**Example: User enters date range 1/1/2024 to 3/31/2024**

```
Bad (non-standardized dates):
  Include 1/15/2024 revenue? (yes, within range)
  Include 1/31/2024 revenue? (yes, within range)
  Include 2/15/2024 revenue? (yes, within range)
  Result: Revenue counted twice for some months ✗

Good (month-end dates):
  Include 1/31/2024 revenue? (yes, within range)
  Include 2/29/2024 revenue? (yes, within range)
  Include 3/31/2024 revenue? (yes, within range)
  Result: Exactly one row per month ✓
```

## Testing Date Transformation

**Before using in dashboard, validate:**

**Test 1: Check for text dates**
```
Right-click "Date" column → Data Type
Should show: "Date" (not "Text")

If shows "Text": Transformation failed. Redo Step 1.
```

**Test 2: Verify month-end standardization**
```
Look at all visible dates:
1/31/2024, 2/29/2024, 3/31/2024 ✓ (all month-end)

Or look for any non-31/30/29 dates:
1/15/2024 ✗ (mid-month, not standardized)
```

**Test 3: Year boundary check**
```
In January data, confirm year = 2024 (not 2025 or 2023)
In December data, confirm year = 2024 (not 2023)

Multi-year confusion is common.
```

**Test 4: Duplicate date elimination**
```
Count distinct dates:
If 36 months of data, should have exactly 36 distinct dates
If >36, you have duplicates or non-month-end dates
```

## Common Date Errors & Fixes

**Error 1: Excel shows date as number (43831)**
- Cause: Format is numeric, not date-formatted
- Fix: Right-click → Format Cells → Date → OK
- Result: Shows 1/31/2024 (not 43831)

**Error 2: Date column shows "1/31/2024 12:00 AM" (with time)**
- Cause: System exported datetime, not just date
- Fix: In Power Query, use `Date.ToText([DateTime],"MM/DD/YYYY")`
- Result: 1/31/2024 (no time)

**Error 3: Leap year causes formula errors (2/29 in non-leap year)**
- Cause: Hardcoded formula like `=DATE(2023,2,29)` (2023 not leap year)
- Fix: Use `Date.EndOfMonth([Date])` which handles leap years
- Result: 2/28/2023 automatically (not error)

**Error 4: Dashboard shows wrong month data**
- Cause: Dates are week-ending (Fridays) not month-end
- Fix: Run month-end standardization `=Date.EndOfMonth([Date])`
- Result: All dates become last day of month

## Date Transformation Checklist

Before considering dates ready for dashboard:

- [ ] All dates are actual date type (not text)
- [ ] All dates are month-end (1/31, 2/28/29, 3/31, etc.)
- [ ] Year is correct (2024, not 2025 or 2023)
- [ ] No duplicate dates for same account
- [ ] Date range is continuous (no missing months)
- [ ] Earliest date matches GL period start
- [ ] Latest date matches most recent GL close
- [ ] Multi-year data clearly separated by year

