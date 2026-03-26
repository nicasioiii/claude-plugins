---
name: TikTok Shop Setup Reference
description: >
  Complete 33-step launch sequence with full detail, business registration
  requirements (SS4 letter, EIN), account setup sequence, social account linking,
  ad account connection, fulfillment integration (Aftership/WebBee/Shopify) with
  syncing rules, shipping configuration, customer support setup with templates,
  review importing pipeline (Amazon->Shopify->Yotpo->TikTok), team structure
  and role-based access, operations/support/affiliate daily tasks, outsourcing
  guidelines, Asana workflow templates, and 18 anti-patterns to avoid.
  When to Read: User needs the specific how-to steps for any part of TikTok
  Shop setup, fulfillment configuration details, review importing process,
  or team management structure.
  Cross-references: For GMV Max ads and optimization strategy, see SKILL.md
  above. For creator outreach workflows, see content-creator-strategy.
---

# TikTok Shop Setup -- Complete Reference

## Business Registration Requirements (Michelle)

### Required Documents
1. **SS4 Letter from IRS** -- must show business name, EIN, and mailing address
   - The digital EIN copy IS NOT ENOUGH -- TikTok Shop will reject it
   - Must be the official physical letter the IRS mails
   - If lost, call **(800) 829-4933** to request a copy
