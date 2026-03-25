---
name: "Scenario Modeling"
description: "Best/base/worst case construction, scenario variable selection, input ranges, o-shoot fund concept, decision-making across scenarios, presentation framework."
when_to_read: "When the user needs to build scenario models, determine scenario inputs, construct best/base/worst cases, or make decisions that account for multiple possible futures."
---

# Scenario Modeling

## Three-Scenario Framework (Leikauf)

### Base Case (Build First)
The most likely outcome. Blend of realism and caution.

**Construction:**
1. Start with historical trends as foundation
2. Apply STEP headwinds and tailwinds from external analysis
3. Use Aharonoff's projection methods for each line item
4. Validate with department heads and management
5. This becomes the primary forecast used for decision-making

### Best Case
Everything works under ideal conditions -- but still realistic.

**Construction:**
1. Start from base case
2. Apply optimistic values to 3-5 key swing variables
3. Assume tailwinds materialize fully, headwinds partially mitigated
4. Revenue growth at the high end of reasonable range
5. Cost efficiencies achieved as planned

**Common mistake:** Making best case too optimistic. If it has never happened before in the business, it probably should not be in the best case.

### Worst Case
A few major setbacks -- not catastrophe, not business failure.

**Construction:**
1. Start from base case
2. Apply pessimistic (but plausible) values to same 3-5 key variables
3. Assume headwinds materialize fully, tailwinds do not
4. Revenue growth at the low end or flat
5. Key costs increase beyond plan

**Common mistake:** Making worst case either too mild (just 5% below base) or too extreme (company goes bankrupt). It should represent a bad-but-survivable year.

---

## Selecting Scenario Variables

Choose 3-5 variables that have the largest impact on outcomes. Typical swing variables:

| Variable | Base Case | Best Case | Worst Case |
|----------|-----------|-----------|------------|
| Revenue growth rate | 10% | 18% | 2% |
| Customer acquisition cost | $45 | $35 | $65 |
| COGS as % of revenue | 38% | 35% | 42% |
| Headcount additions | 5 | 8 | 2 |
| Average order value | $85 | $95 | $75 |

### Variable Selection Criteria
- **High sensitivity:** Small changes in this variable produce large changes in outcomes
- **High uncertainty:** This variable could plausibly swing significantly
- **Manageable count:** 3-5 variables. More than that makes scenarios unmanageable
- **Independent:** Variables should not all move in the same direction for the same reason

---

## The "O Shoot Fund" (Leikauf)

The worst-case scenario is not just a planning exercise -- it determines how much cash buffer the business needs.

**Calculation:**
```
O Shoot Fund = Base Case Operating Expenses x 3 months
  PLUS: Worst Case Revenue Shortfall x 6 months
  PLUS: Unexpected CapEx buffer
```

**Simpler approach:**
```
Required Cash Buffer = Worst Case Monthly Cash Burn x Number of Months to Recovery
```

This is more actionable than the generic "save 3-6 months of expenses" because it is based on YOUR worst case, not a rule of thumb.

---

## Decision-Making Across Scenarios

### The Resilience Test
For any major decision (new hire, expansion, large investment):

1. **Does it work in the base case?** If no, do not proceed.
2. **Does it still work in the worst case?** If no, it is too risky.
3. **Does it amplify the best case?** If yes, it has upside potential.
4. **Can you reverse it if the worst case happens?** Reversible decisions are safer.

### Decision Matrix
| Decision | Best Case Impact | Base Case Impact | Worst Case Impact | Proceed? |
|----------|-----------------|-----------------|-------------------|----------|
| Hire 2 salespeople | Revenue +25% | Revenue +12% | Burn increases 8% | Yes (reversible) |
| Sign 3-year lease | Saves $2K/mo | Saves $2K/mo | Locked into cost | Cautious (irreversible) |
| Launch new product | Revenue +40% | Revenue +15% | Development cost wasted | Yes if staged |

### Forecasting Accuracy
It is acceptable to be slightly wrong in forecasts, but not drastically wrong (Leikauf). Scenario modeling does not predict the future -- it prepares you for multiple futures so you are never blindsided.

---

## Scenario Presentation Framework

When presenting scenarios to stakeholders:

1. **Start with base case** -- this is the plan
2. **Show the range** -- best case to worst case creates a confidence interval
3. **Highlight key swing variables** -- what determines which scenario we land in
4. **Identify decision points** -- "If revenue drops below X by Month 6, we trigger Plan B"
5. **Present the buffer** -- "We have enough cash to survive worst case for Y months"

### Visual Format
Use a stacked or clustered bar chart showing all three scenarios for key metrics:
- Revenue
- Operating Income
- Ending Cash Balance
- Headcount

---

## Reforecasting Rhythm

**Monthly:** Update actuals, compare to base case, investigate variances
**Quarterly:** Full reforecast with updated assumptions, save "memorialized" version (Aharonoff)
**Annually:** New 12-month rolling forecast with fresh STEP/Porter analysis

---

## Cross-References

- **External factors driving scenario assumptions** -> `external-analysis.md` (this skill)
- **Projection methods for building scenarios** -> `projection-methods.md` (this skill)
- **Budget vs actuals from scenario baseline** -> `financial-modeling/actualization-and-rollforward.md`
- **Cash flow implications of scenarios** -> `financial-diagnostics/references/cash-flow-analysis.md`
- **Presenting scenarios to stakeholders** -> `advisory-communication`
