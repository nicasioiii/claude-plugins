---
name: Seasonal Adjustment & Multi-Year Pattern Analysis
description: Identify seasonality in historical data, build seasonal multipliers, and apply them to forecasts for accuracy.
---

# Seasonal Adjustment & Pattern Analysis

## Identifying Seasonality

**Seasonality:** Predictable, repeating patterns within a year.

Examples:
- Retail: Nov-Dec spike (holiday shopping)
- School supplies: August/September peak
- HVAC: Summer AC demand, winter heating demand
- Landscaping: Spring/summer peak, winter trough

**How to identify:**
1. Gather 36 months of monthly revenue (3 years minimum)
2. Plot on a chart (month on X-axis, revenue on Y-axis)
3. Look for repeating pattern across all 3 years

## Calculating Seasonal Indices

**Formula:**
```
Seasonal Index = Actual Revenue for Month / Average Monthly Revenue
```

**Example (retail company, $120K annual revenue):**
```
Monthly Average = $120,000 / 12 = $10,000/month

                Revenue     Index (Actual/$10K)
January         $8,000      0.80  (80% of average; post-holiday slump)
February        $8,500      0.85
March           $9,000      0.90
April           $10,000     1.00  (baseline month)
May             $11,000     1.10
June            $12,000     1.20
July            $14,000     1.40  (summer peak)
August          $15,000     1.50  (summer peak)
September       $12,000     1.20  (back-to-school)
October         $11,000     1.10
November        $18,000     1.80  (holiday buildup)
December        $20,000     2.00  (holiday peak)
```

**Seasonality pattern: Summer peaks (July-Aug 1.4-1.5x), Winter holidays spike (Nov-Dec 1.8-2.0x), January low (0.8x)**

## Multi-Year Verification

**Check if pattern repeats across 3 years:**

```
              Year 1    Year 2    Year 3    Average Index
January       0.80      0.78      0.82      0.80
February      0.85      0.84      0.86      0.85
March         0.90      0.91      0.89      0.90
...
July          1.40      1.38      1.42      1.40 (consistent)
August        1.50      1.52      1.48      1.50 (consistent)
...
December      2.00      2.05      1.95      2.00 (consistent)
```

**If indices are consistent across years (within 5%), seasonality is reliable.**
**If indices vary wildly (0.80 → 1.20 → 0.60), seasonality is weak or pattern is changing.**

## Applying Seasonal Adjustments to Forecast

**Approach 1: Seasonal multiplier directly**

```
Forecast = Base Forecast * Seasonal Index

Example:
Base forecast (assuming flat $10K/month):
- July: $10,000 * 1.40 = $14,000
- December: $10,000 * 2.00 = $20,000
```

**Approach 2: Growth rate + seasonal multiplier (more sophisticated)**

```
Forecast = (Prior Year Same Month * Growth Rate) * Seasonal Index

Example (5% annual growth):
- July 2024 forecast: ($14,000 from July 2023) * 1.05 (growth) * 1.40 (seasonality) = $20,580
- December 2024: ($20,000 from Dec 2023) * 1.05 * 2.00 = $42,000
```

## Seasonal Adjustment in Model

**In Drivers tab, create seasonal index row:**

```
                        Jan     Feb     Mar     Apr     May     Jun
Seasonal Index          0.80    0.85    0.90    1.00    1.10    1.20

                        Jul     Aug     Sep     Oct     Nov     Dec
Seasonal Index          1.40    1.50    1.20    1.10    1.80    2.00
```

**Use in forecast formula:**

```
Apr 2024 Revenue Forecast = Mar 2024 Actual Revenue * (1 + Growth%) * Apr Seasonal Index
                          = $110,000 * 1.05 * 1.00
                          = $115,500
```

**May 2024:**
```
= Mar 2024 Revenue * (1 + Growth%) * May Seasonal Index
= $110,000 * 1.05 * 1.10
= $127,050
```

