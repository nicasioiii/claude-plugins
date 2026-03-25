---
name: Funnel Conversion Rate Optimization
description: |
  MANDATORY TRIGGERS: optimize funnel, diagnose funnel not converting, run split tests, improve conversion rate, audit funnel performance, test funnel pages, improve take rates, figure out what is wrong with funnel, CRO, A/B testing, funnel optimization.
  FOR: 5D CRO system (Discover, Design, Develop, Document, Deploy), 9 conversion levers, compound testing methodology, Position/Price/Switch diagnostic framework, diagnostic signals table, 10 proven split tests, minimum data thresholds (30-100 customers), weekly tracking cadence, revenue projection from test wins, testimonial acquisition strategies, and discount retargeting method.
  Do NOT use for: Designing the funnel structure from scratch (use funnel-architecture), writing the sales page or VSL copy (use sales-page-copy or vsl-sales-copy), designing upsell/downsell offers (use upsell-downsell-strategy), or ad creative testing (defer to paid-ads-mastery plugin).
---

# Funnel Conversion Rate Optimization

Diagnose underperforming funnels, identify the highest-leverage improvements, and run structured tests. This skill combines Gusten's 5D CRO system, Katie's Position/Price/Switch framework, and Georgi's funnel economics optimization levers into a unified diagnostic and testing approach.

## Quick Navigation
- **Detailed split test implementations, test prioritization** -> references/cro-playbook.md
- **Design principles for conversions, CTA design, testimonial visuals, mobile vs desktop** -> references/conversion-design.md
- **5D CRO system, 9 levers, Position/Price/Switch** -> See frameworks below

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| How to implement split tests? Test prioritization? Detailed A/B test guidance? | cro-playbook.md |
| Design principles for higher conversions? CTA design? Testimonial layout? Mobile optimization? | conversion-design.md |

---

## THE 5D CRO SYSTEM (GUSTEN)

A structured process for systematic funnel optimization:

| Phase | Activities |
|-------|-----------|
| **Discover** | Identify conversion levers, audit current performance, analyze compound testing opportunities |
| **Design** | Create mockups of test variants in Figma or similar tool |
| **Develop** | Build A/B test containers, set up tracking, establish naming conventions |
| **Document** | Manage tests in a system (ClickUp/Notion), analyze data, check statistical significance |
| **Deploy** | Implement winning variants for 100% of traffic, then move to next test |

---

## NINE CONVERSION LEVERS

When creating test hypotheses, pull from these nine levers:

1. **Social Proof** -- UGC, reviews, testimonials. Creates trust. Add specific testimonials matching your claims throughout the page (not just one section).

2. **Product Discovery** -- Navigation simplification, smart recommendations, "best sellers" badges. Helps them find the right product faster. (Primarily e-commerce.)

3. **Product Detail** -- Key benefits, USP icons, persuasive messaging, improved imagery. Communicate value more clearly.

4. **Price and Value** -- Strategic positioning of the offer stack to improve price-to-value ratio perception. Visual differentiation between packages (more checkmarks on the preferred option).

5. **Usability** -- Reduce friction, cognitive load, unnecessary steps and clicks. Sticky add-to-cart, quick-buy popups, remove unused navigation items.

6. **Average Order Value** -- Order bumps, cross-sells, upsells, post-purchase offers, quantity bundling, "customer favorite" badges. Every $1 increase in AOV compounds across all traffic.

7. **Scarcity & Urgency** -- Countdown timers, limited-time offers, stock alerts. Answers "why should I act NOW?"

8. **Authority & Liking** -- Celebrity endorsements, expert faces, relatable brand messaging. Adding recognized faces to pages has been shown to significantly improve conversion.

9. **Unity** -- Community identity messaging. Using community identity language in cross-sell headlines (e.g., "Other Patriots also bought") can outperform generic headlines.

See references/conversion-design.md for seven design principles that increase conversions, CTA design patterns, testimonial visual formats, and mobile vs desktop optimization guidance.

---

## COMPOUND CONVERSION TESTING

A/B testing is like compound interest -- improvements stack multiplicatively, not additively.

**Example with 50,000 product page views and $105K baseline revenue:**
- +10% add-to-cart improvement alone = +$10,500/month
- +10% ATC + 5% cart + 5% checkout = +21.28% total improvement = +$22K/month
- Add 20% AOV improvement on top = +$47K/month

**Key principle:** Test multiple touchpoints SIMULTANEOUSLY (homepage, product page, cart, checkout) because improvements compound. A 10% lift on one page + 5% lift on another = 15.5% total improvement, not just 15%.

**Test building framework:**
1. Start with **TOUCHPOINT** (homepage, PLP, PDP, cart, checkout, nav, site-wide, post-purchase)
2. Choose **LEVER** to pull (social proof, usability, price/value, etc.)
3. Pick **SEGMENT** (mobile only, desktop, new users, returning users)
4. Decide **ACTION** (add, change, or remove an element)

---

## POSITION / PRICE / SWITCH FRAMEWORK (KATIE)

When a bump, upsell, or funnel step underperforms, follow this three-step diagnostic in order:

### Step 1: POSITION (Rewrite the Copy)
Upload the copy to an LLM. Tell it: "This is an upsell for [product], it's only converting at X% when it should be Y%. Can you identify why?"

Try leading with a result at the top. Katie increased conversion rate by 2% on one upsell just by repositioning the copy.

**Do NOT change the price yet. Do NOT yank the product yet.** Copy is the cheapest, fastest fix.

