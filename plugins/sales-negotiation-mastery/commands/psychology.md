---
name: psychology
description: "Explain or apply a psychological principle to a sales or negotiation situation. Maps to sales-psychology and sales-mindset-prep."
---

# /psychology Command

## Purpose

Help the user understand, explain, or apply a psychological principle to their sales or negotiation situation.

## Routing

**Primary skill:** `sales-psychology`
**Supporting skill:** `sales-mindset-prep` (when the question relates to mindset, conviction, or inner game)

## Workflow

1. **Identify the principle.** What psychological concept is the user asking about? Common requests:
   - Loss aversion / prospect theory
   - Framing and reframing
   - Consistency bias / Socratic dialogue
   - The Six Human Needs
   - System 1 vs. System 2
   - The Belief Ladder / Buying Pocket
   - Negotiator types (Analyst, Accommodator, Assertive)
   - The Mirror principle (your objections = their objections)
   - "Know their religion"
   - Selling to affluent / empathy gap

2. **Explain the principle.** Draw from `sales-psychology` SKILL.md and references. Use the source instructor's framing and examples.

3. **Apply to their context.** If the user provides a specific situation, show HOW the principle applies. Give actionable advice, not just theory.

4. **Cross-reference related skills.** If the psychological principle connects to a specific technique (e.g., loss aversion --> accusation audits in `tactical-empathy`), point them to the related skill.

## Example Interactions

**User:** "Why do prospects keep saying 'I need to think about it' when the call went well?"
- Route: `sales-psychology` (consistency bias, System 1/2) + `objection-handling` cross-reference
- Explain: The prospect's System 1 (emotional brain) may feel good, but System 2 (rational brain) has not been given enough structure to act. Also check the Mirror principle -- do YOU believe they should think about it?

**User:** "How do I use loss aversion in my pitch?"
- Route: `sales-psychology` (prospect theory, bending reality)
- Explain the 70% stat, then show how to frame their current pain as ongoing loss, not just absence of gain

**User:** "What type of negotiator am I dealing with?"
- Route: `sales-psychology` (Three Negotiator Types) + `negotiation-tactics` cross-reference
- Walk them through identifying Analyst, Accommodator, or Assertive traits
