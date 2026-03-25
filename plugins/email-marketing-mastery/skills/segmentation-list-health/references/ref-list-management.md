---
name: List Management & Health Protocols
description: >
  When to Read: User asks about list cleanup triggers, impact on deliverability and billing,
  predictive analytics for churn, LTV-based upselling, negative segments to monitor,
  or when/how to remove subscribers.
  Cross-references: ref-segmentation-framework.md for segment definitions,
  fix-deliverability for authentication and warm-up protocols.
---

# List Management & Health Protocols

## List Cleanup Triggers (E03 + E02)

### When to Clean
- Open rates below 15-20% (15% is borderline; below 15% is definitely time)
- Seen as low as 2-5% -- "by then you definitely need to do a list cleanup"
- Deliverability declining across multiple campaigns
- Spam rate approaching 0.2% (Google danger zone)
- Unsubscribe rate consistently above 0.4%

### Impact of List Cleanup
- **Deliverability improvement:** Removing dead weight improves sender reputation
- **Billing optimization:** Klaviyo charges by contact count. Removing unengaged contacts directly reduces costs
- **Metric accuracy:** Inflated list size masks true engagement rates
- **Sender reputation:** ISPs evaluate engagement ratios. Dead contacts drag down ratios

---

## List Cleanup Protocol

### Step 1: Identify Candidates
Use the Chronic Unengaged segment definition:
- Not opened/clicked in last 180 days
- Never visited site
- Never purchased
- Not in any active flow

### Step 2: Last Chance (Sunset Flow)
Before removing, run through sunset unengaged flow (2 emails):
- Email 1: Goodbye + offer incentive
- Email 2: Offer urgency + unsubscribe option
- If no engagement after both: proceed to removal

### Step 3: Suppress or Remove
- **Suppress:** Mark as unengaged, exclude from all campaigns and flows. Keep profile for historical data
- **Remove:** Delete from Klaviyo entirely. Reduces billing immediately
- **Recommendation:** Suppress first. Delete in batches if cost reduction is needed

### Step 4: Monitor Results
- Open rates should increase within 1-2 campaign cycles
- If no improvement: deliverability issue is deeper than list health (check authentication, IP reputation)

---

## Klaviyo Billing Optimization

### How Klaviyo Billing Works
- You pay for total active contacts (profiles not suppressed)
- Unengaged contacts who will never buy still count toward your bill
- Proper list hygiene directly reduces monthly ESP cost

### Cost-Saving Actions
1. Suppress chronic unengaged (180-day no activity, no purchase)
2. Remove hard bounces immediately
3. Suppress spam complainers
4. Remove profiles with no email address
5. Suppress profiles that have unsubscribed (Klaviyo handles this automatically)

---

## Predictive Analytics (E03 -- MuteSix)

### Churn Prevention (Subscription-Based)
- Know your average churn point (e.g., after 2-3 months)
- Set up triggered email BEFORE the churn window
- Offer: free gift, discount, or other incentive
- Also applicable to non-subscription ecommerce for re-engagement
- Timing is critical: too early wastes the offer, too late loses the customer

### Lifetime Value (LTV) Upselling
- If average LTV = $100, create campaigns to push LTV to $150 with add-on products
- Example: water filter purchased -> send filter replacement reminder at 3-6 months
- Use LTV data to segment and target the right add-on product
- High-LTV customers get different (better) offers than average customers

---

## Negative Segments to Monitor (E03)

### Critical Watchlist

| Segment | Threshold | Action |
|---|---|---|
| Unsubscribes | Track rate per campaign | >0.4% per send = reduce frequency or tighten segment |
| Hard bounces | Track and remove immediately | Any hard bounce = remove. Sending to bounced = reputation damage |
| Spam complainers | Track and suppress | >0.2% spam rate = Google danger zone. Suppress immediately |
| Fake/disposable emails | Monitor for patterns | Enable double opt-in on giveaway forms |

### Unsubscribe Rate Context
- Some unsubscribes are healthy (self-cleaning)
- Sudden spike = something wrong (wrong segment, too aggressive, irrelevant content)
- Gradual increase = frequency too high for audience tolerance
- Klaviyo data: ~50% decrease in unsubscribe rate when using segmentation properly

---

## List Health Monitoring Schedule

