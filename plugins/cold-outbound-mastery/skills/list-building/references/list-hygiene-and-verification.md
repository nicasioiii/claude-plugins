---
name: "List Hygiene & Verification"
description: "NeverBounce workflows, email verification, bounce rate benchmarks, DNC list management, form spam prevention, and outsourcing QA via Upwork."
---

# List Hygiene & Verification

## Email Verification with NeverBounce

### Full Verification Workflow

**Step 1: Prepare your list**
- Export your prospect list as CSV
- Include columns: email, first name, last name, company (at minimum)
- Remove obvious duplicates before upload

**Step 2: Upload and verify**
1. Go to NeverBounce
2. Upload CSV
3. Wait for verification (typically minutes for lists under 10K)

**Step 3: Interpret results**

NeverBounce categorizes every email into:
| Category | Meaning | Action |
|----------|---------|--------|
| Valid | Confirmed deliverable | Keep -- safe to email |
| Invalid | Confirmed undeliverable | Remove immediately |
| Disposable | Temporary/throwaway email | Remove -- these convert to bounces |
| Unverifiable | Cannot confirm either way | Keep cautiously -- monitor bounces |
| Unknown | Insufficient data | Keep cautiously -- monitor bounces |

**Step 4: Process results**
1. Download the "Undeliverable" results (disposable + invalid)
2. Import that list back into your CRM/ESP with a tag like "invalid-neverbounce-2026"
3. Before deleting: check if any are past customers (you may want to keep records)
4. Check activity of flagged contacts -- if 0-1 email opens over their lifetime, safe to remove
5. Remove from all active campaign lists

### Cost and Frequency

- **Cost:** ~$76 per 9,500 records
- **Frequency:** Run cleaning at least quarterly for actively growing lists
- Monthly for aggressively growing lists (high inbound volume)
- Before every major campaign launch (especially after list has been dormant)

### Benchmark Data

- Orzechowski's list scored 96.6% valid -- very clean
- If you are below 90% valid, your list building sources need investigation
- Even 2-3% invalid = you are paying for dead weight that hurts your deliverability score

### Common Reasons for Invalid Emails

- Misspellings (gmail.cod instead of gmail.com)
- Apple private relay dummy emails (random@privaterelay.appleid.com)
- Abandoned/cancelled service email addresses
- ISP-converted spam traps (old dormant addresses turned into traps)
- Employees who left the company (work email deactivated)
- Job changers (frequent in tech -- target audience changes roles, email becomes invalid)

---

## Bounce Rate Management

### Target Benchmarks

| Level | Bounce Rate | Status | Action Required |
|-------|------------|--------|-----------------|
| Healthy | Under 2% | Green | Maintain current practices |
| Caution | 2-3% | Yellow | Clean list, investigate sources |
| Danger | 3-5% | Orange | Pause campaigns, full list clean |
| Critical | Above 5% | Red | Stop all sends, nuclear list cleaning |

### Reducing Bounce Rates

1. **Verify before sending:** Run every new list through NeverBounce before first send
2. **Real-time verification:** Some tools (UpLead, Seamless) verify at the point of export
3. **Monitor per-campaign bounces:** Track bounce rate for every campaign separately
4. **Remove hard bounces immediately:** Any email that hard bounces once should be removed permanently
5. **Investigate soft bounces:** Retry once, then remove if it soft bounces again

### Source Quality Tracking

Track bounce rates by lead source to identify bad data providers:

| Source | Acceptable Bounce Rate |
|--------|----------------------|
| UpLead (verified export) | Under 1% |
| Apollo.io | 1-3% |
| Manual research (LinkedIn + hunter.io) | Under 2% |
| Upwork freelancers | Under 3% (with QA process) |
| Purchased lists | 5-15% (this is why you never use them on primary domain) |

If a source consistently produces high bounce rates, stop using it or implement stricter verification.

---

## DNC (Do Not Contact) List Management

### Building Your DNC List

Your DNC list must include everyone who should NOT receive outreach:

