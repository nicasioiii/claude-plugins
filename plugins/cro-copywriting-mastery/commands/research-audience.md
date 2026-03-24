---
name: Audience Research Worksheet
description: "Guided worksheet for audience research. Asks 5 questions about your target customer and produces a structured research brief with avatar summary, research priorities, and next steps. TRIGGERS: audience research, customer research, avatar, voice of customer, who is my customer"
---

# Audience Research Worksheet

This command walks you through a structured audience research process. It produces a One-Page Avatar Summary and a prioritized research plan.

## Process

Ask the user these 5 questions using AskUserQuestion, one at a time. Wait for each answer before proceeding.

### Question 1: Product and Problem
"What product or service are you writing copy for, and what is the primary problem it solves? Be as specific as possible about both the product and the problem."

### Question 2: Current Customer Knowledge
"How much do you already know about your target customer? Choose one:
A) I have paying customers I can survey and interview
B) I have trial users or leads but few paying customers
C) I have website visitors but no customers yet
D) I am pre-launch with no customers or visitors"

### Question 3: Customer Description
"Describe your ideal customer in 2-3 sentences. Include: who they are (role/identity), what frustrates them most, and what outcome they want. If you are unsure, describe who you THINK they are."

### Question 4: Competitive Landscape
"Name 2-3 competitors or alternatives your customer might consider instead of you. What do those alternatives get wrong or leave unaddressed?"

### Question 5: Existing Research
"What research have you already done? Check all that apply:
A) Customer interviews
B) Customer surveys
C) Review mining (Amazon, Reddit, forums)
D) On-site polls or exit-intent surveys
E) Support ticket or chat transcript analysis
F) None yet"

## Output

After collecting all 5 answers, produce the following structured output:

### Section 1: One-Page Avatar Summary
Using the customer-research skill, generate a complete One-Page Avatar Summary with:
- Avatar Name (assign one based on their description)
- One-sentence summary
- Top 3 Pains (inferred from their answers)
- Top 3 Desires (inferred from their answers)
- Top 3 Likely Objections (inferred from competitive landscape)
- Probable Buying Trigger
- Core Emotional State (fear-based or hope-based)
- Suggested Language to Use (based on their product/problem description)

### Section 2: Research Priority Matrix
Based on their answer to Question 2, recommend the highest-priority research method:
- A (paying customers): Start with 7 customer interviews using the interview-guide.md protocol
- B (trial users): Start with a trial user survey using Question Set B from survey-templates.md
- C (visitors only): Start with exit-intent polls + review mining from review-mining-process.md
- D (pre-launch): Start with review mining + competitor content audit + AYTM survey

### Section 3: Top 5 Research Questions
Generate 5 custom research questions tailored to their specific product and market, using the question bank from the customer-research skill.

### Section 4: Before-After Grid Starter
Pre-fill as much of the Before-After Grid as possible from their answers:
- Have (before/after)
- Feel (before/after)
- Average Day (before/after)
- Status (before/after)
- Good vs. Evil (before/after)

Mark any cells that need research to complete.

### Section 5: Next Steps
Provide 3 specific, actionable next steps prioritized by impact and feasibility.
