---
name: Awareness Stage Diagnostic
description: "Interactive diagnostic that identifies your market's awareness stage and sophistication level, then produces a strategy brief with hook approach, offer type, copy length, and messaging recommendations. TRIGGERS: awareness diagnosis, awareness stage, market awareness, sophistication level, where is my market"
---

# Awareness Stage Diagnostic

This command walks you through a structured diagnostic to identify your market's awareness stage and sophistication level. It produces a strategy brief that determines what to say, how to say it, and where to begin.

## Process

Ask the user these 4 questions using AskUserQuestion, one at a time. Wait for each answer before proceeding.

### Question 1: Prospect Knowledge
"Think about the majority of people who will see your copy. Which statement best describes them?
A) They do not know they have this problem yet
B) They know they have the problem but do not know solutions exist
C) They know solutions exist and are evaluating different types of solutions
D) They know about your specific product and are comparing you to alternatives
E) They already know and trust your product -- just need a reason to buy now"

### Question 2: Market Skepticism
"How would you describe the skepticism level in your market?
A) Low -- people are excited by the concept itself, few competitors
B) Moderate -- several competitors making similar claims, proof matters
C) High -- market wants to know HOW things work, not just WHAT they do
D) Very high -- market has tried mechanisms before and experienced downsides
E) Cynical -- 'I have heard it all before, nothing works' sentiment"

### Question 3: Competitor Messaging
"Look at your top 2-3 competitors' ads and landing pages. What do their headlines and hooks focus on?
A) Simple descriptions of what the product does
B) Bold claims about results (bigger numbers, faster timelines)
C) Named methods, systems, or frameworks explaining HOW their product works
D) 'How to get X without Y' language -- removing negatives from previous solutions
E) Story-driven, identity-focused, or paradigm-shifting approaches"

### Question 4: Traffic Source
"Where is the primary traffic coming from?
A) Cold traffic -- paid ads to people who have never heard of us
B) Warm traffic -- email list subscribers, blog readers, social followers
C) Hot traffic -- retargeting visitors who have been to our site before
D) Referral traffic -- word of mouth, affiliate partners
E) Mixed -- significant traffic from multiple sources"

## Output

After collecting all 4 answers, produce the following structured output:

### Section 1: Awareness Stage Diagnosis
Map their answers to a primary awareness stage using the awareness-sophistication skill. Explain the diagnosis with specific evidence from their answers.

Format:
- **Primary Awareness Stage:** [Stage Name]
- **Confidence:** [High/Medium/Low based on consistency of answers]
- **Evidence:** [Which answers pointed to this stage]
- **If answers conflict:** Note the conflict and recommend targeting the lower awareness stage (it is safer to over-educate than under-educate)

### Section 2: Sophistication Stage Diagnosis
Map their answers to a market sophistication stage using the sophistication-examples.md reference.

Format:
- **Market Sophistication Stage:** [Stage Number and Name]
- **Evidence:** [Which answers pointed to this stage]
- **Implications:** [What this means for their messaging approach]

### Section 3: Strategy Brief

Produce a complete strategy table:

| Dimension | Recommendation |
|-----------|---------------|
| **Hook Strategy** | [What to lead with based on awareness stage] |
| **Offer Type** | [Content opt-in / Lead magnet / Trial / Sale / Promotion] |
| **Copy Length** | [Short / Medium / Long / Very Long] |
| **Approach** | [Direct / Indirect / Mixed] |
| **Mechanism Emphasis** | [Based on sophistication: claim only / named mechanism / mechanism + negative removal / paradigm reset] |
| **Proof Priority** | [What type of proof matters most at this stage] |
| **Primary Emotion** | [What emotion to target based on awareness level] |

### Section 4: Hook Templates
Provide 3 stage-appropriate hook templates from the awareness-hooks-by-stage.md reference, customized to their specific product and market.

### Section 5: What to Avoid
List the top 3 mistakes people commonly make when writing for this awareness/sophistication combination. Pull from the awareness-sophistication skill's anti-patterns.

### Section 6: Next Steps
Provide 3 specific actions they should take before writing, ordered by priority.