2. **Registered business address** -- where business is registered (not beneficial owner's home, unless same)
3. Business must be registered in the US AND operated by a beneficial owner within the US

### Document Format Rule
- Convert all documents to **JPG format** -- system claims PDF/PNG but reads JPGs best

---

## Account Setup Sequence (12 Steps)

1. Complete business registration (SS4 letter, address verification)
2. Create US-based TikTok social media account (mobile, US IP, US SIM)
3. Use same email as TikTok Shop account (different password -- separate login process)
4. Set up as personal account with real birthday (tied to ID verification)
5. Complete identity verification on social account (prompt in TikTok inbox within minutes to 24 hours)
6. Link social account to TikTok Shop (profile > QR code scan from mobile app)
7. Authorize brand content sharing
8. Connect ad account (Marketing > Shop Ads > Create Account for new advertisers)
9. Set up customer support (chat automations, FAQs, chatbot)
10. Configure shipping (warehouse setup, shipping templates)
11. Install fulfillment integration (Aftership, WebBee, or Shopify)
12. **Run a test order** before turning on traffic

---

## Fulfillment Integration Options

| Option | Cost | Best For |
|---|---|---|
| **TikTok for Shopify channel** | Free | Already using Shopify + Amazon MCF integration |
| **Aftership for Amazon** | $11-$39/month (free trial) | No Shopify site |
| **WebBee** | Paid (2-week trial) | No Shopify site |

### Aftership/WebBee Configuration Rules (Critical)

| Setting | Value | Reason |
|---|---|---|
| Auto-link product SKUs | YES | Match products across platforms |
| Auto-update product details/titles | **NO** | Amazon listings are Amazon-specific |
| Sync price | **NO** | TikTok pricing should differ from Amazon |
| Sync inventory | **YES** | Only thing to bring from Amazon |
| Order sync to Amazon | **After 1 hour** | TikTok 60-minute customer cancellation grace period |
| Fulfillment sync shipping method | **Expedited Shipping** | Standard pricing for MCF; meets TikTok 2-day dispatch |
| Cancellation sync | Auto-restock Amazon inventory on cancel | Prevents inventory mismatch |
| Category mapping | **DO NOT map** | Handle manually -- categories do not translate |

### Shopify Integration Setup
1. Apps and Services > App Store > Install "TikTok for Shopify" channel
2. Shop Management > Connect Account (authorize Shopify + TikTok Shop)
3. Verify warehouse information (return + pickup both need data)
4. Map products: sync **inventory ONLY** (not product info, not price)
5. Click "Complete Map"
6. **Run a test order**

[CONTRARIAN] At pro volume, look at Fulfilled by TikTok (FBT) instead -- saves significantly more than Amazon MCF. FBT availability is seasonal (closed during Q4, reopens in January).

---

## Shipping Configuration

### Warehouse Setup
- Navigate: Orders > Shipping Settings
- Set up pickup warehouse AND return warehouse
- If using Amazon MCF: use your home/business address (NOT an Amazon warehouse)

### Shipping Template
- Only need one template for most sellers
- Select standard shipping
- Select all US states EXCEPT Hawaii and Alaska (deselect those)
- Flat rate: $5-$8 (TikTok will not allow $12-$13 shipping charges)

---

## Customer Support Setup

### Setup Checklist
1. **Add team members** via Account Settings > User Management
   - Assign as Customer Service Agent AND Order Fulfillment Specialist
2. **Chat automations:**
   - Notification settings for correct team members
   - FAQ cards (shipping, refund -- TikTok pre-loads common FAQs)
   - Custom FAQs in your brand voice
   - Chat greeting with FAQ card
3. **Enable TikTok AI chatbot:**
   - Activate all day (24/7), not just business hours
   - Leave business hours "open" -- do not restrict
   - Human agent checks during working hours; bot covers the rest
4. **Saved replies:** Create groups in your brand's tone of voice

### Recommended Saved Replies
- **Collab request:** "Thanks for your interest in promoting our products. We offer free samples here on TikTok Shop, simply go to the product you're interested in and request a sample."
- **Negative review:** "We're sorry our {product} didn't meet your expectations. Please contact support so we can try to resolve the issue."

---

## Review Importing Pipeline (Amazon > Shopify > Yotpo > TikTok)

### Why It Exists
TikTok Shop has no direct Amazon review import. A website (Shopify) is required as an intermediary.

### Step 1: Export Amazon Reviews
1. Use Chrome extension (Helium 10 Review Insights)
2. Filter for 4 and 5 star reviews only
3. Export as CSV

### Step 2: Prepare Yotpo CSV
1. Install Yotpo Product Reviews & UGC app on Shopify (not the email marketing one)
2. Open Yotpo > Import Reviews > Provider: "Other" > Download CSV template
3. Import template into Google Sheets

**CSV field rules:**
| Field | Format |
|---|---|
| Date | YYYY-MM-DD (with leading zeros) |
| Shopify Product Handle | End of your Shopify product URL |
| Public Review | `TRUE` (capital letters) |
| Reviewer Email | Generated fake emails (Amazon reviews lack real emails) |
| Images | 1 image URL per review line only; distribute extras to reviews without images |

**Data cleaning:** Remove "Reviewed in the United States on" prefix, reformat dates, generate fake emails (fakeemails.com).

### Step 3: Import to Shopify
1. Export Google Sheet as CSV
2. Yotpo app: Upload File > confirm genuine > Import Reviews
3. Check failure report if import fails (common: date formatting, missing TRUE, wrong handle)

### Step 4: Yotpo to TikTok Shop (Paid)
1. Upgrade to paid Yotpo plan (estimate monthly orders low to reduce cost; monthly billing for cancellation)
2. Contact Yotpo support (open support ticket, not chat)
3. Tell support: "We are on TikTok Shop and would like help to import our Shopify reviews as verified"
4. Processing: ~4 hours; reviews appear on TikTok Shop in up to 3 days

### Critical Matching Requirement
SKU and barcode (UPC/GTIN) must match between Shopify and TikTok Shop. Check TikTok Shop listing: Sales Information > Product Identifier Code + Seller SKU.

### Post-Import
Cancel Yotpo paid subscription before next billing cycle.

---

## Team Structure (Michelle)

### Three Core Roles
| Role | Responsibilities | Access Level |
|---|---|---|
| **Operations Manager** | Daily shop oversight, sales monitoring, inventory, suspension prevention | Main Administrator |
| **Creator Outreach Specialist** | Affiliate research, outreach, sample management | Affiliate Center + Order Fulfillment + Customer Service |
| **Customer Support Agent** | Buyer messages, review responses, support tickets | Customer Service Agent + Order Fulfillment Specialist |

One person can cover multiple roles initially.

### User Management Rules
- Email must NOT be currently associated with another TikTok Shop
- Workaround: Gmail plus-addressing (example+1@gmail.com, example+2@gmail.com)
- Activation email must be accepted within 120 hours (5 days)

### Daily/Weekly Task Matrix

**Operations Manager:** Shop operations check (daily), sales review (daily), orders/shipping (daily), product catalogue (daily), account health (weekly), post/video performance (weekly)

**Customer Support:** Buyer responses/inbox (daily, notified), review requests from buyers (weekly), product rating responses (as needed)

**Affiliate Outreach:** Research and outreach 30-50 creators/day (daily), check affiliate messages (daily), sample request approval (daily), update tracker (daily), post-sample messaging (daily), affiliate reminder outreach (weekly), performance reporting (weekly)

---

## Outsourceable Tasks (Michelle)

- Affiliate outreach: searching, sorting, saving, inviting to Target Collaborations
- Creator validation
- Sample management: filtering, approving, step-by-step communication
- Review requests from affiliates and buyers
- Customer service inbox management
- Shop ads: spark code importing, setup, management, optimization

---

## Anti-Patterns -- 18 Mistakes to Avoid

1. Using digital EIN copy for registration (must be physical SS4 letter)
2. Creating TikTok account outside US without VPN (permanent geo-lock)
3. Having VA access account without US VPN (switches geo-lock)
4. Making up birthday during account creation (ID verification fails)
5. Syncing product info/prices from Amazon to TikTok (keep separate)
6. Mapping categories from Amazon to TikTok (handle manually)
7. Running GMV Max without sufficient converting content (waste of budget)
8. Running all products in one GMV Max campaign (underperformers drag down)
9. Ignoring unreplied buyer messages (damages brand rating, can lose account)
10. Setting specific business hours for chatbot (leave 24/7)
11. Charging $12-13 for shipping (platform caps at $5-8)
12. Trying Yotpo review import on free plan (only works on paid)
13. Not matching SKUs between Shopify and TikTok Shop (breaks review import)
14. Including brand name in listing titles automatically (may hurt discovery)
15. Using Shopify integration for product listings (use for fulfillment only)
16. Syncing orders to Amazon immediately (wait 1 hour for cancellation window)
17. Not requesting/extending spark codes from converting creators (lost amplification)
18. Using same email for VA across multiple TikTok Shops (blocked by platform)

---

## Key Benchmarks

| Metric | Value |
|---|---|
| Ideal product price point | Under $50 |
| TikTokability minimum score | 3 out of 5 keys |
| Daily creator outreach (standard) | 30-50 creators |
| Daily creator outreach (aggressive) | 1,000-2,500 creators |
| Content completion conversion rate | ~10% of outreach |
| Shipping flat rate range | $5-$8 |
| Order sync delay (Amazon MCF) | 1 hour |
| Aftership pricing | $11-$39/month |
| User invitation acceptance window | 120 hours (5 days) |
| Review display time on TikTok Shop | Up to 3 days |
| Yotpo processing time | ~4 hours |
| Target GMV Max ROI | ~5x |
| Max products per GMV Max campaign | 1 (recommended) |
| Free shipping conversion lift | 16% |
| IRS phone for SS4 replacement | (800) 829-4933 |
