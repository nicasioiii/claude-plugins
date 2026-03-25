# Funnel Mastery v1.0.0 -- Routing & Operations

## Plugin Overview

Complete funnel strategy and design knowledge engine for online businesses. Built from 4 extraction files covering 4 courses across ~100+ hours of instruction from Alex Hormozi ($100M Money Models / $18K Upsell), Gusten Sun (Funnel University 2025), Katie & Floyd (3X Profit Upsells, Downsells & Cross-Sells), and Stefan Georgi (RMBC II). Provides end-to-end guidance from funnel economics through market research, offer stack design, funnel architecture, sales page copy, VSL scripts, advertorials, upsell/downsell strategy, backend sequences, checkout optimization, and conversion rate optimization.

---

## Ambiguous Request Decision Tree

When a user's request could match multiple skills, use this decision tree:

```
IF request mentions "math" or "profitable" or "CAC" or "CPA" or "AOV" or "LTV" or "break even" or "economics"
  -> funnel-economics

IF request mentions "research" or "awareness level" or "customer persona" or "who is my customer" or "target market"
  -> market-research

IF request mentions "offer" or "pricing" or "what should I sell" or "value ladder" or "attraction offer" or "money model"
  -> offer-stack-design

IF request mentions "which funnel" or "funnel type" or "map my funnel" or "design my funnel" or "what kind of funnel"
  -> funnel-architecture

IF request mentions "sales page" or "landing page copy" or "write my page"
  -> sales-page-copy

IF request mentions "VSL" or "video sales letter" or "VSL script"
  -> vsl-sales-copy

IF request mentions "advertorial" or "presell" or "native ad page" or "pre-sell article"
  -> advertorial-copy

IF request mentions "upsell" or "downsell" or "order bump" or "post-purchase" or "OTO"
  -> upsell-downsell-strategy

IF request mentions "backend email" or "post-purchase email" or "backend sequence"
  -> backend-sequences

IF request mentions "checkout" or "cart abandonment" or "checkout page" or "payment options"
  -> checkout-optimization

IF request mentions "optimize" or "split test" or "conversion rate" or "CRO" or "not converting"
  -> funnel-cro

IF request is broad ("help me with my funnel" / "I want to build a funnel" / "I sell [product]")
  -> Ask: "Are you looking to: (A) evaluate your funnel economics/profitability, (B) research your market and audience, (C) design your offer stack and pricing, (D) select and map your funnel type, or (E) optimize an existing funnel?"

ELSE -> route to funnel-architecture (most common starting point for new funnels)
```

---

## Skill Routing Table (All 11 Skills)

### Stage 1: STRATEGY & ECONOMICS
| Skill | Display Name | Use When |
|---|---|---|
| `funnel-economics` | Funnel Economics | CAC/GP/LTV math, CFA levels, AOV targets, profitability modeling, break-even analysis, margin targets |
| `market-research` | Market Research | Schwartz awareness levels, psychographic research, competitor analysis, research briefs, TAM estimation |

### Stage 2: OFFER DESIGN
| Skill | Display Name | Use When |
|---|---|---|
| `offer-stack-design` | Offer Stack Design | Money models, attraction offers, pricing psychology, value ladders, 3T Triangle, sequential build order |

### Stage 3: FUNNEL ARCHITECTURE
| Skill | Display Name | Use When |
|---|---|---|
| `funnel-architecture` | Funnel Architecture | 10 funnel types, 15-factor scoring, platform congruency, selection tree, funnel blueprints |

### Stage 4: COPY & CONTENT
| Skill | Display Name | Use When |
|---|---|---|
| `sales-page-copy` | Sales Page Copy | CONVERSIONS framework, 10-step sales page, feature-benefit-impact chains, high-ticket page structure |
| `vsl-sales-copy` | VSL Sales Copy | Classic VSL outline, 8 short VSL structures, unique mechanism development, in-feed vs. on-page VSL |
| `advertorial-copy` | Advertorial Copy | Presell articles, native ad landing pages, advertorial structure, length guidelines |

### Stage 5: POST-PURCHASE
| Skill | Display Name | Use When |
|---|---|---|
| `upsell-downsell-strategy` | Upsell & Downsell Strategy | Binge-buying psychology, upsell timing, order bumps, 4 upsell types, downsell rules, continuity |
| `backend-sequences` | Backend Sequences | Post-purchase email sequences, backend offer ordering, email copy patterns, high-ticket email selling |
| `checkout-optimization` | Checkout Optimization | Order form design, one-click upsells, trust elements, payment plans, platform selection |

