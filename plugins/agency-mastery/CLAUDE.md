# Agency Mastery v1.0.0 -- Routing & Operations

## Plugin Overview

Complete agency building knowledge engine covering the full lifecycle from strategic foundation to scaling and leadership. Built from 3 extraction files covering Shan Hanif (Genflow, $100M+ revenue, 100+ team), Dee Deng (Right Hook Digital, 115+ people, 9 time zones), and Donvesh (Agency Cashflow Roadmap, 0-to-$25K systems).

---

## Ambiguous Request Decision Tree

When a user's request could match multiple skills, use this decision tree:

```
Is the user asking about AGENCY TYPE, VISION, VALUES, MISSION, or SKILLS AUDIT?
  YES -> agency-foundation
  NO -> Continue

Is the user asking about NICHE SELECTION, IACP, USP, PERSONA, or POSITIONING?
  YES -> niche-positioning
  NO -> Continue

Is the user asking about PRICING, OFFER STRUCTURE, RETAINERS, or CONTRACTS?
  YES -> offer-pricing
  NO -> Continue

Is the user asking about FINDING CLIENTS, OUTREACH, DMs, ADS, or LEAD GEN?
  YES -> client-acquisition
  NO -> Continue

Is the user asking about SALES CALLS, CLOSING, PROPOSALS, DECKS, or NEGOTIATION?
  YES -> sales-closing
  NO -> Continue

Is the user asking about ONBOARDING A NEW CLIENT, KO MEETING, or WELCOME EMAIL?
  YES -> client-onboarding
  NO -> Continue

Is the user asking about SOPs, PROJECT MANAGEMENT, FUNCTION CHART, or PROCESSES?
  YES -> delivery-operations
  NO -> Continue

Is the user asking about CLIENT COMMUNICATION, MEETINGS, REPORTING, or RETENTION?
  YES -> client-management
  NO -> Continue

Is the user asking about REVENUE, PROFIT, CASH FLOW, KPIs, or FINANCIAL PROJECTIONS?
  YES -> agency-finance
  NO -> Continue

Is the user asking about HIRING, TEAM BUILDING, SCALING, LEADERSHIP, or EQUITY?
  YES -> scaling-team
  NO -> Check if OUT OF SCOPE (see table below) or ask clarifying questions
```

---

## Skill Routing Table (All 10 Skills)

### Layer 1: STARTING (Pre-Revenue to First Client)

| Skill | Triggers | Scope |
|---|---|---|
| `agency-foundation` | agency type, cash flow vs equity, GRA, CIGAR, Ikigai, vivid vision, core values, mission, skills audit, SWOT, service selection, agency triangle, what kind of agency, getting started | Agency types, evolution stages, skills audit, service selection, vision/mission/values, CIGAR methodology, GRA diagnostic, Ikigai, founder mindset |
| `niche-positioning` | niche, IACP, ideal client, USP, positioning, persona, target market, audience research, specialization, competitive analysis, TAM, utility trap | IACP framework, niche selection, niche-service matrix, USP creation, audience research, customer persona, positioning grid, TAM validation |
| `offer-pricing` | pricing, offer, retainer, fee, rate, how much to charge, value-based, performance pricing, contract terms, discounting, foot-in-door, packages | Bottom-up/top-down pricing, performance models, 10% value rule, price escalation, anti-discounting, foot-in-door, contract clauses |
| `client-acquisition` | find clients, get clients, outreach, DMs, cold email, hot outreach, lead gen, personal brand, content, paid ads, video audit, landing page, VSL, funnel | 6 acquisition channels, DM frameworks, hot/cold outreach, paid ads, video audits, lead sourcing, landing pages, VSLs, follow-up sequences |
| `sales-closing` | sales call, discovery call, close, closing, deck, pitch, proposal, negotiation, objection handling, pipeline, CRM, qualifying questions | Sales pipeline, pre-call prep, call frameworks, deck structure, MVP pitch, discovery call pull method, negotiation tactics, proposals/contracts |

### Layer 2: BUILDING ($0-10K/month)

| Skill | Triggers | Scope |
|---|---|---|
| `client-onboarding` | onboarding, new client setup, kick-off, KO meeting, welcome email, onboarding form, first 30 days | Onboarding sequence, internal KO email, client welcome, onboarding form, KO meeting/deck, post-KO actions, first 30 days |
| `delivery-operations` | SOP, standard operating procedure, process, project management, Asana, function chart, RACINDA, matrix management, knowledge management | SOP types/rollout, RACINDA, function chart, PSIU framework, matrix management, project boards, process library, knowledge management |
| `client-management` | client communication, account management, client meetings, reporting, retention, testimonials, SLAs, weekly cadence, monthly report | 5 pillars of account management, communication SLAs, meeting framework, reporting templates, testimonial collection, dashboards |

### Layer 3: GROWING ($10K-50K/month)

| Skill | Triggers | Scope |
|---|---|---|
| `agency-finance` | revenue, profit, cash flow, KPIs, financial projections, unit economics, cash buffer, EBITDA, time tracking, over-servicing | Revenue waterfall, KPI chain, cash buffer benchmarks, profit-per-team, projections, revenue concentration risk, time tracking |

### Layer 4: SCALING ($50K+/month)

