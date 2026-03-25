---
name: Pop-Up Form Optimization
description: >
  When to Read: User asks about pop-up form design, offer types, behavior settings,
  mobile vs desktop forms, success page strategy, double opt-in, form split testing,
  or form-to-flow connection.
  Cross-references: ref-newsletter-growth.md for paid/organic growth beyond pop-ups,
  ecom-flows for welcome series triggered by forms.
---

# Pop-Up Form Optimization

## Offer Types Ranked by Conversion Rate (E02 -- Ascending)

| Rank | Offer Type | Best For | Notes |
|---|---|---|---|
| 1 (lowest) | No offer | Extreme brand loyalty (Supreme-type) | Only works with scarcity/exclusivity |
| 2 | Info product (ebook, course, video) | B2B, service, creator | Most brands don't invest enough effort |
| 3 | Discount (fixed amount, e.g., $50 off) | High AOV stores ($150+) | $50 off sounds better than 2.5% off |
| 4 | Discount (percentage, e.g., 10% off) | Low AOV stores | 10% off sounds better than $3 off |
| 5 | Free shipping | International audiences | Works when shipping is common objection |
| 6 | Free item | Any ecommerce | Perceived value >> actual COGS cost. Frame as "bundle upgrade" |
| 7 (highest) | Giveaway | List building at volume | Highest conversion but lowest lead quality. Use double opt-in |

### Discount Code Best Practices (E02)
- Add random characters to codes (e.g., WELCOME10DKWS) to prevent web scraping
- Random characters create exclusivity perception
- Use expiring discount codes (Klaviyo feature) so urgency is real
- Embed code into button/link so it auto-applies at checkout

---

## Behavior Settings (E02 + E03)

### Mobile (80% of traffic for average store)
- **NEVER load immediately** -- increases bounce rate, captures low-quality leads
- Best practice: 20-50% scroll delay OR 6-10 second delay
- Center pop-up preferred over full-screen (less intrusive)

### Desktop
- **NEVER load immediately**
- Best practice: exit intent only
- Desktop leads generally have slightly higher conversion rate

### Other Settings
- **Re-show delay:** 5-14 days after form close (aggressive: 5-7 days)
- Don't show to existing Klaviyo profiles / subscribers
- Exclude cart and checkout URLs
- Separate mobile and desktop forms -- clone and modify behaviors independently
- Target: show to new visitors only (not returning/logged-in users)

---

## Pop-Up Types (E03 -- MuteSix)

| Type | Use Case | Placement |
|---|---|---|
| Welcome pop-up | First-time visitors; capture email + discount | Center preferred |
| UnoBar / banner bar | Site-wide announcement; shows offer + code | Top of page, always-on during promos |
| Exit intent pop-up | Triggered when user moves to leave site | Desktop only |
| Abandoned cart pop-up | Reminder overlay on site | Cart/product pages |
| Countdown timer bars | Drive urgency; 24-hour reset or accurate countdown | Top of page |
| Upsell / cross-sell pop-ups | Post-add-to-cart | Cart page |

---

## Aesthetic Principles (E02)

- Less is more -- same principle as email banners
- Communicate offer in minimum words
- Examples from 9-figure brands:
  - Snow Teeth: "Do you like free stuff?"
  - The Oodie: "$25 off"
  - Magic Spoon: "Win free cereal" (3 words)
- Match pop-up design to brand guidelines
- Use high-resolution product imagery when possible

---

## Success Page Strategy (E02 + E03)

### Option A: Show Discount Code Immediately
- Reduces friction to first purchase
- Subscriber can shop right away
- Works best for low-AOV impulse purchases

### Option B: Direct to Inbox (E02 Recommended)
- Trains subscribers to open emails from day one
- If landing in spam/promotions, instructs them to move to inbox
- Builds better long-term engagement habit
- Works best for high-AOV products and newsletters

---

## Double Opt-In Decision Tree

```
Are you running a giveaway or contest?
  YES -> Turn ON double opt-in (giveaway leads are low quality)
  NO -> Continue

Is your bounce rate above 2%?
  YES -> Turn ON double opt-in
  NO -> Continue

Is your spam rate above 0.1%?
  YES -> Turn ON double opt-in
  NO -> Continue

Are you collecting many fake/disposable emails?
  YES -> Turn ON double opt-in
  NO -> Keep double opt-in OFF (default recommendation)
```

---

## Form Split Testing (E02)

### Testing Methodology
- Name tests by variable type (e.g., "Copy - Headline Variation 2")
- 500-2,000 views before determining winner
- Give at least 5 days for meaningful data
- If results are consistently too close, the variable is too low-impact -- change the offer

### Priority: Test in This Order
1. Offer (discount amount, type)
2. Timing/behavior (scroll depth, delay)
3. Copy (headline, CTA text)
4. Design (colors, layout, images)

---

## Holiday-Specific Pop-Ups (E03)

### BFCM Pop-Up Strategy
- Set up a separate pop-up with the holiday discount
- When someone enters email via BFCM popup, trigger a holiday-specific welcome email
- This captures NEW visitors during peak traffic who would otherwise miss campaign emails
- Pop-up messaging MUST match current email campaign messaging
- Change popup every time the discount tier changes

### Pre-BFCM Capture
- "Give us your email, we'll notify you first when deals drop"
- Proven high-conversion capture strategy
- Creates anticipation and permission for aggressive BFCM sending

---

## Form-to-Flow Connection (Critical Setup)

### The #1 Setup Mistake (E02)
- Form's "list to submit" MUST match the welcome series trigger list in Klaviyo
- If different list selected, welcome series won't fire
- Always verify: form submission list = welcome flow trigger list

### Pop-Up to Klaviyo List Setup
- Connect pop-up to a dedicated Klaviyo list (static list, not segment)
- Pop-up submits to list -> list triggers welcome flow
- For multiple pop-up types (welcome, BFCM, exit intent), use the same main list OR set up separate flows for each

### Traffic Source Segmentation (E03)
- Segment subscribers by acquisition source: Facebook, Google Ads, organic
- Trigger different pop-ups and messaging per traffic source
- Target differently based on how they found the brand
