# CLAUDE.md: cfo-finance-mastery Plugin

## Plugin Overview

This plugin provides **comprehensive CFO-level financial analysis, modeling, forecasting, dashboards, profit optimization, and advisory frameworks** for business owners and operators managing $100M+ in decisions.

Built from:
- Charles Leikauf's **CFO Mastery** program (strategic frameworks, profit levers, client engagement, sales psychology)
- Josh Aharonoff's **Financial Modeling & Excel Dashboards** courses (DADA framework, Power Query, three-statement integration)
- Real-world case studies and client scenarios

**Design principle:** Organized by **workflow stage**, not financial topic. Business owners work through: Diagnose → Understand Drivers → Forecast → Optimize → Monitor → Communicate. This plugin follows that sequence.

---

## Skill Routing Table

| User Intent | Primary Skill | Secondary Skill | Trigger Command |
|------------|--------------|-----------------|-----------------|
| "My financials are confusing" | financial-diagnostics | financial-modeling-excel | /analyze-financials |
| "I don't understand cash vs profit" | financial-diagnostics | advisory-communication | /analyze-financials |
| "I need a financial model" | financial-modeling-excel | forecasting-strategy | /forecast-to-model |
| "How do I build a model?" | financial-modeling-excel | power-query-dashboards | /forecast-to-model |
| "What will next year look like?" | forecasting-strategy | profit-levers | /build-forecast |
| "I need a forecast" | forecasting-strategy | financial-modeling-excel | /build-forecast |
| "How do I make more profit?" | profit-levers | financial-diagnostics | /optimize-profit |
| "My margins are shrinking" | profit-levers | financial-diagnostics | /optimize-profit |
| "I need to improve cash flow" | profit-levers | financing-strategy | /optimize-profit |
| "Should I take a loan?" | financing-strategy | profit-levers | /financing-decision |
| "What's the best financing?" | financing-strategy | forecasting-strategy | /financing-decision |
| "I need a dashboard" | power-query-dashboards | financial-modeling-excel | /build-dashboard |
| "How do I monitor monthly?" | power-query-dashboards | financial-diagnostics | /build-dashboard |
| "How do I explain this to my investor?" | advisory-communication | financial-diagnostics | /explain-to-stakeholder |
| "My team doesn't understand the numbers" | advisory-communication | financial-diagnostics | /explain-to-stakeholder |
| "How do I coach my CFO?" | advisory-communication | depends on peer's focus (diagnostics/modeling/forecasting/profit/financing) | /mentor-peer |
| "What's my burn rate?" / "Am I running out of cash?" | financial-diagnostics | — | /analyze-financials |
| "Help me prepare for a board meeting" | advisory-communication | financial-diagnostics | /explain-to-stakeholder |
| "What KPIs should I track?" | power-query-dashboards | financial-diagnostics | /build-dashboard |
| "Compare this quarter to last quarter" | financial-diagnostics | — | /analyze-financials |
| "Should I hire more people?" / "Can I afford to expand?" | forecasting-strategy | profit-levers | /build-forecast |
| "What's my cash runway?" / "How fast are we burning?" | financial-diagnostics | forecasting-strategy | /analyze-financials |
| "When will we break even?" | forecasting-strategy | profit-levers | /build-forecast |
| "I need to prepare for the board meeting" | advisory-communication | financial-diagnostics | /explain-to-stakeholder |
| "How do I run the monthly close?" | financial-diagnostics | financial-modeling-excel | /analyze-financials |

---

## Ambiguous Request Decision Tree

```
User asks something financial but it's unclear which skill to use
│
├─ "I need help with my financials"
│  └─ Ask: "Are you trying to understand what happened (analysis)
│            or predict what comes next (forecast)?"
│
├─ "I'm growing but losing money"
│  └─ Root cause: financial-diagnostics first (identify the problem)
│      Then: profit-levers (fix it)
│
├─ "I need an Excel model"
│  └─ Ask: "Do you have a forecast to put in the model, or do we
│            need to build that first?"
│      If no forecast: /build-forecast first, then /forecast-to-model
│      If yes: /forecast-to-model directly
│
├─ "Should I invest in X / expand / hire?"
│  └─ Root cause: forecasting-strategy (model the impact)
│      Then: financing-strategy (if capital needed)
│
├─ "I don't know if we're on track"
│  └─ Build diagnostics first: /analyze-financials
│      Then: power-query-dashboards (create monitoring system)
│
├─ "My investor is asking questions"
│  └─ Root cause: advisory-communication (/explain-to-stakeholder)
│      May need financial-diagnostics first if investor is asking
│      for specific analysis
│
├─ IF request is about hiring/scaling/expansion
│  └─ Route to forecasting-strategy first (model the impact before deciding)
│
├─ IF request is about presenting to board/investors
│  └─ Route to advisory-communication with financial-diagnostics as secondary
│
└─ If still unclear: "Tell me what decision you're trying to make,
                       and what information you need to make it well."
```

---

## Execution Priority Order

When a user asks for something that could involve multiple skills, address in this order:

### 1. **Diagnose Reality First**
- Use financial-diagnostics before recommending changes
- Can't optimize what you don't understand
- Exception: If they already have a diagnosis, skip to #2

### 2. **Understand Drivers**
- Use financial-modeling-excel to link assumptions to outcomes
- Prevents "false solutions" to misdiagnosed problems
- Exception: If they just want quick recommendations, can skip to #3

### 3. **Model the Future**
- Use forecasting-strategy to stress-test ideas
- Prevents decisions that look good short-term but fail long-term
- Exception: If they're in crisis (need immediate optimization), can parallelize with #4

### 4. **Optimize Within Reality**
- Use profit-levers once you know the business model
- Focus on highest-impact levers first
- Exception: Some levers (pricing) require forecasting first

