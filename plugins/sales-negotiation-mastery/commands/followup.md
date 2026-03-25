---
name: followup
description: Create follow-up sequences, re-engagement plans, pipeline management strategies, and re-offer campaigns for stalled or dead deals
skill: pipeline-followup, appointment-setting
---

Help me follow up with prospects, manage my pipeline, re-engage stalled deals, or build reactivation campaigns.

When the user runs `/followup`, determine which sub-task they need and route accordingly:

## Routing Logic

1. **"Prospect went dark / ghosted"** --> Deploy the Anti-Ghosting Sequence from `pipeline-followup`, then escalate to Voss's "Have you given up?" from `tactical-empathy` if needed.

2. **"Build a follow-up sequence"** --> Use the 8-Touch Follow-Up System from `pipeline-followup`. Customize touch timing and methods to their offer type and prospect profile.

3. **"Re-offer / bring back a dead deal"** --> Use the Re-Offer Technique from `pipeline-followup`. Design the re-offer around their original objection. Load `references/reoffer-techniques.md` for scripts.

4. **"Improve show rates"** --> Use Show Rate Improvement methods from `pipeline-followup` (6 methods). Cross-reference `appointment-setting` for confirmation protocols and triage calls.

5. **"Pipeline management / CRM setup"** --> Use Pipeline Management System from `pipeline-followup`. Load `references/pipeline-management.md` for CRM fields, HotList system, and pipeline math.

6. **"Database reactivation"** --> Use the DR process from `pipeline-followup`. Segment by original objection, match re-offers, and deploy Dean Jackson 9-word email.

7. **"Setter follow-up / booking confirmation"** --> Route to `appointment-setting` for triage calls, confirmation protocols, and speed-to-lead methods.

## Required Context

Before building any follow-up plan, ask:
- What was the prospect's original objection? (If unknown, suggest reviewing call notes)
- How long ago was the last contact?
- What methods have you already tried?
- What is your offer price point? (Determines re-offer options)

## Key Frameworks to Apply

- **8-Touch System** (Alexander) -- varied methods, 14-day sequence
- **Re-Offer Technique** (Gordon) -- new offer designed for their specific objection
- **Content Tagging / Consumption Follow-Up** (Gordon) -- use brand content as hooks
- **Dean Jackson 9-Word Email** (Gordon) -- "Are you still trying to [goal]?"
- **Anti-Ghosting Sequence** (Gordon) -- escalating from "?" to GIFs to nuclear option
- **"Have You Given Up?"** (Voss) -- no-oriented reactivation question
- **Database Reactivation** (Alexander) -- systematic revival of dead list
- **Half-Your-Commission Rule** (Alexander) -- 50% of income should come from pipeline
