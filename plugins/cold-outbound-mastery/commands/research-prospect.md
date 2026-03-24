---
name: Research Prospect
description: Research a specific prospect or account to build outreach angles. Activates prospect-research skill. Outputs trigger analysis, messaging angles, and recommended approach by channel.
---

# Research Prospect Wizard

## Step 1: Gather Context

Ask the user:

1. **Prospect/Account:** Company name and (optionally) specific contact name/title
2. **Your offer:** What do you sell? One sentence.
3. **Your ICP:** Who is your ideal buyer? (title, company size, industry)
4. **Case studies:** Do you have a relevant case study for this prospect's industry/size? If yes, one sentence.
5. **Channel:** Which channel(s) are you planning to use? (cold email, cold call, LinkedIn DM, Instagram DM, multi-channel)
6. **Research already done:** Have you found anything yet? (LinkedIn profile, recent news, etc.)

---

## Step 2: Build the Messaging Matrix

**Load skill:** `prospect-research` > references/messaging-matrix.md

Based on the prospect's role and company, fill in the messaging matrix:

| Dimension | Your Analysis |
|---|---|
| **Priorities** | What is likely most important to this person given their role? |
| **Current Solutions** | How are they probably solving this today? |
| **Problems** | What challenges do they likely face with current approach? |
| **Aspirations** | What do they ultimately want to achieve? |

Use the 4 Questions to Write Painfully Triggering Messages:
1. What is the crappy job if you invert the user's solution?
2. So what? What does that mean for their business?
3. Why do they have that problem? What observable signal would reveal this?
4. How do you prevent the so-what?

---

## Step 3: Identify Triggers

**Load skill:** `prospect-research` > references/trigger-research-workflows.md

Run through the trigger hierarchy using available information:

### Hard Triggers (check first)
- [ ] Recent funding?
- [ ] New executive hire in relevant department?
- [ ] Product launch or expansion?
- [ ] Job postings for roles your product supports?
- [ ] Strategic initiative announcements?

### Soft Triggers (check second)
- [ ] Industry trends affecting them?
- [ ] Company size/stage pattern match?
- [ ] Competitor moves?

### Activity-Based Triggers (if in pipeline)
- [ ] Email opens?
- [ ] Website visits?
- [ ] LinkedIn engagement?

Apply the First-Best Principle: once you find a strong trigger, stop and build the angle.

---

## Step 4: Determine Account Tier

Based on triggers found:

| Tier | Criteria | Recommended Effort |
|---|---|---|
| **A** | Hard trigger found | Full personalization, multichannel, extra call dials |
| **B** | Soft trigger found | Personalized emails, standard sequence |
| **C** | ICP fit, no specific trigger | Templated angles, pervasive problems |

---

## Step 5: Build Channel-Specific Angles

### For Cold Email
Output:
- Recommended first line angle (personalization leading)
- Problem statement (using messaging matrix)
- Value/social proof line
- CTA suggestion (interest-based, never ask for time)
- Subject line options (5 words or less, internal camouflage)

### For Cold Call
Output:
- Opener context (for tailored permission or heard-the-name)
- Problem proposition (using Hairy Lollipop Test -- is it visual enough?)
- One-sentence solution
- Interest-based CTA
- Top 3 likely objections with Miyagi responses

### For LinkedIn DM
Output:
- Restrained compliment angle (4-6/10 enthusiasm)
- Business question to pry pain
- Personal connection thread idea
- WIIFM element (what value can you foreshadow?)
- Authority-building observation

### For Multi-Channel
Output the above for each channel plus recommended sequence order and timing.

---

## Step 6: Deliver the Research Brief

Present a clean research brief with:

1. **Account Overview:** Company, contact, role, tier
2. **Trigger Found:** What signal and where you found it
3. **Messaging Angle:** The problem to lead with and why
4. **Channel-Specific Copy Angles:** Tailored for each planned channel
5. **VOC Opportunities:** Any prospect language to mirror
6. **Next Steps:** What to write first, which skill to use next

**Cross-reference:** If the user needs the actual outreach copy written, direct them to:
- `/cold-email` for email copy
- `/cold-call-script` for call frameworks
- `/linkedin-dm` for DM sequences
- `/first-line` for personalized opening lines
