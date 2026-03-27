---
name: Monetize Plan
description: Create a personalized monetization plan for a creator. Calculates freedom number, selects revenue model, designs offer stack, and builds launch timeline with pricing strategy.
---

# /monetize-plan -- Creator Monetization Plan Builder

## INTAKE QUESTIONS (Ask All Before Planning)

### Question 1: Current Stage
**Where are you in your creator journey?**

| Choice | Approach |
|--------|----------|
| A) Under 1K followers, no revenue yet | Foundation-first: build audience before monetizing |
| B) 1K-10K followers, ready for first offer | First-dollar plan: low-risk offer validation |
| C) 10K+ followers, some revenue, want to scale | Scaling plan: optimize offer stack and funnels |
| D) Established creator, want new revenue stream | Diversification: add revenue streams strategically |

### Question 2: Expertise and Niche
**What specific transformation can you help people achieve?**
- What is the before state? (specific pain)
- What is the after state? (specific outcome)
- How long does the transformation take?

### Question 3: Revenue Goal
**What is your monthly income target?**

| Range | Strategy |
|-------|----------|
| $1K-$5K/month | 1-3 coaching clients OR low-ticket digital product |
| $5K-$15K/month | Group coaching OR course + community |
| $15K-$30K/month | Premium offer stack OR multiple revenue streams |
| $30K+/month | Diversified: products + coaching + affiliates + partnerships |

### Question 4: Preferred Model
**Which revenue model interests you most?**

| Choice | Model |
|--------|-------|
| A) Digital products (courses, ebooks, templates) | Scalable, build once sell forever |
| B) Coaching or consulting | High-ticket, relationship-based |
| C) Community or membership | Recurring revenue, community-driven |
| D) Brand partnerships | (Route to /build-pitch-deck) |
| E) Ghostwriting or freelance services | (Route to ghostwriting-freelance skill) |
| F) Not sure -- help me decide | Run through decision framework |

---

## EXECUTION PROCESS

### Step 1: Load Skills
1. Load `monetize-content` SKILL.md
2. Load `monetize-content/references/ref-revenue-models.md`
3. Load `monetize-content/references/ref-lead-magnets.md`
4. If community model: also load `community-building` SKILL.md

### Step 2: Calculate Freedom Number
Using the Freedom Number Calculator:
1. Walk through expense categories
2. Calculate gross target (net / 0.6)
3. Work backwards to required sales volume at chosen price point
4. Present revenue model options that fit their audience size

### Step 3: Design Offer Stack
Based on chosen model, build:
- **Core offer** -- The main product/service (name, description, deliverables, price)
- **Entry offer** -- Lead magnet or low-ticket item that feeds the core offer
- **Premium offer** -- Upsell for highest-value clients
- **Pricing rationale** -- Price anchoring and competitive positioning

### Step 4: Build Lead Magnet Funnel
1. Suggest 3 lead magnet ideas based on their expertise
2. Apply naming formula for each
3. Map distribution channels (comment magnet, bio link, stories)
4. Outline email nurture sequence (5 emails)

### Step 5: Create Launch Timeline
Based on their stage, produce:
- Pre-launch content plan (14 days)
- Launch week schedule (5 days)
- Post-launch optimization (7 days)
- Ongoing content-to-sale rhythm

---

## OUTPUT FORMAT

Deliver a complete Monetization Plan document with:

```
## YOUR MONETIZATION PLAN

### Freedom Number
- Monthly target: $___
- Gross target: $___
- Revenue model: ___
- Required sales: ___ per month at $___

### Offer Stack
| Tier | Name | Price | Description |
|------|------|-------|-------------|
| Entry | [Lead magnet name] | Free | [Description] |
| Core | [Main offer name] | $___ | [Description + deliverables] |
| Premium | [Upsell name] | $___ | [Description + additional value] |

### Lead Magnet Plan
- Name: ___
- Type: ___
- Distribution: ___
- Email sequence: [5-email outline]

### Launch Timeline
[14-day pre-launch + 5-day launch + ongoing rhythm]

### Content Mix for Monetization
- Educational: ___% | Personality: ___% | Promotional: ___%
- Lead magnet CTA rotation schedule

### Next Steps (Priority Order)
1. ___
2. ___
3. ___
```

---

## EDGE CASES

- **No audience yet:** Recommend building to 1K followers first. Offer coaching/consulting from day 1 if they have existing expertise (minimum 100 engaged followers in niche).
- **Multiple revenue streams desired:** Prioritize ONE offer first. Add streams sequentially, not simultaneously.
- **Ghostwriting/freelance interest:** Route to `ghostwriting-freelance` skill for service-based monetization.
- **Brand partnerships interest:** Route to `/build-pitch-deck` command.
