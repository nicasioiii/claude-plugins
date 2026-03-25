---
name: "Deliverability Recovery"
description: "New domain strategy, Warmup Inbox configuration, Klaviyo warm-up campaign sequence, IP warm-up send schedule for ESP migration, dual-ESP operation, shared vs. dedicated IP decision, plain text warmup, prevention checklist, and reply-based warmup tactics."
---

# Deliverability Recovery Reference

## New Domain Strategy [E02]

### When to Buy a New Domain
- GlockApps shows Gmail: Spam
- Google Postmaster domain reputation: Low or Bad
- Domain has been flagged and warmup on existing domain has failed after 4+ weeks

### Domain Naming Convention
- Format: `shop[yourdomain].com` or `get[yourdomain].com` or `mail.[yourdomain].com`
- Example: Main domain `acmebrand.com` -> new sending domain `shopacmebrand.com`
- Set up URL forwarding so the new domain redirects to your main site [E02]

### New Domain Setup Checklist
1. Purchase domain
2. Configure DNS: SPF, DKIM, DMARC (see ref-deliverability-diagnosis.md)
3. Set up URL forwarding to main domain
4. Connect to ESP (Klaviyo, etc.)
5. Begin warmup protocol (Steps 3.4-3.7 in SKILL.md)
6. Wait minimum 2-4 weeks before campaign sends [E02]

---

## Warmup Inbox Configuration [E02]

### Tool Purpose
Creates a healthy incoming:outgoing email ratio that signals legitimacy to ISPs. Simulates real email conversations with positive engagement signals.

### Configuration
| Parameter | Setting |
|-----------|---------|
| Starting baseline | 1-2 emails/day |
| Daily increase | 2-3 emails/day |
| Maximum daily volume | 40 emails/day |
| Reply rate target | 40% |
| Duration before retest | 1 week (existing domain), 2-4 weeks (new domain) |

### Supplementary Tactic: Newsletter Signups [E02]
- Sign the sending address up for 10 real newsletters
- Creates organic incoming email flow
- Set Gmail filters to auto-archive these (mark as read, never send to spam)
- Simulates an active, engaged mailbox

### Cost Comparison
- Warmup Inbox: approximately $15-20/month (approximately 20% cost of Lemwarm)
- Lemwarm: approximately $30-40/month
- TrulyInbox: approximately $9/month

---

## Klaviyo Warm-Up Campaign Sequence [E02]

### Pre-Campaign Steps
1. Set up all flows first -- flows create a consistent drip-feed of sends that builds reputation
2. Monitor flow performance: 50%+ open rate on Email 1 of welcome and abandon checkout flows = healthy baseline
3. If flow open rates are below 50%, continue warmup before adding campaigns

### Campaign Warm-Up Progression

| Campaign # | Segment | Expected Open Rate | Notes |
|-----------|---------|-------------------|-------|
| 1 | Highly engaged 60-day OR existing customers + website engagers | 30-50%+ | Most engaged segment; test carefully |
| 2 | Highly engaged 90-day | 25-40% | Expand only if Campaign 1 maintains healthy rates |
| 3 | Highly engaged 120-day | 20-35% | Further expansion |
| 4 | Broader engaged segment | 15-25% | Approach with caution |
| 5+ | Test whole list | Varies | Only after previous campaigns are stable |

### Rules During Warm-Up
- First campaigns should be **plain text** (highest engagement, no image loading issues) [E03]
- Send frequency: start with 1 campaign per week, increase to 2-3/week as reputation improves
- Monitor Google Postmaster and GlockApps after each expansion
- If open rates drop below target, pull back to previous segment level

---

## ESP Migration IP Warm-Up Schedule [E03/MuteSix]

### For a 2M Subscriber List (Example)

**Phase 1: Segment Build**
- Export engagement data from old ESP
- MailChimp -> Klaviyo: native integration ports open/click data automatically
- Other ESPs (Drip, ActiveCampaign, etc.): manual export required
- Build engagement segments in new ESP:
  - Opened last email
  - Opened last 5 emails
  - Opened last 10 emails
  - Opened last 15 emails
  - Opened last 20 emails
- Layer Shopify/ecommerce data: placed order in last 80 weeks

**Phase 2: Random Bucket System**
- Export large segments
- Add "random bucket" custom field (numbered 1-50)
- Use bucket ranges to control exact send volume
- Example: Buckets 7-11 = approximately 35,000 members
- Reuse same email template to different buckets until overlap requires new creative