**July 2024 (summer peak):**
```
= Mar 2024 Revenue * (1 + Growth%) * July Seasonal Index
= $110,000 * 1.05 * 1.40
= $161,700
```

## Seasonal Adjustment for COGS & Expenses

**COGS typically follows revenue seasonality:**

```
Forecast COGS = Forecast Revenue * COGS % * Seasonal Index

Example:
July forecast revenue: $161,700 (seasonal, summer peak)
COGS %: 40%
Seasonal impact: COGS is proportional to revenue
Forecast COGS: $161,700 * 40% = $64,680
```

**Some expenses are seasonal-independent:**

```
Payroll: Usually fixed (same monthly payroll regardless of season)
Rent: Fixed (same monthly rent)
Software: Fixed (same subscription)

BUT:
Advertising: May spike in Nov-Dec (holiday season campaigns)
  - Base ad spend: $8,000/month
  - Nov-Dec multiplier: 1.5x (increased holiday marketing)
  - Nov ad spend: $8,000 * 1.5 = $12,000

Fulfillment: Scales with revenue (more units shipped, more fulfillment cost)
  - Variable fulfillment: $2/unit
  - July forecast units: 1,500 (peak season)
  - July fulfillment: 1,500 * $2 = $3,000
```

## Seasonal Cash Flow Planning

**Seasonal business faces cash swings. Plan proactively:**

```
Low Season (January):
- Revenue: $8,000
- Operating Expenses: $35,000 (fixed)
- AR Collection: $10,000 (from Dec sales)
- Net Cash Need: ($8K + $35K - $10K) = ($33K) ← Cash outflow

Peak Season (July-August):
- Revenue: $15,000
- Operating Expenses: $35,000 (fixed)
- AP Payments: $15,000 (inventory purchased)
- AR Collection: $25,000 (from prior month peak sales)
- Net Cash: ($15K + $25K - $35K - $15K) = ($10K) ← Still negative if capital needed

Year-end (November-December):
- Revenue: $38,000 (peak)
- Operating Expenses: $35,000
- AR Collection: $30,000
- AP Payments: $20,000
- Net Cash: ($38K + $30K - $35K - $20K) = $13,000 ← Positive

Result: Seasonal business needs line of credit or capital reserve to bridge low seasons.
```

## Building Cash Reserve for Seasonal Low

**Rule:** Build cash reserve during peak season to cover low season.

```
Peak season cash accumulation (July-December): $150,000
Low season cash burn (January-June): ($80,000)
Remaining buffer: $70,000 (covers emergencies and growth)

Without this reserve, January forces a loan or credit card debt (expensive).
```

## Practical Example: Seasonal Forecast

```
                Jan     Feb     Mar     Apr     May     Jun     Jul     Aug
2023 Actual     8.0K    8.5K    9.0K    10.0K   11.0K   12.0K   14.0K   15.0K
Index           0.80    0.85    0.90    1.00    1.10    1.20    1.40    1.50

2024 Forecast:
Base (prior + 5%): 8.4K 8.9K 9.5K 10.5K 11.6K 12.6K 14.7K 15.8K
With Seasonality:
Index applied:    0.80  0.85  0.90  1.00  1.10  1.20  1.40  1.50
2024 Forecast:    8.4K  8.9K  9.5K 10.5K 12.8K 15.1K 20.6K 23.7K
                 (0.80× (0.85× (0.90× (1.00× (1.10× (1.20× (1.40× (1.50×
                  base) base) base) base) base) base) base) base)
```

**Result:** Forecast accounts for both historical growth (5% increase) AND seasonal patterns (summer peak, winter trough).

## Testing Seasonal Adjustments

**Before using in model, validate:**

1. **Check if indices sum to 12** (across all 12 months, should equal approximately 12)
   ```
   Example: 0.80+0.85+0.90+1.00+1.10+1.20+1.40+1.50+1.20+1.10+1.80+2.00 = 15.85
   This is > 12, so indices are higher than average (suggesting growth during period)
   ```

