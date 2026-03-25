# CFO Finance Mastery v2.0 -- Routing & Operations

## Plugin Overview

Complete CFO-level financial knowledge engine for business owners. Built from 4 extraction files covering Leikauf's CFO Mastery curriculum and Aharonoff's Financial Modeling, Excel Dashboard, and Excel Everything courses. Provides end-to-end guidance from financial statement diagnosis through three-statement modeling, covering diagnostics, ratio analysis, forecasting, modeling, profit optimization, working capital, financing, dashboards, Excel techniques, and stakeholder communication.

---

## Ambiguous Request Decision Tree

When a user's request could match multiple skills, use this decision tree:

```
Is the user asking about READING or DIAGNOSING financial statements?
  YES -> Is it about specific ratios or benchmarks? -> financial-ratios
       -> Is it about AR/AP/inventory management? -> working-capital
       -> Otherwise -> financial-diagnostics
  NO -> Continue

Is the user asking about RATIOS, BENCHMARKS, or LENDING METRICS?
  YES -> financial-ratios
  NO -> Continue

Is the user asking about FORECASTING or PROJECTIONS?
  YES -> Is it about building assumptions, scenarios, or projection methods? -> forecasting-strategy
       -> Is it about building the actual model in Excel? -> financial-modeling
  NO -> Continue

Is the user asking about a FINANCIAL MODEL or THREE-STATEMENT MODEL?
  YES -> Is it about the architecture, drivers tab, or error checks? -> financial-modeling
       -> Is it about choosing projection methods? -> forecasting-strategy
       -> Is it about Excel formulas/shortcuts? -> excel-for-finance
  NO -> Continue

Is the user asking about PROFIT IMPROVEMENT?
  YES -> Is it about pricing, cost reduction, or revenue growth? -> profit-optimization
       -> Is it about AR/AP/inventory/CCC specifically? -> working-capital
  NO -> Continue

Is the user asking about FINANCING or LENDING?
  YES -> financing-strategy
  NO -> Continue

Is the user asking about DASHBOARDS or REPORTING?
  YES -> Is it about Excel dashboard design? -> dashboards-and-reporting
       -> Is it about presenting to stakeholders? -> advisory-communication
  NO -> Continue

Is the user asking about EXCEL techniques?
  YES -> excel-for-finance
  NO -> Continue

Is the user asking about COMMUNICATION or CLIENT CALLS?
  YES -> advisory-communication
  NO -> Ask clarifying questions
```

---

## Skill Routing Table (All 10 Skills)

### Layer 1: FOUNDATION
| Skill | Display Name | Use When |
|---|---|---|
| `financial-diagnostics` | Financial Diagnostics | P&L, balance sheet, cash flow diagnosis, vertical/horizontal/variance analysis, profit leak detection, revenue recognition, COGS vs SG&A classification |
| `financial-ratios` | Financial Ratios | Liquidity, profitability, efficiency, leverage, return, working capital, lending ratios with targets and benchmarks, CCC deep dive, DSCR |

### Layer 2: FORWARD PLANNING
| Skill | Display Name | Use When |
|---|---|---|
| `forecasting-strategy` | Forecasting Strategy | 12-month rolling forecasts, STEP framework, Porter's Five Forces, 3-scenario modeling, 9 P&L projection methods, EPN/ARSR revenue frameworks, headcount projection, seasonal adjustment |
| `financial-modeling` | Financial Modeling | DADA framework, 3-statement model architecture, drivers tab, template tab, color coding, error checks, BS projection, actualization, roll-forward, model audit |

### Layer 3: OPTIMIZATION
| Skill | Display Name | Use When |
|---|---|---|
| `profit-optimization` | Profit Optimization | Pricing strategy, cost reduction, productivity metrics, profit tree, revenue diversification, CLV/RFM analysis, negotiation tactics, best owner theory |
| `working-capital` | Working Capital | AR management (28-day billing, factoring), AP management (vendor negotiation), inventory (ABC analysis, JIT), CCC optimization, payroll timing |

