---
name: Fulfillment Options & Integration Guide
description: >
  3PL comparison (ShipBob, Deliverr, Shopify Fulfillment Network, Amazon FBA),
  Amazon MCF configuration for TikTok Shop (critical sync settings), Aftership
  vs WebBee comparison, shipping cost optimization tactics, international shipping,
  returns warehouse setup, and test order verification checklist.
---

# Fulfillment Options & Integration Guide

---

## 3PL Comparison

| Provider | Best For | Pricing Model | Key Advantage | Key Limitation |
|---|---|---|---|---|
| **Amazon FBA** | Omnichannel + Prime badge | Per-unit pick/pack + monthly storage | Prime eligibility; MCF for off-Amazon | Long-term storage fees; commingling risk |
| **ShipBob** | DTC brands, Shopify-first | Pick/pack + storage + shipping | Strong Shopify integration; 2-day shipping network | Higher per-unit cost for low volume |
| **Deliverr** | Fast shipping badge on marketplaces | Per-unit fulfillment fee | Walmart 2-day, eBay Fast 'N Free badges | Acquired by Shopify; less Amazon focus |
| **Shopify Fulfillment Network** | Shopify merchants | Integrated pricing | Native Shopify integration | Limited availability; newer service |

### Decision Framework
- Selling on Amazon -> **Amazon FBA** (enables Prime; use MCF for other channels)
- Shopify-only DTC brand -> **ShipBob** or **Shopify Fulfillment Network**
- Multi-marketplace (Walmart, eBay, Amazon) -> **Deliverr** or **Amazon FBA**
- Below 300 units/month -> Self-ship until you hit volume thresholds

---

## Amazon MCF for TikTok Shop -- Complete Setup (Michelle)

### Three Integration Methods

**Method 1: TikTok for Shopify Channel (FREE)**
- Requires existing Shopify store using Amazon MCF
- Install TikTok for Shopify channel app
- Complete setup/integration between TikTok and Shopify
- Best option if Shopify + Amazon MCF integration already exists

**Method 2: Aftership for Amazon**
- Pricing: $11/month (essentials) or $39/month
- Free trial available
- Good support and responsive team
- Essentials plan sufficient for most sellers

**Method 3: WebBee**
- Two-week free trial
- Good support and responsive team
- Alternative if Aftership doesn't fit

### Critical Sync Configuration (Aftership/WebBee)

**Channel Syncing Rules:**
| Setting | Configuration | Why |
|---|---|---|
| Auto link product SKUs | ENABLE | Matches products between platforms |
| Auto update product details from Amazon | **DISABLE** | Amazon listing changes are Amazon-specific; should not overwrite TikTok listings |
| Sync price from Amazon | **DISABLE** | Pricing strategy differs per platform |
| Sync inventory from Amazon | **ENABLE** | This is the only thing you want synced |

**Order Syncing:**
- Sync to Amazon after **ONE HOUR** delay
- TikTok has a 60-minute grace period where customers can cancel
- Syncing immediately means you fulfill orders that get canceled

**Fulfillment Sync:**
- Select **EXPEDITED** shipping -- expedited now comes standard for Amazon MCF with better pricing
- Expedited meets TikTok's 2-day dispatch rate requirements
- Don't worry about carrier name matching (it will show Amazon)

**Cancellation Sync:**
- Enable auto restock of Amazon inventory if TikTok order gets canceled

**Category Mapping:**
- Do **NOT** map categories from Amazon to TikTok Shop
- Handle category assignment manually in TikTok

**Product Mapping:**
- SKU in TikTok listing MUST match Amazon SKU for sync to work
- Verify SKU matching before going live

### Shopify Integration Specifics
- Only sync **inventory** -- do NOT sync product info or price
- Syncing can take time; be patient
- Ensure both return warehouse and pickup warehouse info is saved before proceeding

---

## Aftership vs WebBee Comparison

