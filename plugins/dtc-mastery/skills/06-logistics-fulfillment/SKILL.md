---
name: Shipping, Logistics & Fulfillment
description: >
  MANDATORY TRIGGERS: shipping, logistics, fulfillment, 3PL, ocean freight, air freight,
  freight forwarder, customs, Bill of Lading, Amazon MCF, FBA fulfillment, TikTok shipping,
  shipping costs, container shipping, warehouse, returns warehouse, shipping pricing,
  free shipping threshold, express shipping, courier, DHL, FedEx, fulfillment center,
  order timelines, lead time, delivery, dispatch, shipping template, flat rate shipping.
  FOR: Moving products from factory to customer across all platforms -- shipping method
  selection (courier vs air vs ocean), ocean freight step-by-step, freight forwarder
  selection, 3PL comparison, Amazon MCF for TikTok/Shopify, shipping pricing strategy,
  fulfillment sync configuration, and order timeline planning. Synthesizes Jason Wong
  (ocean freight process), Gretta Van Riel (shipping best practices), Matt Clark
  (fulfillment options), and Michelle (TikTok fulfillment setup).
  Do NOT use for: Amazon FBA listing or PPC strategy (use amazon-listing-optimization
  or amazon-ppc-advertising), TikTok Shop account registration (use tiktok-shop-setup),
  supplier negotiation or sourcing (use sourcing-suppliers skill), product pricing
  strategy (use pricing-finance skill).
---

# Shipping, Logistics & Fulfillment

## Quick Navigation
- **Shipping method selection** -> Weight-based decision framework below
- **Ocean freight process** -> Step-by-step below
- **3PL comparison & fulfillment options** -> ref-fulfillment-options.md
- **Amazon MCF for TikTok Shop** -> ref-fulfillment-options.md
- **Shipping pricing strategy** -> Pricing section below

---

## When to Read Reference Files

| User Question Pattern | Load This Reference |
|---|---|
| Which 3PL should I use? ShipBob vs Deliverr vs FBA? | ref-fulfillment-options.md |
| How do I set up Amazon MCF for TikTok Shop orders? | ref-fulfillment-options.md |
| Aftership vs WebBee -- which integration? | ref-fulfillment-options.md |
| What are the sync settings for TikTok fulfillment? | ref-fulfillment-options.md |
| How do I handle returns? | ref-fulfillment-options.md |
| Test order checklist? | ref-fulfillment-options.md |

---

## Cross-References

| Topic | Primary Skill | Go To |
|---|---|---|
| TikTok Shop registration and account setup | tiktok-shop-setup | `skills/tiktok-shop-setup/SKILL.md` |
| Supplier negotiation and first order placement | sourcing-suppliers | `skills/sourcing-suppliers/SKILL.md` |
| Product pricing and unit economics | pricing-finance | `skills/pricing-finance/SKILL.md` |
| Shopify store setup and fulfillment config | shopify-dtc-setup | `skills/shopify-dtc-setup/SKILL.md` |
| Quality control before shipment | quality-control | `skills/quality-control/SKILL.md` |

---

## Shipping Methods Decision Framework (Jason Wong)

Choose shipping method based on weight:

| Weight | Method | Transit (from China) | Relative Cost |
|---|---|---|---|
| Under 50 kg | Express courier (FedEx, DHL, UPS) | ~3 days | Highest |
| 50-500 kg | Air freight | ~10 days | Medium (3-5x ocean) |
| Over 500 kg (1,000+ lbs) | Ocean freight | ~30 days | Lowest |

**Cost comparison (Jason Wong):** The same shipment costing $195 by ocean can cost $1,000 by air -- a 5x price difference.

**Product value also guides choice:**
- Low-value items ($5 USB cable) -> postal service / economy
- High-value items (jewelry, electronics) -> express courier with better insurance

**Freight forwarder tip (Jason Wong):** If your supplier chooses the freight forwarder, they may mark up the price. Find your own freight forwarder in the manufacturing country for better rates.

---

## Ocean Freight -- Complete Step-by-Step (Jason Wong)

### Three Required Documents
1. **Bill of Lading (BL):** Legal certificate of cargo ownership. Needed to pick up delivery at port.
2. **Commercial Invoice:** Declares value and contents.
3. **Packing List:** Itemized contents of shipment.