### Stage 6: OPTIMIZE
| Skill | Display Name | Use When |
|---|---|---|
| `funnel-cro` | Funnel CRO | 5D CRO system, 9 conversion levers, compound testing, Position/Price/Switch framework, split tests |

---

## Cross-Reference Map with Trigger Conditions

| Source Skill | References | Trigger Condition |
|---|---|---|
| `funnel-economics` | `offer-stack-design` | Economics healthy, want more revenue per customer |
| `funnel-economics` | `funnel-cro` | Economics broken, CPA too high |
| `market-research` | `offer-stack-design` | Research complete, ready to design offer |
| `market-research` | `vsl-sales-copy` | Research complete, need VSL copy |
| `offer-stack-design` | `funnel-architecture` | Offer stack designed, select funnel type |
| `offer-stack-design` | `upsell-downsell-strategy` | Need specific upsell/downsell design |
| `funnel-architecture` | `sales-page-copy` | Funnel type selected, write copy |
| `funnel-architecture` | `vsl-sales-copy` | Funnel type selected, write VSL |
| `funnel-architecture` | `upsell-downsell-strategy` | Funnel includes post-purchase flow |
| `upsell-downsell-strategy` | `funnel-economics` | After designing upsells, validate math |
| `upsell-downsell-strategy` | `backend-sequences` | Upsells include backend email flow |
| `funnel-cro` | `funnel-economics` | CRO improvements, update projections |
| `funnel-cro` | `offer-stack-design` | CRO reveals offer is wrong |
| Any copy skill | `market-research` | Research must be done before writing copy |

---

## Slash Command Table

| Command | Description | Skills Activated |
|---|---|---|
| `/funnel-audit` | Diagnose an existing funnel's performance | funnel-economics, funnel-cro |
| `/design-funnel` | Design a complete funnel from scratch | market-research, funnel-architecture, offer-stack-design |
| `/build-offer-stack` | Create complete offer string (front-end through backend) | offer-stack-design, upsell-downsell-strategy, funnel-economics |
| `/write-sales-page` | Generate sales page copy | market-research, sales-page-copy |
| `/write-vsl` | Generate VSL script | market-research, vsl-sales-copy |
| `/design-upsells` | Design post-purchase upsell flow | upsell-downsell-strategy, checkout-optimization |
| `/optimize-funnel` | Run CRO process on existing funnel | funnel-cro, funnel-economics |

---

## Cross-Plugin Boundaries

| Topic | This Plugin Handles | Delegate To |
|---|---|---|
| Paid ad creation, targeting, budgets | Nothing (ad context only for funnel design) | `paid-ads-mastery` |
| Email marketing strategy/general sequences | Post-purchase backend sequences only | `email-marketing-mastery` |
| Cold outreach / DM selling | Nothing | `cold-outbound-mastery` |
| Web design / Webflow builds | Nothing | `design-mastery` |
| General copywriting principles | Funnel-specific copy only | `cro-copywriting-mastery` |

---

## Instructor Source Map

| Instructor | Primary Skills |
|---|---|
| Alex Hormozi (E01) | funnel-economics, offer-stack-design, upsell-downsell-strategy |
| Gusten Sun (E02) | funnel-architecture, sales-page-copy, funnel-cro, offer-stack-design |
| Katie & Floyd (E03) | upsell-downsell-strategy, backend-sequences, checkout-optimization, funnel-cro |
| Stefan Georgi (E04) | market-research, vsl-sales-copy, advertorial-copy, funnel-economics, funnel-architecture |

---

## Execution Priority Order

When multiple skills apply: funnel-economics > market-research > offer-stack-design > funnel-architecture > sales-page-copy > vsl-sales-copy > advertorial-copy > upsell-downsell-strategy > backend-sequences > checkout-optimization > funnel-cro

---

## Implementation Notes

- **Decision Tree First:** Use routing tables above to determine which skill(s) to invoke
- **Cross-Reference When Needed:** Acknowledge when multiple skills contribute
- **SKILL.md First, Then References:** Start with SKILL.md for high-level guidance, then reference files for deep specifics
- **Ask Clarifying Questions:** If business model or funnel type is ambiguous, ask before routing
- **Instructor Disagreements:** When instructors disagree, present both positions and the reconciliation. Never silently pick one side
- **Business Model Context:** If the user has specified their business model (digital product, service, DTC, SaaS), filter advice accordingly. Hormozi's frameworks skew toward service businesses. Katie's toward digital products. Georgi's toward DTC supplements. Gusten's toward personal brand info products.
