---
name: AI Content
description: AI-assisted content creation. Generate posts, hooks, scripts, or repurposed content using proven prompt frameworks from the Ghostwriter GPT system. Supports LinkedIn, Twitter/X, Instagram, and newsletter formats.
---

# /ai-content -- AI-Assisted Content Creator

## INTAKE QUESTIONS (Ask All Before Generating)

### Question 1: Content Type
**What do you want to create?**

| Choice | Output |
|--------|--------|
| A) LinkedIn post | Full post: hook + body + CTA (~2,800 chars) |
| B) Twitter/X post or thread | Tweet or thread with hook + value + CTA |
| C) Instagram caption | Caption with hook, body, CTA, hashtags |
| D) Newsletter issue | Subject line + intro + 3-4 sections + CTA |
| E) Social hooks (batch) | 5-10 hook variations for a single topic |
| F) Content repurpose | Transform one piece into multiple platform formats |
| G) Comment engagement batch | 5-10 thoughtful comments for niche engagement |

### Question 2: Topic and Pillar
**What topic should this content cover?**
- Specific subject or angle
- Which of your content pillars does this fall under?
- Any specific story, stat, or insight you want to include?

### Question 3: Target Reader
**Who specifically should care about this content?**
- Job title or persona
- What problem are they facing?
- What transformation do they want?

### Question 4: Tone and Voice
**What tone should the content have?**

| Choice | Description |
|--------|------------|
| A) Conversational authority | Friendly expert sharing insights |
| B) Bold and contrarian | Challenging conventional wisdom |
| C) Vulnerable and personal | Sharing struggle or lesson learned |
| D) Tactical and actionable | Step-by-step practical advice |
| E) Analytical and data-driven | Stats, studies, evidence-based |

### Question 5: Content Format (if applicable)
**Which format should this use?**

| Choice | Format |
|--------|--------|
| A) Paragraph style | Concise insight or opinion |
| B) Listicle | "X things/mistakes/rules" |
| C) Old vs. New | Contrast outdated vs. modern approach |
| D) Framework/Steps | Numbered tactical how-to |
| E) One-liner/Punchline | Compressed wisdom |
| F) Story-driven | Personal narrative with lesson |
| G) Let me choose based on topic | AI selects best format |

---

## EXECUTION PROCESS

### Step 1: Load Skills
1. Load `ai-content-workflow` SKILL.md
2. Load `ai-content-workflow/references/ref-ai-prompts.md`
3. If LinkedIn: also load `linkedin-growth` SKILL.md for platform rules
4. If Twitter: also load `twitter-growth` SKILL.md for platform rules
5. If hooks requested: also load `write-hooks` SKILL.md

### Step 2: Apply AI Leverage Framework
Before generating, verify the user is providing:
- Their unique expertise or angle (not asking for generic content)
- Specific audience context
- At least one personal insight, story, or data point

If any are missing, ask: "To create content that sounds like YOU and not generic AI, I need [specific missing element]. Can you provide that?"

### Step 3: Generate Content Using Prompt Framework
Apply the 5-step prompt engineering structure:
1. Define rules for the platform/format
2. Apply positive attributes (conversational, specific, personal)
3. Incorporate user's examples and voice
4. Use their input variables
5. Deliver in requested format

### Step 4: AI Quality Check
Before delivering, verify against the AI Content Quality Checklist:
- Does it sound like the user (not generic AI voice)?
- Does it contain their unique insights (not advice anyone could give)?
- Have all AI tells been removed?
- Is there at least one personal element?
- Would the user be proud to put their name on this?

### Step 5: Deliver with Variations
Provide:
- **Primary version** -- Best-fit content piece
- **Hook variation** -- Alternative opening for A/B testing
- **CTA variation** -- Alternative call to action
- **Platform adaptation notes** -- How to adjust for other platforms

---

## OUTPUT FORMAT

### For LinkedIn Posts
```
## YOUR LINKEDIN POST

### Hook (first 200 characters -- before "See more")
[Hook text]

### Full Post
[Complete post body with formatted headers and sections]

### CTA
[Call to action]

---

### Alternative Hook
[Variation for A/B testing]

### Repurpose Notes
- Twitter thread version: [brief adaptation guidance]
- Instagram caption version: [brief adaptation guidance]
```

### For Newsletter Issues
```
## YOUR NEWSLETTER

### Subject Line Options (pick one)
1. [Option 1 -- 4-7 words]
2. [Option 2 -- 4-7 words]
3. [Option 3 -- 4-7 words]

### Introduction
[Hook + context + transition]

### Section 1: [Header]
[Content]

### Section 2: [Header]
[Content]

### Section 3: [Header]
[Content]

### CTA
[Clear single call to action]
```

### For Hook Batches
```
## HOOK VARIATIONS FOR: [Topic]

| # | Hook | Type | Platform Fit |
|---|------|------|-------------|
| 1 | [Hook text] | [Question/Statement/Story/Stat] | [Best platform] |
| 2 | [Hook text] | [Type] | [Best platform] |
| ... | ... | ... | ... |

### Recommendation
Best hook for [platform]: #__ because [rationale]
```

---

## EDGE CASES

- **No niche or audience defined:** Route to `/build-brand` first. AI content without positioning = generic content.
- **Wants fully AI-generated content with no personal input:** Explain AI leverage vs. dependency. Require at least one personal insight per piece.
- **Wants batch content (week/month):** Generate framework + 3-5 sample pieces, then provide the prompt template for user to continue generating.
- **Newsletter request without email list:** Recommend building list first via lead magnet (route to `/create-lead-magnet`).
- **Ghostwriting for clients (not self):** Route to `ghostwriting-freelance` skill.
