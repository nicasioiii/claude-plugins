---
name: Offer Engineering Scorecard
description: "Score and build offers using the Attractive Solution and Irresistible Offer scorecards. Asks 5 questions about your offer, scores it on 16 dimensions, and produces improvement recommendations with copy-ready language. TRIGGERS: offer engineering, score my offer, improve my offer, value stack, pricing, guarantee"
---

# Offer Engineering Scorecard

This command walks you through a structured offer evaluation. It scores your offer on 16 dimensions across two scorecards and produces specific improvement recommendations with copy-ready language.

## Process

Ask the user these 5 questions using AskUserQuestion, one at a time. Wait for each answer before proceeding.

### Question 1: The Offer
"Describe your offer in detail. What is the product or service? What does the customer get when they buy? Include the price point if you have one."

### Question 2: The Result
"What specific, measurable result does the customer get? How quickly do they typically see their first result? And how much effort is required from the customer to get that result?"

### Question 3: The Proof
"What proof do you have that this works? Include: testimonials, case studies, number of customers, specific results achieved, any data or research supporting the approach."

### Question 4: The Competition
"What alternatives does your customer have? What do those alternatives cost? What do those alternatives get wrong or leave unaddressed?"

### Question 5: Current Offer Elements
"Which of these does your offer currently include? Check all that apply:
A) Money-back guarantee
B) Bonuses or added-value items
C) A named method, system, or framework
D) Urgency or scarcity element
E) Value stack showing total worth vs. price
F) Payment plan option
G) None of these yet"

## Output

After collecting all 5 answers, produce the following structured output:

### Section 1: Attractive Solution Scorecard
Score the offer 1-10 on each of the 9 Attractive Solution dimensions from the offer-scorecard-template.md. For each score, provide a brief justification based on their answers.

1. Solves a Significant Problem: _/10
2. Produces a Big, Desirable Result: _/10
3. New, Not Simply Better: _/10
4. Unique and Different: _/10
5. Superior to Alternatives: _/10
6. Quick and Easy to Implement: _/10
7. Produces Fast Results: _/10
8. Done-For-You Elements: _/10
9. Success Confidence: _/10

**Total: _/90**

Provide the assessment: Exceptional (80+), Strong (70-79), Needs Work (50-69), or Rework Required (below 50).

### Section 2: Irresistible Offer Scorecard
Score the offer 1-10 on each of the 7 Irresistible Offer dimensions.

1. Outcome Clarity: _/10
2. Price Perception: _/10
3. Time to Results: _/10
4. Effort Required: _/10
5. Perceived Likelihood of Success: _/10
6. Risk Reversal: _/10
7. Urgency: _/10

**Total: _/70**

Provide the assessment: Irresistible (60+), Strong (50-59), Needs Work (35-49), or Not Ready (below 35).

### Section 3: The One-Liner Test
Write the offer as a single 5-15 word sentence. Evaluate whether it passes:
- [ ] States a specific, desirable outcome
- [ ] Implies speed or ease
- [ ] Would make a prospect say "Tell me more"
- [ ] Cannot be confused with a competitor's offer

If it fails, provide 3 alternative one-liners.

### Section 4: Top 3 Improvement Priorities
Identify the 3 lowest-scoring dimensions and provide specific, actionable improvement recommendations for each:

For each priority:
- **Current score:** X/10
- **The problem:** What is weak about this dimension
- **The fix:** Specific action to take
- **Copy-ready language:** A draft sentence or paragraph they can use in their copy to strengthen this dimension

### Section 5: Value Stack Draft
If they have bonuses (Question 5B), build a value stack. If they do not, recommend 2-3 bonuses and build the stack with those recommendations.

Include:
- Each component with name and value
- Bonus items with values
- Total perceived value
- Actual price
- Value-to-price ratio
- Draft copy following the value-stack presentation format from the value-stacking-worksheet.md

### Section 6: Guarantee Recommendation
Based on their product type and current guarantee status, recommend a specific guarantee structure using templates from the guarantee-templates.md reference. Provide draft guarantee copy ready to use.

### Section 7: Pricing Psychology Recommendation
Based on their price point and competitive landscape, recommend 2-3 pricing psychology tactics from the pricing-psychology-playbook.md reference. Provide draft sentences implementing each tactic.

### Section 8: Next Steps
Provide 3 specific actions ordered by impact:
1. The highest-impact offer improvement to make first
2. The copy element to write or rewrite immediately
3. The test to run to validate the improved offer
