---
name: Diagnose Campaign
description: Quick diagnostic for a specific metric issue. User reports one underperforming metric; provides targeted root cause analysis and fix. Faster than full campaign audit. Activates campaign-ops skill.
---

# Quick Campaign Diagnostic

## Step 1: Identify the Symptom

Ask the user:

1. **What metric is underperforming?** (e.g., "low open rate," "no replies," "calls not converting," "meetings not showing up")
2. **What is the current number?** (e.g., "12% open rate," "0.5% reply rate," "3% connect rate")
3. **What channel?** (email, phone, LinkedIn, DM)
4. **How long at this level?** (just started, was better before, always been this way)

---

## Step 2: Run Targeted Diagnostic

**Load skill:** `campaign-ops` > references/benchmarks-and-diagnostics.md

Based on the specific symptom reported, run ONLY the relevant diagnostic tree.

### Quick Diagnostic Responses

**"My open rate is low"**
-> Check: subject line length (>5 words?), capitalization, spam words in copy, deliverability (SPF/DKIM/DMARC), warmup status, send timing, domain reputation
-> Most likely fix: Rewrite subject line (5 words, internal camouflage, no gimmicks)
-> If subject lines are good: Deliverability problem -> `/deliverability-audit`

**"My reply rate is low"**
-> Check: email length (>150 words?), problem language vs. buzzwords, CTA type (asking for time = -44%), personalization quality, links/images in email, case study present
-> Most likely fix: Switch to interest-based CTA, add problem language, remove links
-> If copy is good: Wrong audience -> check list quality with `list-building`

**"I'm getting replies but no meetings"**
-> Check: response speed (minutes, not hours), follow-up count (need 5+), calendar link friction, CTA clarity in reply
-> Most likely fix: Reply faster, simplify booking, build proper sequence

**"My bounce rate is high"**
-> Check: email verification (did you run NeverBounce?), list age (>30 days old?), targeting job changers?
-> Fix: Verify all emails before sending, rebuild stale segments

**"I'm getting spam complaints"**
-> Check: unsubscribe link present? Content has spam words? Sending from unwarmed domain? Volume too high too fast?
-> Fix: PAUSE immediately, audit with `email-infrastructure` skill

**"My connect rate on calls is low"**
-> Check: mobile vs. landline numbers, calling times (Wed-Thu 8-10 AM / 4-5 PM?), phone number spam-tagged?
-> Fix: Prioritize mobile numbers, register at freecallerregistry.com, rotate numbers

**"I'm connecting but not booking meetings"**
-> Check: opener type (canned vs. context-first?), problem proposition specificity (Hairy Lollipop Test), objection handling method
-> Fix: Switch to context-first opener, rewrite problem proposition -> `cold-calling`

**"Meetings are no-showing"**
-> Check: day-before email sent? Day-of text sent? Booking distance (>5 days?), no-show protocol (2/5/8 min)?
-> Fix: Add confirmation sequence, text day-of, implement no-show escalation

**"LinkedIn acceptance rate is low"**
-> Check: sending with notes? (always send empty), profile optimized? Content active? Sending to right audience? Right time zone?
-> Fix: Remove connection notes, optimize profile, post 2+/week -> `linkedin-outreach`

**"LinkedIn DMs not getting replies"**
-> Check: using exclamation points? Too enthusiastic? Not answering WIIFM? Single thread only? Asking for call too early?
-> Fix: Restrained compliments (4-6/10), multi-thread, throw rope -> `linkedin-outreach`

---

## Step 3: Deliver Quick Fix

Output a focused response:

1. **Diagnosis:** The root cause in one sentence
2. **Benchmark:** What the metric should be
3. **Fix:** The specific action to take (1-3 steps maximum)
4. **Skill to use:** Where to get detailed guidance
5. **Timeline:** When to expect improvement (e.g., "test 100 emails with new subject lines, measure after 3 days")

Keep it tight. This is a quick diagnostic, not a full audit. If the user needs a comprehensive analysis, direct them to `/campaign-audit`.