| Feature | Aftership | WebBee |
|---|---|---|
| Pricing | $11/mo (essentials) or $39/mo | Paid (varies) |
| Free trial | Yes | 2-week trial |
| Support quality | Good, responsive | Good, responsive |
| Setup complexity | Moderate | Moderate |
| Recommended for | Most sellers | Alternative option |

**Michelle's recommendation:** Either works well. Aftership essentials plan is sufficient for most sellers. Choose based on pricing and trial experience.

---

## Shipping Cost Optimization Tactics (Jason Wong)

1. **Lighten packaging:** Reduce weight of primary packaging (what customer opens) and secondary packaging (box holding units together)
2. **Choose sea freight over air** for non-urgent reorders ($195 vs $1,000 for same shipment)
3. **Negotiate pick-and-pack fees** with your 3PL -- get competing quotes for leverage
4. **Get your own freight forwarder** rather than using supplier's (avoids markup)
5. **Calculate duty codes correctly:** Most freight forwarders use wrong HTS codes. One seller saved $275,000 by finding the correct code. Use tarifftaminator.com for verification.
6. **Flat pack products where possible** to reduce dimensional weight charges
7. **Buy packing materials in bulk** (eBay, Alibaba) rather than retail

---

## International Shipping Considerations

- **Incoterms matter:** FOB (Free On Board) = you pay from port. CIF (Cost, Insurance, Freight) = supplier covers to destination port
- **FOB is more common** for experienced importers (gives you control over shipping)
- **Import duties:** Always calculate duty rate BEFORE launching a product -- affects true unit economics
- **Check for:** FDA surveillance, countervailing duties, anti-dumping duties before product selection
- **Protect import records:** Competitors can look up your Bill of Lading records. Options: ghost entity LLC, use air freight for sensitive shipments (no public BL)

---

## Returns Warehouse Setup

### TikTok Shop (Michelle)
- Set up both **pickup warehouse** and **return warehouse** addresses
- If using Amazon MCF: use your home/business address (NOT Amazon warehouse address)
- Return warehouse: either business address or home address

### General Returns Best Practices
- Include prepaid return label in shipment (improves customer experience)
- Track return rate by product -- high return rate signals product/listing problem
- Consider donation tax deduction for returned/expired inventory (Kevin King strategy)
- Returns can be resold as "open box" on secondary channels

---

## Test Order Verification Checklist (Michelle)

Run this BEFORE turning on any traffic-driving activities:

1. [ ] Place a test order on TikTok Shop using a real payment method
2. [ ] Verify order appears in TikTok Shop seller center
3. [ ] Confirm order syncs to Amazon (after 1-hour delay) or your fulfillment provider
4. [ ] Verify Amazon generates a corresponding MCF order
5. [ ] Check that tracking number populates back to TikTok Shop
6. [ ] Confirm customer receives shipping notification
7. [ ] Verify delivery status updates in TikTok Shop
8. [ ] Test a cancellation within 60-minute window (should auto-restock)
9. [ ] For Shopify integration: verify inventory levels sync correctly
10. [ ] Document any issues and resolve before launching marketing

---

## TikTok Shipping Template Setup (Michelle)

1. Generally only need ONE shipping template
2. Select **standard shipping**
3. Select ALL US states **EXCEPT Hawaii and Alaska** (deselect those two)
4. Set flat rate between **$5-$8**
5. Choose shipping mode:
   - **TikTok Shipping:** For 3PL or self-fulfillment
   - **Seller Shipping:** For Amazon MCF fulfillment (must create template first)
6. Set up warehouse addresses before configuring templates

### Two Shipping Modes
| Mode | Use When | How It Works |
|---|---|---|
| TikTok Shipping | Using 3PL or shipping yourself | Default TikTok shipping flow |
| Seller Shipping | Using Amazon MCF (via Aftership/WebBee/Shopify) | Must create shipping templates first |