### Step 2: PRICE (Slight Decrease)
If repositioning does not work, slightly decrease the price.
- $197 -> $147
- $66 -> $55

**Do NOT cut the price in half.** That hurts revenue per customer. Just "release the pressure a little bit."

### Step 3: SWITCH (Replace the Product)
If repositioning AND price decrease do not work, remove the product. If you do not have a replacement, just remove it altogether until you do.

When take rate is dramatically below benchmark (e.g., 1% when target is 5-10%), "the product itself sucks" -- it is not something people want. No amount of copy or pricing will fix a product nobody wants.

---

## DIAGNOSTIC SIGNALS TABLE

| Signal | Diagnosis | Action |
|--------|-----------|--------|
| Take rate within 10% of benchmark | Healthy | Monitor weekly, do not touch |
| Take rate slightly below benchmark | Copy/positioning issue | Rewrite the page copy (Step 1) |
| Take rate dramatically below (e.g., 1% vs 10% target) | Product is wrong | Replace the product (Step 3) |
| Bump under 40% | Copy or price issue | Rewrite bump copy, verify price is $27-$37 |
| AOV under $70 | Urgent problem for ad profitability | Fix immediately using Position/Price/Switch |
| AOV at $70+ | Healthy | Optimize incrementally, do not burn anything down |
| Sales page converting below 1% (cold) | Copy, offer, or traffic mismatch | Test headline, check traffic source alignment |
| Sales page converting 1-3% (cold) | Normal range | Test for incremental improvements |
| High traffic but low add-to-cart | Product detail or value perception issue | Test imagery, benefit copy, price display |
| High add-to-cart but low checkout | Trust or friction issue | Add trust badges, simplify checkout, add payment plans |

---

## DATA REQUIREMENTS

### Minimum Data Before Diagnosing
- **30 customers minimum** before drawing any conclusions about upsell/bump performance
- **Ideal: 100 customers** for reliable data
- Anything less than 30 is noise -- you cannot draw conclusions

**Exception:** If AOV is under $70 with fewer than 100 customers, this is an urgent problem. Fix it at 30 customers.

### Weekly Tracking Cadence
Track all take rates weekly. Put stats into a spreadsheet. Compare against industry benchmarks from this skill. Look for trends, not individual data points.

### Statistical Significance
Do not call a winner too early. For A/B tests, require 95% confidence before deploying the winner to 100% of traffic. Small sample sizes produce misleading results.

---

## TEN SPLIT TESTS TO RUN (GUSTEN)

See `references/cro-playbook.md` for detailed implementation guidance on each test.

1. **Video vs. image** at top of page (also test video placement: top, middle, sidebar)
2. **Headline A vs. Headline B** -- Test different angles
3. **Light mode vs. dark mode** -- Dark for design/crypto/NFT; light for text-heavy pages
4. **Order form placement** -- Popup vs. embedded sidebar vs. separate page
5. **Platform-specific landing pages** -- Different URLs for Facebook, YouTube, Instagram with customized messaging
6. **Short vs. long copy** -- Short for freebies; long for story-driven sales
7. **Price testing** -- Sometimes $37 outperforms $7 (perceived value effect)
8. **Upsell page length** -- Ultra-short ("Wait! Add this for $47. Yes/No") vs. long-form with stack
9. **Payment plans** -- Adding 3x $397 alongside $1,000 one-time
10. **Testimonial placement** -- Above the fold (small) + clustered near CTA (detailed)

---

## DISCOUNT RETARGETING METHOD (GUSTEN)

A strategy that added $100K+/month to one course and $40K+/month to another:

- Run a discount ad ONLY to retargeting audience (warm leads who already know your normal price)
- Photo ad outperformed video for retargeting -- a "$300 OFF" sign is harder to ignore than a video
- Works because audience is already price-anchored at full price
- Keep discount smaller than Black Friday (preserve BF momentum)
- Budget: $30/day on retarget ad (low to avoid exhausting warm audience)
- Monitor FREQUENCY metric: keep at 2-3. Above 5 = wasting money. Above 7-10 = turn off.
- Must have other ads continuously bringing NEW leads into funnel (retarget feed depends on fresh audience)

---

## CRO OPTIMIZATION LEVERS -- PRIORITY ORDER (GEORGI)

When working on funnel economics, optimize in this order:

**Lower the CPA (highest impact):**
- Finding better ads (higher CTR, lower CPM)
- Increasing landing page conversion rate (copy, design, A/B tests)
- Finding alternate traffic sources
- Abandon cart + decline recovery (email, call center, text)

**Increase AOV (second priority):**
- AOV money close in VSL/sales page (push bigger packages)
- Offer bumps at checkout
- Better upsells with higher conversion rates
- Pricing split-tests

**Increase LTV (third priority):**
- Add continuity/subscription
- Reduce churn (gifts, better communications)
- Email list monetization

**Lower COGS (lowest priority, smallest impact):**
- Different fulfillment partners
- Negotiate lower shipping/product rates

---

## CROSS-REFERENCES

- CRO improvements feed back into `funnel-economics` to update revenue projections
- If CRO reveals the offer is wrong -> `offer-stack-design` to redesign
- If copy is the bottleneck -> `sales-page-copy` or `vsl-sales-copy` for rewrite
- If upsells specifically underperform -> `upsell-downsell-strategy` for product redesign
- For ad creative testing -> defer to paid-ads-mastery plugin
- For checkout-specific optimization -> `checkout-optimization`
