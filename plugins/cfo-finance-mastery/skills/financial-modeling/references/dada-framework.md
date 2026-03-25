---
name: "DADA Framework & Model Design"
description: "Four qualities of effective models, tab architecture with source/input/output structure, schema flow, template tab design, color coding system, instructions tab components, named range conventions."
when_to_read: "When the user needs model design guidance, template tab setup, instructions tab content, color coding implementation, or named range architecture."
---

# DADA Framework & Model Design

## The Four Qualities

### D -- Dynamic and Flexible
**What this means in practice:**
- Source tabs accept fresh accounting exports without restructuring
- Change one input -> all outputs recalculate
- Named ranges allow flexible references (not hard-coded cell addresses)
- Key named ranges:
  - `Company_Name` -- linked to a single cell, referenced everywhere
  - `Latest_Month_of_Actuals` -- boundary between historical and projected data
  - `error_check` -- referenced on every tab header

### A -- Accurate
**Implementation:**
- Error check tab monitors all key equations
- Balance sheet equality verified every period
- Revenue matches across drivers, P&L, and summary
- Cash aligns across BS and CF statement
- "Go To Special" > Constants to find hard-coded values that should be formulas

### D -- Digestible
**Implementation:**
- Tab order follows logical flow (Instructions -> Summary -> Drivers -> Statements -> Error Checks)
- Consistent section headers with buffer rows between sections
- Group detail rows under summary headers
- Use outlines (Alt+A+G) to allow expand/collapse

### A -- Attractive
**Implementation:**
- Consistent font throughout (one font family)
- Consistent number formatting (accounting format recommended)
- Date formatting: MMM-YY (Jan-25, Feb-25)
- Strategic white space between sections
- Dashboard-quality summary tab

---

## Template Tab Design (Aharonoff)

A hidden tab that serves as a blueprint. Duplicate it for every new section to maintain consistency.

### Core Components
1. **Company name** -- linked to `Company_Name` named range (update once, changes everywhere)
2. **Dynamic tab name** -- formula that auto-updates when tab is renamed
3. **Date structure:**
   - Start dates (1st of each month)
   - End dates (EOMONTH)
   - Year identifiers
   - Quarter identifiers
   - Monthly, quarterly, and annual display periods
4. **Consistent header row** with secondary info row below
5. **Pre-built aggregation formulas** for quarterly and annual rollups
6. **Actuals vs Projection boundary** -- conditional formatting based on `Latest_Month_of_Actuals`

### Smart Formula Patterns

**For income statement items (flows -- sum over period):**
```
=SUMIFS([data_range], [begin_date_row], ">=" & [period_start], [end_date_column], "<=" & [period_end])
```

**For balance sheet items (positions -- point-in-time):**
```
=INDEX([values], 0, MATCH([period_end_date], [date_range], 0))
```

This is the fundamental difference: P&L uses SUMIFS (accumulates), BS uses INDEX (grabs snapshot).

---

## Instructions Tab Design (Aharonoff)

Transforms the model from a complex spreadsheet into a user-friendly tool.

### Required Components
1. **Color coding documentation** -- what each color means with examples
2. **Tab descriptions** -- concise purpose of each tab and its relationship to others
3. **Interactive navigation** -- hyperlinks (Ctrl+K) from tab names to cell A1 of each tab
4. **Visual flow diagram** -- using Excel shapes, show data flow between tabs with arrows
5. **Error check integration** -- show how error checking spans the entire model

### Tab Description Examples
- **Summary Financials:** "Summarizes the three financial statements based on summary groupings"
- **Drivers:** "Consolidates inputs for income statement and balance sheet -- the only tab where historical and projection formulas differ"
- **Error Checks:** "Monitors all key equations across the model. Green = no errors. Red = investigation needed."

---

## Color Coding Implementation

### Step-by-Step Process
1. Select entire used range on a tab
2. Go To Special > Constants > Uncheck Text (finds all hard-coded numbers)
3. Color all identified cells blue (these are inputs)
4. Leave all formula cells black (these are calculations)
5. Manually identify cross-tab references and color purple
6. Add red background to error check rows and balance check rows

### Convention Enforcement
- Run "Go To Special" > Constants periodically to catch newly introduced hard-coded values
- Any hard-coded number that is not blue is either a mistake or needs documentation
- Use `Ctrl + /` to find formula inconsistencies within ranges

### Dashboard Exception
When creating board-ready output:
- All cells use black text regardless of type
- No color coding on presentation tabs
- Copy summary as picture (Alt+H+V+U) for slides

---

## Named Range Architecture

### Essential Named Ranges
| Name | Points To | Purpose |
|------|----------|---------|
| `Company_Name` | Single cell with company name | Referenced in headers across all tabs |
| `Latest_Month_of_Actuals` | Date cell for last month with actual data | Controls actuals/projection boundary |
| `error_check` | Comprehensive error formula result | Displayed on every tab header |

### Creating Named Ranges
- **Name Manager:** Ctrl+F3
- **Quick create:** Select cell, type name in Name Box (left of formula bar)
- **Bulk create:** Use "Create from Selection" for adjacent labels

### Using `Latest_Month_of_Actuals`
This named range is the cornerstone of actualization:
- Point it to the date of the most recent month with real data
- Formulas throughout the model reference it to determine whether to pull actual data or use projection formulas
- Update monthly during roll-forward (change one cell, entire model adjusts)

---

## Cross-References

- **Building the drivers tab** -> `drivers-tab.md` (this skill)
- **Three-statement construction** -> `three-statement-construction.md` (this skill)
- **Actualization and roll-forward** -> `actualization-and-rollforward.md` (this skill)
- **Excel techniques for model building** -> `excel-for-finance`
