---
name: Pitch Craft
description: Craft a cold pitch for a specific prospect. Combines prospect research, messaging psychology, and channel-specific copy into a complete outreach message. Activates prospect-research and outbound-psychology skills, plus the appropriate channel skill. Outputs a ready-to-send pitch with psychological reasoning.
---

# Cold Pitch Crafter

## Step 1: Gather Prospect Context

Ask the user:

1. **Prospect details:** Company name, contact name, their role/title
2. **Your offer:** What do you sell? (Be specific -- not "marketing services" but "we write cold email campaigns that book 15+ meetings/month")
3. **Your case study:** One sentence about a relevant result (e.g., "We helped X company achieve Y result in Z time")
4. **Channel:** Where are you sending this? (cold email, LinkedIn DM, cold call, Instagram DM, Facebook DM)
5. **Research done:** What do you already know about this prospect? (LinkedIn profile, recent news, triggers found, pain points identified)
6. **Your confidence level:** Are you feeling confident about this pitch? (This helps determine if mindset guidance is needed alongside the tactical pitch)

---

## Step 2: Build the Messaging Foundation

**Load skill:** `prospect-research` > references/messaging-matrix.md

### Quick Messaging Matrix
Based on available information, fill in:
- **Their likely priority:** What matters most given their role and recent activity?
- **Their current solution:** How are they probably handling this today?
- **Their problem:** What is painful about the current approach?
- **Their aspiration:** What would the ideal outcome look like?

### Trigger Check
**Load skill:** `prospect-research` > references/trigger-research-workflows.md

Identify the strongest available trigger (hard > soft > activity-based). Use the first-best principle -- the first good trigger is the best trigger.

---

## Step 3: Apply Psychological Principles

**Load skill:** `outbound-psychology` > references/persuasion-psychology.md

For this specific pitch, determine:

1. **Reciprocity play:** What value can you lead with or offer?
2. **Curiosity gap:** What subject line / opening creates curiosity without revealing everything?
3. **Social proof angle:** Which case study or result is most relevant to THIS prospect?
4. **Personalization depth:** How specific can you get based on available research?
5. **CTA design:** What is the minimum viable ask? (Never ask for time in first outreach)
6. **Foot-in-the-door sequence:** What small ask leads to the bigger commitment?

---

## Step 4: Craft the Channel-Specific Pitch

### For Cold Email
**Load skill:** `cold-email-copy`

Structure:
1. **Subject line:** 5 words or less, internal camouflage, no gimmicks
2. **First line (personalization):** Research-based, leads with trigger in first 5-10 words
3. **Problem statement:** Using messaging matrix, specific enough to trigger a memory
4. **Value/social proof:** One-sentence case study formula ("Recently we helped [X] achieve [Y] in [Z]")
5. **CTA:** Interest-based ("Would this be relevant?") or offer-based (+28% reply rate)
6. **Technical compliance:** Under 150 words, plain text, no links, no images, spintax on CTA

Provide 2-3 subject line options and 2 CTA variants for A/B testing.

### For LinkedIn DM
**Load skill:** `linkedin-outreach`

Structure (Multi-Thread):
1. **Greeting:** "Hey [First name]." (separate message, no exclamation)
2. **Restrained compliment:** 4-6/10 enthusiasm, specific to their business
3. **Rephrase their offer as a question:** Pries pain genuinely
4. **Business question:** Mandatory -- pry at least one pain point
5. **Personal connection thread:** Separate from business
6. **WIIFM element:** What is in it for them to respond?

Include guidance on tone: contractions always, varied line lengths, spontaneity phrases, no exclamation points.

### For Cold Call
**Load skill:** `cold-calling`

Structure:
1. **Opener:** Tailored Permission or Heard the Name (with specific context)
2. **Problem Proposition:** Persona + annoyances + scenery + emotion (Hairy Lollipop Test)
3. **One-Sentence Solution:** Single biggest differentiator
4. **Interest-Based CTA:** "Would you be open to learning more sometime?"
5. **Top 3 Objection Responses:** Using Mr. Miyagi (agree, incentivize, test drive)

Include tone guidance: slow down, laugh at objections, downtones, "feet up" energy for opener.

### For Instagram/Facebook DM
**Load skill:** `dm-outreach`

Structure:
1. **Connection strategy:** How to connect (group member, content engager, cold follow)
2. **Opening DM:** Low-friction, value-first
3. **Pain discovery questions:** Move from Level 1 (surface) to Level 2 (specific)
4. **Call proposal framing:** Only after Level 2 pain identified; "triage call" framing

---

## Step 5: Mindset Check

**Load skill:** `outbound-psychology`

If the user indicated low confidence:
- Address the specific imposter lie that applies (Bree Weber's 3 lies)
- Remind: on the other side of that inbox is just another human being
- Everything they have done counts
- The authority section is optional
- They can pitch something they have never done before

If the user seems ready:
- Remind them to check emotional state before sending
- SURE language review -- remove any weak qualifiers
- Detach from outcome: "Send it and on to the next one"

---

## Step 6: Deliver the Complete Pitch

Output:

### The Pitch
The ready-to-send/say message, formatted for the channel.

### Why This Works (Psychological Reasoning)
Brief explanation of which principles are at play and why the prospect should respond.

### Personalization Opportunities
If the user provides more research later, note where additional personalization would strengthen the pitch.

### Follow-Up Plan
What to send/do if they do not respond:
- Timing for first follow-up
- Angle for follow-up message
- When to break up

### A/B Testing Suggestion
One variable to test (subject line variant, CTA variant, or problem angle variant).