### 5. **Get Financing Right**
- Use financing-strategy only AFTER profit optimization (don't borrow to cover bad margins)
- Structure capital stacks on sound business model
- Exception: If they're in working capital crisis, address immediately

### 6. **Monitor & Communicate**
- Use power-query-dashboards for ongoing tracking
- Use advisory-communication for stakeholder updates
- These run in parallel; both important for execution

---

## Slash Command Summary

| Command | Purpose | Skill |
|---------|---------|-------|
| `/analyze-financials` | Diagnose P&L, balance sheet, cash flow | financial-diagnostics |
| `/build-forecast` | Create 12-month forecast | forecasting-strategy |
| `/optimize-profit` | Identify profit levers and quick wins | profit-levers |
| `/financing-decision` | Evaluate financing options, true cost | financing-strategy |
| `/build-dashboard` | Create Excel dashboard with Power Query | power-query-dashboards |
| `/forecast-to-model` | Convert forecast into 3-statement model | financial-modeling-excel |
| `/explain-to-stakeholder` | Translate financials for audience | advisory-communication |
| `/mentor-peer` | Coach peer through financial challenge | advisory-communication |

---

## Skill Cross-References

### financial-diagnostics
- References: financial-modeling-excel (for modeling corrected financials), profit-levers (once diagnosis reveals problems), advisory-communication (explaining findings to stakeholders)
- Trigger: "What's happening in my financials?"

### financial-modeling-excel
- References: financial-diagnostics (analyze historicals first), forecasting-strategy (extend model into future), power-query-dashboards (display model outputs), profit-levers (use model to test scenarios)
- Trigger: "I need a financial model"

### forecasting-strategy
- References: financial-diagnostics (understand historical trends), financial-modeling-excel (convert forecast to model), profit-levers (optimize within forecast), financing-strategy (ensure cash flow supports debt)
- Trigger: "What should my business look like next year?"

### profit-levers
- References: financial-diagnostics (identify which levers are broken), forecasting-strategy (model impact of changes), financing-strategy (understand cost of capital before investing), advisory-communication (influence stakeholder adoption)
- Trigger: "How do I make more profit?"

### financing-strategy
- References: forecasting-strategy (understand cash flow before committing to debt), profit-levers (optimize before borrowing), advisory-communication (explain capital decisions to board)
- Trigger: "Do I need a loan? What's the best option?"

### power-query-dashboards
- References: financial-modeling-excel (data source), financial-diagnostics (interpret dashboard outputs), advisory-communication (present to stakeholders)
- Trigger: "I need a dashboard I can update monthly"

### advisory-communication
- References: All skills (communication is delivery mechanism), most commonly paired with financial-diagnostics (explaining findings) and forecasting-strategy (presenting scenarios)
- Trigger: "How do I explain this to my investor/team?"

---

## Product Marketing Context

This plugin is built for:
- **Business owners** with $100M+ in financial decisions (not aspiring CFOs)
- **Operators** who want to understand and improve their own financials (not outsource)
- **Strategic thinkers** who want frameworks and models, not just analysis
- **Action-oriented** folks who need to implement, not just learn

**Not designed for:**
- Bookkeeping or accounting accuracy issues (those belong to accounting team)
- Tax optimization (that's a CPA/tax advisor role)
- Business strategy beyond financial implications
- External consulting sales process

---

## In Scope vs Out of Scope

### IN SCOPE (CFO Work)
- Financial analysis and interpretation (P&L, balance sheet, cash flow)
- Forecasting and scenario planning
- Driver-based financial modeling
- Profit lever identification and optimization
- Working capital management (AR, AP, inventory)
- Financing options and capital structure
- KPI dashboarding and monitoring
- Communication frameworks and advisor positioning
- Real-world case studies and niche-specific insights

### OUT OF SCOPE
- Bookkeeping corrections or GL reconciliation (accounting team)
- Tax planning or tax filing (CPA/tax advisor)
- General business consulting unrelated to finance
- Operational execution (owner/operations team)
- Moving client funds or running payroll (liability risk)
- Personal financial planning (outside business)
- Hourly billing advice (only value-based pricing)
- Sales methodology (only financial advisory framework)

---

## Key Assumptions About Users

1. **They have financial data available** (QuickBooks, Xero, exports, or manual records)
2. **They want to use Excel** (not other BI tools; Excel is standard for their environment)
3. **They're making decisions, not reporting to regulators** (financial statements vs SEC compliance)
4. **They value action over perfection** (directionally correct forecast beats perfect one never completed)
5. **They're willing to learn frameworks** (not just hire someone else)
6. **They want opinionated advice** (not just "here are the options")

---

## Quality Standards

- **SKILL.md files:** Under 500 lines, concept-focused, decision trees with examples
- **Reference files:** 200–600 lines, detailed, step-by-step, real case studies
- **Slash commands:** Interactive, ask questions first, produce structured output
- **Tone:** Practical, specific, synthesized, opinionated (not generic "best practices")
- **Real numbers:** Always use exact thresholds (e.g., 30% cost of capital hurdle, 45-day DSO, safety stock formula)
- **Jargon:** Financial terms explained once, then used confidently

---

## How to Use This Plugin

1. **Start with your question or decision:** "I need to improve profit" → /optimize-profit
2. **Plugin asks clarifying questions** → You provide data and context
3. **Plugin suggests skill(s)** → Reads relevant SKILL.md + reference files
4. **Plugin produces structured output** → Analysis, recommendation, roadmap
5. **Plugin suggests next step** → "Now try /forecast-to-model to test impact" or "See profit-levers skill for deep dive"

Each interaction leaves you more financially literate and self-sufficient.