**Phase 3: Send Volume Ramp**

| Day | Send Volume | Notes |
|-----|------------|-------|
| 1 | ~9,000 | Start with most engaged segment |
| 2-3 | ~18,000 | Double if Day 1 engagement is strong |
| 4-5 | ~38,000 | Continue doubling |
| 6-7 | ~75,000 | Monitor closely |
| 8-10 | ~150,000 | Check GlockApps/Postmaster |
| 11+ | Double until full volume | Maintain engagement benchmarks |

- Double every other day (or daily if list is highly engaged)
- First campaign type: plain text (highest engagement)
- Benchmark: 48%+ open rate on engaged segments; minimum 20-30% overall [E03]

**Phase 4: Dual-ESP Operation**
- Continue sending through old ESP while warming new one
- **Critical rule:** Suppress/exclude warm-up segment recipients from old ESP campaigns. Never double-send the same subscriber from both ESPs
- Turn on flows sequentially: enable welcome flow in new ESP, disable in old ESP. Then abandon checkout. Then post-purchase. Etc.

**Timeline Estimates:**
- 2M list: 3 weeks to 1 month
- 500K list: 2-3 weeks
- Under 100K list: as little as 2 weeks [E03]

---

## Shared vs. Dedicated IP Decision [E03]

| Factor | Shared IP | Dedicated IP |
|--------|-----------|--------------|
| List size threshold | Under 500K subscribers | Over 500K subscribers |
| Your responsibility | ESP maintains overall IP health | You own IP reputation entirely |
| Risk from others | Other senders can damage shared reputation | No risk from other senders |
| Warm-up required | Less -- IP already has reputation | Full warm-up from scratch |
| Best for | Small-to-mid senders, new accounts | Large volume senders, brands with dedicated email teams |
| ESP default | Most ESPs (Klaviyo, Mailchimp) use shared by default | Must request or pay extra |

**Recommendation:** Stay on shared IP until you exceed 500K subscribers or send more than 1M emails per month. The shared safety net from your ESP outweighs the control of a dedicated IP for most senders. [E03]

---

## Reply-Based Warmup Tactics [E06/Throssell]

### Why Replies Beat Whitelisting
- Asking subscribers to whitelist has very low compliance
- A reply is the strongest positive engagement signal to an ISP
- Best time: welcome email when subscriber is warm and engaged

### Tactics to Drive Replies
1. **Bribe with value:** Offer to respond with something they want (a resource, answer, recommendation) in exchange for a reply
2. **Low-friction option:** Offer to send a blank reply if they find it awkward to write something
3. **Ask a genuine question:** What is your biggest challenge with [topic]? (Doubles as content research -- see write-newsletter-content skill's content flywheel)
4. **Quiz/survey via reply:** Ask subscribers to reply with a number (1, 2, or 3) based on their situation
5. **Second chance email:** A "did you get this?" re-send to non-openers 24 hours later (saves approximately 8% of otherwise lost subscribers) [E04 cross-ref]

### Rule: Never Ask Your List to Do Something for Free [E06]
Always bribe subscribers with something more valuable than the effort you are asking for. Do not rely on charity or goodwill. Appeal to self-interest.

---

## Prevention System (Ongoing Monitoring) [Synthesized E02 + E03 + E06]

### Weekly Checks
- [ ] Review open rates by segment -- note any drops exceeding 10%
- [ ] Check Google Postmaster for spam rate, IP reputation, domain reputation
- [ ] Review unsubscribe rate (target: below 0.4%)

### Monthly Checks
- [ ] Run GlockApps inbox placement test
- [ ] Check MX Toolbox for blacklist listings
- [ ] Review bounce rates (target: below 0.5% hard bounces)
- [ ] Verify DNS authentication still passing (SPF/DKIM/DMARC)

### Quarterly Checks
- [ ] Review and clean unengaged subscribers (90-120 day window) -> see segmentation-list-health skill
- [ ] Audit list growth sources for spam trap risk
- [ ] Review double opt-in vs. single opt-in performance
- [ ] Test from a fresh GlockApps seed list

### Annual Review
- [ ] Evaluate shared vs. dedicated IP based on current volume
- [ ] Review ESP contract and deliverability SLAs
- [ ] Benchmark against industry deliverability standards