| Skill | Triggers | Scope |
|---|---|---|
| `scaling-team` | hiring, team, scaling, leadership, equity, co-founder, first hire, VA, SDR, retention strategies, missionaries, A-players | Hiring platforms/process, talent-sales staircase, missionaries vs mercenaries, interview process, equity/vesting, leadership grid, partnerships |

---

## Cross-Reference Map

| Skill | Overlaps With | Resolution |
|---|---|---|
| `niche-positioning` | `client-acquisition` | niche-positioning owns audience research; client-acquisition owns applying it to outreach targeting |
| `offer-pricing` | `sales-closing` | offer-pricing owns pricing strategy; sales-closing owns presenting price on calls |
| `offer-pricing` | `agency-finance` | offer-pricing owns client-facing pricing; agency-finance owns internal unit economics |
| `client-acquisition` | `sales-closing` | client-acquisition owns pre-call lead qualification; sales-closing owns on-call qualification |
| `client-onboarding` | `client-management` | client-onboarding owns setup and first 30 days; client-management owns ongoing cadence |
| `client-onboarding` | `delivery-operations` | client-onboarding owns what happens; delivery-operations owns how (SOPs) |
| `client-management` | `agency-finance` | client-management owns client-facing metrics; agency-finance owns internal P&L |
| `delivery-operations` | `scaling-team` | delivery-operations owns org design (function chart); scaling-team owns hiring execution |
| `agency-foundation` | `scaling-team` | agency-foundation owns vision/values definition; scaling-team owns operationalizing them in culture |

---

## Commands (7)

### `/agency-audit`
**Purpose:** Diagnose current agency state and identify highest-leverage next action.
**Skills used:** `agency-foundation`, `agency-finance`, `scaling-team`
**Behavior:** Ask about current revenue, team size, number of clients, biggest bottleneck (acquisition/fulfillment/finance). Map to agency evolution stage. Output: current stage diagnosis, top 3 priorities, which skills to focus on, GRA-style assessment.

### `/agency-offer`
**Purpose:** Build or refine an agency offer with pricing.
**Skills used:** `offer-pricing`, `niche-positioning`
**Behavior:** Walk through service selection, niche validation, bottom-up cost calculation, top-down market positioning. Generate complete offer structure (base + performance components). Warn against hourly pricing, discounting, money-back guarantees.

### `/agency-outreach`
**Purpose:** Generate a personalized outreach sequence for a specific prospect.
**Skills used:** `client-acquisition`, `niche-positioning`
**Behavior:** Ask for prospect details (name, company, industry, problem identified). Generate: hot outreach email (3-section template), DM message, follow-up sequence (day 2/5/10). Suggest video audit or spec work based on deal size. Include channel recommendation.

### `/agency-sales-prep`
**Purpose:** Prepare for a specific sales call.
**Skills used:** `sales-closing`, `offer-pricing`
**Behavior:** Ask for prospect info, current situation, problems identified. Generate: pre-call research checklist, customized deck outline (8 slides), qualifying questions tailored to prospect, key objections to prepare for, pricing recommendation.

### `/agency-onboard`
**Purpose:** Generate complete onboarding package for a new client.
**Skills used:** `client-onboarding`, `client-management`
**Behavior:** Ask for client name, service, fee, term, team members. Generate: internal KO email, client welcome email, KO meeting agenda, KO deck outline, post-KO action checklist, communication channel setup, first-30-days plan.

### `/agency-report`
**Purpose:** Structure a client report (weekly or monthly).
**Skills used:** `client-management`, `agency-finance`
**Behavior:** Ask for report type (weekly/monthly), service type, key metrics. Generate: report structure, section headings, commentary template, recommended visualizations, next-month goals format.

### `/agency-hire`
**Purpose:** Build a hiring plan for the next role.
**Skills used:** `scaling-team`, `delivery-operations`
**Behavior:** Ask for current team size, revenue, biggest bottleneck, budget. Use function chart logic to identify most-leverage role. Generate: JD draft, application task, interview questions (culture fit + skills), trial period structure, onboarding checklist. Recommend hiring platform.

---

## Scope Boundaries -- Out of Scope

| Topic | Route To | Boundary |
|---|---|---|
| Cold email infrastructure (deliverability, warmup, sequences) | `cold-outbound-mastery` | Agency-mastery covers WHEN/WHY to use cold email; cold-outbound-mastery covers HOW to set up |
| Facebook/Meta ads tactics for clients | `paid-ads-mastery` | Agency-mastery covers ads for acquiring agency clients; paid-ads-mastery covers ad buying for client campaigns |
| Deep copywriting frameworks | `cro-copywriting-mastery` | Agency-mastery includes basic copy frameworks for outreach; CRO plugin covers deep copywriting for deliverables |
| SEO execution for clients | `seo-mastery` | Agency-mastery covers content strategy for personal branding; seo-mastery covers SEO for client work |
| Email marketing for clients | `email-marketing-mastery` | Agency-mastery covers agency-specific sequences; email plugin covers email strategy for client campaigns |
| General B2B sales methodology | `sales-negotiation-mastery` | Agency-mastery covers selling agency services; sales plugin covers general high-ticket sales methodology |
| Legal entity formation (LLC, S-Corp) | Consult CPA/attorney | Out of scope -- legal/accounting advice |
| International expansion mechanics | Local legal counsel | Mentioned but not taught in depth by any instructor |