### Weekly
- Check spam rate across recent campaigns (<0.2%)
- Check unsubscribe rate across recent campaigns (<0.4%)
- Review hard bounce count and suppress

### Monthly
- Review engaged segment size vs total list size (healthy: 40-70% engaged)
- Review unengaged segment growth rate
- Check Klaviyo billing tier and cost per contact

### Quarterly
- Run full sunset flow for newly unengaged contacts
- Consider list cleanup for chronic unengaged
- Review segment definitions against current business metrics
- Update VIP thresholds if AOV or order frequency has changed

### Annually
- Full list audit before BFCM (September/October)
- Remove profiles that have been suppressed for 12+ months with zero activity
- Review and update all segment logic gates

---

## Segmentation Impact on Revenue (E02)

### The Diminishing Returns Math
- 1 email/week to broad segment = $2K per email
- 2 emails/week to same segment = $1,500 per email but $3K total
- As long as total revenue increases AND open rates stay above 20%, add campaigns

### Microlist Premium
- Hyper-targeted microlists: 20%+ conversion rates, 70% open rates
- Use for: case study screenshots, VIP promotions, geo-targeted campaigns
- This approach enables sending 4+ campaigns/week without hurting engagement

### The 50% Rule
- Proper segmentation reduces unsubscribe rate by approximately 50% (Klaviyo data)
- This means you can safely double frequency if segmentation is tight
- Frequency + segmentation = total revenue growth without deliverability damage

---

## Annual List Audit Checklist (E03 -- MuteSix)

### Dashboard Review
- [ ] Email as % of total revenue (target: 20-25%)
- [ ] Flows vs. campaigns revenue split (healthy = roughly even)
- [ ] Campaign send frequency and consistency

### Automation Audit
- [ ] Welcome series: trigger, flow filter, # of emails, urgency in final email, A/B testing
- [ ] Abandoned cart: trigger, flow filter, timing (2 hours first email), expiring discount codes, cart value split
- [ ] Browse abandon: trigger rules, flow filter (30 days), frequency
- [ ] Post-purchase: conditional split (new vs. repeat), smart sending OFF
- [ ] Replenishment: trigger timing, dynamic product pull, subscription CTA
- [ ] VIP flow: trigger threshold, offer generosity
- [ ] Smart sending: ON for campaigns and browse abandon, OFF for post-purchase and replenishment

### Segmentation Audit
- [ ] Engaged segment built (180-day open/click/purchase/active)
- [ ] Unengaged segment built
- [ ] VIP segment built
- [ ] Recent purchaser exclusion segment
- [ ] Traffic source segments

### Technical Audit
- [ ] UTM tracking enabled (settings > UTM parameters)
- [ ] SPF and DKIM authenticated
- [ ] Google Postmaster set up
- [ ] Default fallback tags for personalization (first name)
- [ ] Discount codes embedded in buttons (auto-apply at checkout)

---

## BFCM Segment Strategy (E03 -- MuteSix)

### BFCM Benchmark Data (Klaviyo)
- 48% of BFCM sales came from customers active between Q1 prior year and Q3 current year
- 70% of first-time purchasers during BFCM did not buy again -- huge retention opportunity
- Customers who clicked an email prior to Q4 had 17% higher AOV
- 89% of BFCM sales came from customers who had opened an email
- Brands faced 25% higher acquisition costs during BFCM

### Pre-BFCM Segment Preparation (Start September-October)
- Test segmentation and cadence: which segments tolerate multiple emails per day?
- Check ESP plan limits (send volume, traffic caps on popup tools)
- Match pop-up messaging to current campaign messaging (update popup every time discount changes)
- Align messaging across ALL channels (email, Facebook ads, Google ads, site banners)

### Critical BFCM Segment Tactics
- **Exclude purchasers from subsequent sends** so someone who bought at 15% off never sees a 20% offer
- **Do not worry about over-sending during BFCM** -- unsubscribe rate and spam complaints are less of a concern during peak season
- **BFCM-specific popup segment:** capture new visitors with "Give us your email, we'll notify you first when deals drop"
- **Triggered flows for each popup:** repurpose BFCM campaign emails as triggered welcome emails for new popup subscribers
- **Post-BFCM retention:** 70% of BFCM first-time buyers never purchase again -- target them with strong post-purchase flows