### Full Process
1. Factory completes production
2. QC inspection passes (do NOT skip)
3. Freight forwarder books container
4. Empty container picked up and delivered to factory
5. Factory loads cargo into container
6. Arrange shipment inside container (proper stacking/securing)
7. Transport loaded container to port
8. Load onto vessel BEFORE cut-off time
9. Customs clearance at origin
10. Vessel sails
11. Arrival notice issued at destination port
12. Pay terminal handling and delivery charges
13. Exchange Bill of Lading for delivery note
14. Import customs clearance (customs broker if forwarder doesn't handle)
15. Truck delivers to final destination (warehouse, 3PL, or your location)

### Critical Details
- **Cut-off time:** Imposed by shipping vessel to maintain schedule. Miss it and your cargo doesn't make the ship -- next departure could be 1-2 weeks later.
- **Container weight:** Same maximum weight limit for both 20-foot and 40-foot containers. Inaccurate weight declarations can cause crane malfunction or vessel safety problems.
- **Forwarder quote requirements:** Shipping date, origin, destination address, cargo dimensions/characteristics. Declare if shipping hazardous materials or items requiring special licenses.
- **Customs broker:** If your freight forwarder doesn't handle customs clearance, find a customs broker near your destination port.

---

## Order Timelines (Matt Clark)

| Phase | Duration |
|---|---|
| Product sourcing + sampling | 3-4 weeks |
| Logo/branding | 1-2 weeks |
| Packaging design/production | 2-3 weeks |
| Bulk order manufacturing | 3-4 weeks |
| Shipping (sea freight) | 3-4 weeks |
| **Total (sequential)** | **12-14 weeks** |
| **Total (parallel processing)** | **8-10 weeks** |

Parallel processing means overlapping branding/packaging design with sampling and starting manufacturing prep while shipping arrangements are made.

---

## Self-Fulfillment Best Practices (Gretta Van Riel)

For early-stage sellers shipping their own orders:
- **Ship every day** in the afternoon -- find your local post office daily cut-off time
- **Speed directly impacts conversion:** Stating delivery takes weeks causes a large percentage of customers not to buy
- **Pre-package all stock** so it's ready, just waiting on shipping labels when orders come in
- **Use a label printer** (recommended: Dymo LabelWriter 4XL)
- **Flat pack where possible**, use lightest materials
- SkinnyMeTea shipped in small flat-packed envelopes, keeping costs down considerably
- **Buy packing materials in bulk** off eBay for cheaper prices
- Use local postal services (USPS, AusPost, Sendle) before upgrading to carriers

---

## Self-Ship vs 3PL vs Amazon FBA (Matt Clark, Jason Wong)

| Method | Best For | Cost Range | Notes |
|---|---|---|---|
| Self-ship | <50 orders/day | Cheapest per unit | Time-consuming; stops scaling you |
| Amazon FBA | Omnichannel (Shopify + Amazon) | ~$5-10/order + storage | Enables Prime badge; MCF for other channels |
| 3PL | $30K+/month revenue | $2-5/unit storage + $3-6/shipment | Scales easily; dedicated support |

### 3PL Volume Minimums (Gretta Van Riel)
- **US/Canada/UK/Australia:** 300-500 units/month minimum
- **Asia-based 3PL:** 100+ units/month (more lenient thresholds)

### When to Switch to 3PL
- Jason Wong: 3PL becomes cost-effective around $30K/month revenue
- Before that threshold, self-ship or Amazon FBA usually more economical
- UPC barcodes required for Amazon/retail: ~$30-$100 per barcode

---

## Shipping Pricing Strategy

### Gretta Van Riel's Approach
- **Free standard shipping** included in product price -- now a standard customer expectation
- **Express shipping:** customer pays premium
- **Alternative:** Free shipping over threshold (e.g., $100+)
- Key insight: Customers will always pay more for a product if shipping is free

### TikTok Shop Shipping Rules (Michelle)
- Flat rate: **keep between $5-$8** -- TikTok restricts shipping charges
- TikTok will NOT allow charging $12-$13 for shipping
- Exclude Hawaii and Alaska from shipping templates
- Even if Amazon MCF generates different price points, TikTok caps the rate

### DTC/Shopify Strategy (Matt Clark)
- Free shipping threshold drives AOV: set threshold at 20-30% above current AOV
- Free standard + paid express is the safest default
- Display shipping policy prominently -- uncertainty kills conversion

---

## TikTok Shop Fulfillment Overview (Michelle)

Three methods for fulfilling TikTok orders through Amazon inventory:

1. **TikTok for Shopify Channel (FREE):** For sellers already using Shopify + Amazon MCF
2. **Aftership for Amazon ($11-39/month):** Free trial available; good support
3. **WebBee (paid, 2-week trial):** Good support; alternative to Aftership

**Critical sync settings and detailed setup** -> See ref-fulfillment-options.md

**Fulfilled by TikTok (FBT):** For high-volume sellers, FBT saves significantly more than Amazon MCF. Availability is seasonal (may close for Q4). Consider once at "pro level" volume.

---

## Instructor Disagreements

### Fulfillment Method Priority
- **Matt Clark:** Favors Amazon FBA for omnichannel sellers -- enables both Amazon Prime and Shopify fulfillment
- **Gretta Van Riel:** Start with self-shipping to understand your operations; switch to 3PL at scale
- **Michelle:** Use Amazon MCF as bridge for TikTok Shop fulfillment; graduate to FBT at high volume
- **RESOLUTION:** Start self-shipping or FBA (depends on whether you sell on Amazon). At $30K/month, evaluate dedicated 3PL. For TikTok Shop, Amazon MCF is the most practical starting point. FBT for high-volume TikTok sellers.

---

## Anti-Patterns
- Shipping inventory before QC inspection passes (Gretta lost $1M+ on SkinnyMeTea)
- Choosing ocean freight for time-sensitive launches (use air for first batch, ocean for reorders)
- Using supplier's freight forwarder without getting competing quotes
- Missing vessel cut-off times due to late QC approval
- Setting TikTok shipping rates above $8 (platform will reject)
- Syncing TikTok orders to Amazon MCF immediately instead of waiting 1 hour for cancellation window
- Skipping test orders after setting up any fulfillment integration