2. **Verify against 3-year history**
   - Plot 36 months
   - Check if forecast peaks match historical peaks
   - Check if forecast troughs match historical troughs

3. **Sense-check extreme months**
   - December forecast: $42,000 (with 2.0x multiplier)
   - Does this match historical December? (Should be close if seasonal pattern is reliable)

4. **Communicate seasonality to stakeholders**
   - Show that January cash low is expected, not a failure
   - Build forecast with seasonal perspective, not as flat month-over-month

## Industry-Specific Seasonal Patterns

### E-Commerce & Retail Seasonality

**Peak Seasons:**
- November-December: Holiday shopping (1.8-2.2x baseline)
- Black Friday/Cyber Monday: Single-day spikes (3-5x daily average)
- Summer clearance: End of August surge (1.4-1.6x)

**Valley Seasons:**
- January-February: Post-holiday slump (0.6-0.8x)
- May-June: Back-to-school planning dip (0.85-0.95x)

**Practical Example: Fashion Apparel**
```
Monthly Index by Season:
Winter Collection (Oct-Feb peak):
  October:    0.95  (early planning)
  November:   1.90  (Black Friday build-up)
  December:   2.10  (holiday peak)
  January:    0.60  (clearance phase)
  February:   0.65  (return-heavy month)

Summer Collection (May-Aug peak):
  May:        0.85  (transition)
  June:       1.15  (summer starts)
  July:       1.40  (summer peak)
  August:     1.35  (back-to-school)
  September:  0.90  (transition to fall)

Off-peak (March, April, Sept):
  March:      0.75
  April:      0.80
  September:  0.85
```

### Service Business Seasonality (HVAC, Landscaping, Construction)

**HVAC Example:**
```
Summer cooling demand (May-August): 1.6-1.8x
Winter heating demand (Nov-Feb): 1.5-1.7x
Shoulder months (Mar, Apr, Sep, Oct): 0.9-1.0x
Slowest (May overlap, June light): 0.7-0.8x
```

**Landscaping Example:**
```
Spring peak (March-May): 1.7-2.0x (lawn care, planting)
Summer (June-July): 1.4-1.6x (maintenance)
Fall (Sept-Oct): 1.3-1.5x (cleanup, prep)
Winter (Nov-Feb): 0.1-0.3x (minimal activity, snow services)
```

**Construction Trades Example:**
```
Mild weather (March-Oct): 1.2-1.4x (construction season)
Cold weather (Nov-Feb): 0.5-0.7x (weather delays, holidays)
Late spring surge (April-May): 1.6-1.8x (homeowner projects begin)
```

### Subscription/SaaS Seasonality

**Subscription businesses often show flatter patterns but have cyclical elements:**
```
Annual prepay peaks (Jan, Sept): 1.15-1.25x (fiscal year resets)
Mid-year (April-June): 0.95-1.05x (flat, stable retention)
Budget-cut months (August, November): 0.90-0.98x (CFO scrutiny, budget reviews)
```

## Multiplier Calculation Examples: Different Industries

### Multiplier Approach 1: Simple Monthly Index (Retail)

```
Dataset: 3 years of monthly revenue
Total 36-month revenue: $1,200,000
Average monthly: $33,333

Jan: $26,667 / $33,333 = 0.80
Dec: $66,667 / $33,333 = 2.00

→ Use 0.80 for all future January forecasts
→ Use 2.00 for all future December forecasts
```

### Multiplier Approach 2: Quarterly Blended (Service Business)

For businesses with less volatile patterns, blend two years:
```
Q1 2023: $45K (Q1 avg daily: $490)
Q1 2024: $48K (Q1 avg daily: $522)
Blended Q1 multiplier: ($45K + $48K) / 2 = $46.5K

Average daily (annual): $150K / 365 = $410/day
Q1 adjustment factor: $46.5K / ($410/day × 90 days) = 1.25x

→ Q1 forecasts = base × 1.25
```

