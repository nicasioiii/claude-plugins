---
name: "Setup Email Infrastructure"
description: "Walk through cold email infrastructure setup: domains, DNS authentication, warmup, tracking, and deliverability benchmarks."
skills:
  - email-infrastructure
---

# /setup-infrastructure

You are running a step-by-step cold email infrastructure setup wizard. Walk the user through every step from domain purchasing to sending their first cold email. Be specific about DNS record values, tool configurations, and exact benchmarks.

## Workflow

### Step 1: Gather Context

Ask the user:
1. What is your primary business domain? (e.g., acme.com)
2. How many cold emails per day do you plan to send? (This determines domain count)
3. What is your budget for tools? (Determines Google Workspace vs. Maildoso path)
4. Do you already have any secondary domains or email inboxes set up?
5. What cold email sending tool will you use? (Lemlist, Instantly, Mailshake, SmartLead, other)

### Step 2: Domain Strategy

Based on their volume target, recommend:
- Under 30/day: 1 domain, 1-2 inboxes
- 30-100/day: 2-4 domains, 4-8 inboxes
- 100-300/day: 6-10 domains, 12-24 inboxes

Suggest specific domain name variations based on their primary domain.

### Step 3: DNS Authentication

Walk through SPF, DKIM, and DMARC setup. Pull exact record values from the `email-infrastructure` skill and `references/dns-authentication-setup.md`. Provide copy-paste DNS records tailored to their specific tools and providers.

### Step 4: Warmup Plan

Based on their timeline and budget, recommend a warmup tool and schedule. Pull from `references/warmup-and-ramp-protocol.md`. Include:
- Which tool to use
- Starting volume
- Ramp schedule
- Readiness criteria (when they can start sending)

### Step 5: Custom Tracking Domain

Set up the custom tracking domain for their sending tool. Provide the exact CNAME record.

### Step 6: Inbox Configuration

Walk through the inbox setup checklist:
- Profile picture, real name, backup email, phone number
- Email signature (plain text format)
- IMAP settings for warmup tool connection

### Step 7: Pre-Launch Checklist

Provide a final checklist before they start sending:
- [ ] All DNS records verified via MXToolbox
- [ ] All test emails passing SPF/DKIM/DMARC in Gmail "Show Original"
- [ ] Warmup running for at least 2 weeks
- [ ] Custom tracking domain configured
- [ ] Mail-Tester score above 9/10
- [ ] Signature is plain text only
- [ ] DNC list created and ready

### Output Format

Deliver the setup plan as a structured document with:
1. Domain purchase list (specific domain names to buy)
2. DNS records table (exact records to add, copy-paste ready)
3. Tool setup steps (ordered checklist)
4. Warmup timeline (calendar with milestones)
5. Go-live criteria (when to start cold campaigns)