1. **Unsubscribes:** Anyone who clicked unsubscribe in any campaign
2. **Spam complaints:** Anyone who reported your email as spam
3. **Manual removal requests:** Anyone who replied asking to be removed
4. **GDPR deletion requests:** Anyone who exercised their right to be forgotten
5. **Existing customers:** Current clients (unless you have a separate upsell motion)
6. **Do-Not-Call registry contacts:** If cold calling (US: telemarketing.donotcall.gov)
7. **Competitors:** Companies that are competitors, not prospects

### Enforcement Protocol

- Cross-reference DNC list before EVERY campaign send
- Automate DNC checking in your sending tool if possible
- If using multiple tools (Lemlist + Instantly + manual), sync DNC across all
- Continuing to email unsubscribed people 4-5 times triggers phishing/spam reports -- this destroys deliverability permanently

### DNC List Format

Maintain a master spreadsheet or CRM tag with:
- Email address
- Date added to DNC
- Reason (unsubscribe, spam complaint, GDPR request, manual)
- Source campaign (which email triggered the removal)

---

## Form Spam Prevention (For Inbound Lists)

### Honeypot Fields

**What it is:** A hidden form field invisible to human visitors but visible to bots. If the field contains any value, the submission is rejected.

**How to implement:**
- Add a text field to your form
- Hide it with CSS (`display: none` or `position: absolute; left: -9999px`)
- Label it something bots would fill (e.g., "website" or "url")
- Server-side: reject any submission where this field has a value

**Elementor:** Form settings > add field > set to hidden
**Gravity Forms:** Settings > enable anti-spam honeypot checkbox

### reCAPTCHA v3 (Invisible)

**What it is:** Score-based bot detection with zero user friction. No checkbox, no image puzzles.

**Configuration:**
- Score threshold: **0.5 is comfortable** -- higher risks losing real opt-ins
- Most spam bots score below 0.3
- Most humans score above 0.7

**Setup:**
- **Elementor:** Settings > Integrations > paste reCAPTCHA keys > add reCAPTCHA v3 field to form
- **Gravity Forms:** Settings > paste reCAPTCHA keys (invisible v2) > add reCAPTCHA field

### Double Opt-In

- **Not recommended as default** -- you lose too many opt-ins (significant conversion drop)
- Save as an **escalated tactic** for extreme deliverability situations
- Use when: your list quality is severely compromised, you are receiving spam trap hits, or you need to rebuild reputation from scratch

### Best Practice: Layer Defenses

Use BOTH honeypot AND reCAPTCHA on every form. This catches:
- Simple bots (honeypot catches most)
- Sophisticated bots (reCAPTCHA catches the rest)
- Manual spam (harder to prevent, but volume is low)

---

## Outsourcing QA Process (Upwork Lead Gen)

### Quality Check Steps for Outsourced Leads

When receiving leads from Upwork freelancers:

1. **Spot-check companies (5-10 random):**
   - Google the company name -- is it real? Still operating?
   - Check their website -- right industry?
   - Verify revenue/size matches your criteria

2. **Revenue/size validation:**
   - Ensure no companies outside your target range (e.g., no $31B companies if targeting $5-150M)
   - Check employee count as a proxy if revenue data is unavailable

3. **Email verification:**
   - Run the entire batch through NeverBounce
   - Target: under 3% bounce rate
   - If above 5%: reject the batch, provide feedback to freelancer

4. **Deliverability test:**
   - Send 20 test emails from the batch
   - Check inbox placement across Gmail, Outlook, Yahoo
   - If multiple land in spam: investigate the email addresses more closely

5. **Duplicate check:**
   - Cross-reference against your existing CRM/list
   - Cross-reference against your DNC list
   - Remove any overlaps

### Freelancer Performance Standards

| Metric | Acceptable | Reject & Retrain | Fire |
|--------|-----------|------------------|------|
| Bounce rate | Under 3% | 3-5% | Above 5% |
| Revenue match | 95%+ correct | 85-95% correct | Below 85% |
| Data completeness | All required fields | Missing 1-2 fields | Missing 3+ fields |
| Delivery time | On time | 1 day late | 2+ days late |
| Duplicates | Under 5% | 5-10% | Above 10% |

Fire immediately if: data has errors on first delivery, companies are wrong size, or cannot deliver on time. Keep the best performer for ongoing work.