### Multiplier Approach 3: Daily Granularity (High-Volatility Business)

For businesses with high daily variation:
```
Weekdays vs. Weekends (retail):
  Monday: 1.1x (start-of-week shopping)
  Tuesday-Thursday: 1.0x (baseline)
  Friday: 1.3x (weekend prep)
  Saturday: 1.6x (peak shopping)
  Sunday: 1.2x (final day)

Formula for any future week:
  Monday forecast = Base Daily × 1.1
  Saturday forecast = Base Daily × 1.6
```

## Seasonal Adjustment Implementation in Drivers Tab

**Place seasonal indices in a dedicated row within Drivers tab:**

```
                    Jan     Feb     Mar     Apr     May     Jun
Seasonal Index      0.80    0.85    0.90    1.00    1.10    1.20
Base Revenue Forecast: 100
                    Jul     Aug     Sep     Oct     Nov     Dec
Seasonal Index      1.40    1.50    1.20    1.10    1.80    2.00

Monthly Revenue Forecast = Base Revenue × Seasonal Index
  Jan: 100 × 0.80 = 80
  Jul: 100 × 1.40 = 140
  Dec: 100 × 2.00 = 200
```

**Add documentation row (using Excel notes) explaining seasonal factors:**
```
Notes for Seasonal Index row:
"Nov-Dec spike due to holiday shopping behavior;
Jan-Feb dips due to post-holiday inventory clearance.
Indices validated against prior 3 years. Clothing apparel niche."
```

## Handling Seasonal Adjustments for Variable Expenses

**Revenue-based expenses scale with seasonality:**
```
COGS (35% of revenue):
  Jan COGS: 80 × 35% = 28 (follows seasonal dip)
  Jul COGS: 140 × 35% = 49 (follows seasonal peak)

Fulfillment costs ($5 per unit):
  Units sold Jan: 80 units (from base + seasonality)
  Jan fulfillment: 80 × $5 = 400
```

**Fixed expenses do NOT scale with seasonality:**
```
Rent: $10,000/month (same all year, no seasonal adjustment)
Payroll: $50,000/month (same all year, no seasonal adjustment)

BUT marketing spend may be seasonal:
  Base ad spend: $8,000/month
  Nov-Dec multiplier: 1.5x (holiday campaign boost)
  Nov ad spend: $8,000 × 1.5 = $12,000
  Dec ad spend: $8,000 × 1.5 = $12,000
```

## Monthly Adjustment Methodology: Step-by-Step

**When new actuals arrive (month-by-month updates):**

1. **Import actuals into Source tab** (GL export)
2. **Update Drivers tab with new month's data** (SUMIFS pulls actuals automatically)
3. **Review seasonal pattern** for the new month
4. **Validate index consistency:**
   ```
   Is March 2024 actual / Annual Avg ≈ March 2023 index?
   If yes: Seasonality pattern is stable; use existing indices
   If no: Pattern may be shifting; investigate reason
   ```
5. **Adjust indices if pattern has shifted:**
   ```
   Old March index: 0.90
   Actual Mar 2024: $35K (vs. annual avg $37K) = 0.95

   If shift is permanent: Update index to 0.95
   If shift is one-time anomaly: Keep at 0.90, add note
   ```
6. **Reforecast remaining months** with updated drivers

## Seasonal Adjustment Validation Checklist

- [ ] Indices are based on 36+ months of data (3+ years)
- [ ] Pattern repeats across all years (within 5% variance)
- [ ] Indices sum to approximately 12 (total annual consumption stays constant)
- [ ] Extreme months (peak/trough) are documented and explained
- [ ] Forecast peaks match historical peaks
- [ ] Forecast troughs match historical troughs
- [ ] Seasonal notes are recorded in Excel comments for future reference
- [ ] COGS and variable expenses scale with revenue seasonality
- [ ] Fixed expenses (rent, payroll) are NOT adjusted for seasonality
- [ ] Revenue-based variable expenses are adjusted proportionally