### Layer 4: CAPITAL
| Skill | Display Name | Use When |
|---|---|---|
| `financing-strategy` | Financing Strategy | Five Cs of credit, DSCR targets, debt matching, MCA warning, credit card strategy, SBA programs, lender relationships, personal guarantees |

### Layer 5: MONITORING
| Skill | Display Name | Use When |
|---|---|---|
| `dashboards-and-reporting` | Dashboards & Reporting | Excel dashboards, Power Query ETL, KPI cards, budget vs actuals, gauge/donut charts, management reports, cash-out/break-even/spotlight dashboards, pivot tables |
| `advisory-communication` | Advisory Communication | CFO Value Pyramid, simplification framework, R-D-R format, learning styles, EQ for CFOs, 3x3 monthly call structure, five-day close advocacy |

### Layer 6: ENABLEMENT
| Skill | Display Name | Use When |
|---|---|---|
| `excel-for-finance` | Excel for Finance | Date functions, lookups (INDEX MATCH, XLOOKUP), SUMIFS/SUMPRODUCT, What-If analysis, tables, named ranges, formula auditing, conditional formatting, macros, Camera tool, shortcuts |

---

## Cross-Skill Workflow Chains

### Full Diagnostic-to-Action Workflow
```
financial-diagnostics -> financial-ratios -> forecasting-strategy -> financial-modeling -> dashboards-and-reporting -> advisory-communication
```

### Profit Improvement Workflow
```
financial-diagnostics -> financial-ratios -> profit-optimization -> working-capital -> forecasting-strategy (model impact)
```

### Lending Preparation Workflow
```
financial-diagnostics -> financial-ratios (lending ratios) -> financing-strategy
```

### Model Building Workflow
```
forecasting-strategy (assumptions) -> financial-modeling (construction) -> dashboards-and-reporting (BvA output)
```

---

## Slash Commands

| Command | Primary Skill | Description |
|---------|--------------|-------------|
| `/analyze-financials` | financial-diagnostics | Guided P&L, balance sheet, and cash flow diagnosis |
| `/ratio-analysis` | financial-ratios | Calculate and interpret key financial ratios |
| `/build-forecast` | forecasting-strategy | Build a 12-month rolling forecast with scenarios |
| `/forecast-to-model` | financial-modeling | Convert forecast assumptions into a 3-statement model |
| `/optimize-profit` | profit-optimization | Identify and prioritize profit levers |
| `/working-capital` | working-capital | Optimize AR/AP/inventory and CCC |
| `/financing-decision` | financing-strategy | Evaluate financing options and prepare for lending |
| `/build-dashboard` | dashboards-and-reporting | Design an Excel dashboard with Power Query |
| `/excel-help` | excel-for-finance | Excel formula or technique guidance |
| `/explain-to-stakeholder` | advisory-communication | Translate financial data for a non-finance audience |
| `/structure-cfo-call` | advisory-communication | Plan a monthly CFO review call |

---

## Instructor Disagreements -- Resolution Guide

### SUMPRODUCT vs SUMIFS
- **SUMIFS:** Use for structured data pulls (drivers tab, source-to-destination)
- **SUMPRODUCT:** Use for dashboard formulas with multi-criteria logic and sum/index switching
- Both are correct tools -- use case determines the choice

### P&L Terminology
- **Leikauf:** Uses EBIT/EBITDA (standard in banking/lending contexts)
- **Aharonoff:** Uses "Net Operating Income" / "Net Other Income" (maps to three-statement model)
- **Mapping:** Operating Income = EBIT = Net Operating Income

### Forecasting Approach
- **Leikauf:** External-environment-driven (STEP, Porter's) -- sets assumptions
- **Aharonoff:** Formula-driven projection mechanics (nine methods) -- implements assumptions
- **Resolution:** Complementary. Phase 1: Leikauf's frameworks. Phase 2: Aharonoff's methods.
