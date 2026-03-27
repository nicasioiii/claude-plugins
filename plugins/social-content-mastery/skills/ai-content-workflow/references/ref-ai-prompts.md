---
name: AI Prompts Reference
description: Prompt templates for content generation, niche discovery, positioning, commenting, newsletter writing, and the meta-prompt framework
---

# AI Prompts Quick Reference

## Prompt Engineering Meta-Framework (Nicolas Cole)

### The "Unbundling Language" Process

**Goal:** Translate your expertise into AI-readable instructions.

**5-Step Structure for Any Content Prompt:**

```
STEP 1: RULES
Define 3-7 specific rules that make this content type work.
Example for LinkedIn posts:
- First 200 characters must be a hook AND cliffhanger
- Headers must be tangible, specific, actionable, skimmable
- Each section: declarative opening (what) --> 3-5 tactical pieces (how) --> one-sentence insight (why)
- Alternate between bulleted lists and paragraph style

STEP 2: POSITIVE ATTRIBUTES
List what "good" looks like:
- Conversational tone (reads like a friend texting advice)
- Specific numbers (not "a lot" but "347")
- Personal stories or examples (not generic advice)
- Clear transformation (reader's before/after state)

STEP 3: EXAMPLES
Provide 3-5 real examples of excellent output:
[Paste your best-performing posts that follow the rules]

STEP 4: INPUT VARIABLES
- Topic: [your subject]
- Industry: [your niche]
- Target audience: [specific person]
- Tone: [conversational/professional/bold]
- Platform: [LinkedIn/Twitter/Instagram]

STEP 5: OUTPUT FORMAT
- Length: [word/character count]
- Structure: [sections, bullets, paragraphs]
- Include: [CTA, hashtags, emoji usage]
```

### Key Insight
"AI slop is a prompt quality problem, not an AI limitation." Cole spent 20 hours compressing 10 years of expertise into prompts. That investment yields consistently high-quality output.

---

## AI Niche Interview Generator

### Purpose
Discover content/service opportunities from your existing knowledge.

### Prompt Template
```
You are a career strategist and niche discovery expert. Interview me to help me
discover my Information Advantage -- the specialized knowledge from my unique
combination of jobs, hobbies, goals, and experiences.

Ask me 6 questions, ONE AT A TIME, waiting for my response before the next:

1. What jobs have you worked in the last 2-5 years? What did you learn that
   most people in those roles don't realize?
2. What hobbies have you started or gotten deeply into recently?
3. What goals have you reached that you're proud of?
4. What specific skills have you built that others struggle with?
5. What unique experiences have shaped your perspective?
6. What topics do friends/colleagues always ask you about?

After all 6 answers, generate:
- A summary of my Information Advantage (2-3 sentences)
- A list of 5 specific businesses/industries I could create content for
- For each: the specific job title of the person who would benefit most
- For each: the specific problem I could help them solve
- For each: my unique competitive advantage over generic content
```

---

## AI Positioning Consultant

### Prompt Template
```
You are a positioning consultant specializing in personal brands and content
creators. Based on the following information about me:

[Paste your Information Advantage summary, current niche, target audience]

Generate:

1. A list of 30 more specific niches within my chosen industry
   (progressively more narrow)

2. A constellation of 20 tangentially related industries where my expertise
   would also be valuable (the "client constellation")

3. Three versions of a short-form bio:
   - Basic: "I [service] for [audience]"
   - Specific: Add industry, sub-niche, and specific deliverable
   - Problem/outcome focused: Add the problem solved and transformation delivered

Format each as ready-to-paste text for LinkedIn/Twitter/Instagram bio.
```

---

## LinkedIn Content Generator

### Prompt Template
```
You are a LinkedIn content strategist. Generate content for the following creator:

Niche: [your industry/topic]
Target reader: [specific job title or persona]
Content pillar: [which of your 3-5 pillars]

Step 1: Generate 3 potential content ideas using these proven LinkedIn styles:
1. Steps -- explaining something in sequential steps
2. Stats -- interesting stats, studies, industry trends
3. Mistakes -- what mistakes to avoid
4. Lessons -- what you learned from experience
5. Examples -- curated examples of companies, success stories

Step 2: Choose the ONE idea most likely to perform on LinkedIn and explain why.

Step 3: Write a complete LinkedIn post following these rules:
- First 200 characters: strong hook that creates curiosity (before "See more" fold)
- Introduction (200-400 chars): niche-specific problem + promise of solution
- 3-4 main sections with bold declarative headers
- Each section: opening statement + 3-5 tactical points + one insight
- Alternate between bulleted lists and paragraph style throughout
- Conclusion: actionable takeaway + CTA
- Total: approximately 2,800 characters
- Tone: conversational, authoritative, specific (no jargon, no fluff)

IMPORTANT: Include specific numbers, personal experience references, and
actionable advice. Avoid generic statements that any AI could produce.
```

---

## Newsletter Ghostwriting System

### Prompt Template
```
You are a newsletter strategist writing for [niche/industry].

Target reader: [specific persona]
Newsletter frequency: [weekly/biweekly]
Goal: [build trust / drive sales / establish authority]

Write a value newsletter with these 4 components:

1. SUBJECT LINE
   - 4-7 words maximum (before inbox cutoff)
   - Be CLEAR, not clever
   - Use compression: write long title first, then cut filler words
   - Bad: "You'll never believe it" / Good: "How to [specific outcome] in [timeframe]"

2. INTRODUCTION
   - Hook the reader in first 2 sentences
   - Connect to a specific problem they're facing this week
   - Transition to the value you're about to deliver

3. HEADERS (3-4 sections)
   - Skimmable -- reader should get 80% of value from headers alone
   - Tangible and specific (not "Tips for Success" but "3 Scripts That Close")
   - Numbered for easy navigation

4. SECTION CONTENT
   - Each section: specific advice + example + actionable next step
   - Include one personal story or case study
   - Conversational tone (first person, contractions, direct address)

End with: One clear CTA (reply, click, buy, share)

Topic for this newsletter: [your topic]
```

---

## Comment Engagement Generator

### Prompt Template
```
You are a social media engagement strategist. Generate thoughtful, valuable
comments for me to post on content in my niche.

My niche: [your industry/topic]
My expertise: [what you're known for]
Platform: [LinkedIn/Twitter/Instagram]

For each of the following post topics, write a comment that:
- Adds genuine value (not just "great post!")
- Demonstrates my expertise without being self-promotional
- Is 2-4 sentences long (comment-appropriate length)
- Asks a follow-up question OR shares a relevant insight
- Sounds conversational and authentic

Post topics to comment on:
1. [Topic 1]
2. [Topic 2]
3. [Topic 3]

Generate 2 comment variations per topic.
```

---

## AI Services Outreach Prompt

### Purpose
Replaces 15-20 minutes of manual prospect research with ~15 seconds of AI output.

### Prompt Template
```
Research the following person for a potential ghostwriting/content service pitch:

Name: [prospect name]
Company: [company name for disambiguation]

Generate:
1. All social profiles (bird's eye view of digital footprint)
2. Medium-form bio (crash course on who this person is -- 3-4 sentences)
3. Audit of their social profiles based on:
   - Posting consistency
   - Content quality and engagement
   - Profile optimization (bio, headline, about section)
   - Obvious gaps or missed opportunities
4. Identification of 3 specific problems I could help solve
5. Tailored pitch recommendation per service type:
   - Social ghostwriting pitch angle
   - Newsletter ghostwriting pitch angle
   - LinkedIn content strategy pitch angle
```

---

## Short-Form Content Generator (5 Formats)

### Prompt Template
```
Generate [number] short-form social posts for [platform] using the following format:

FORMAT: [Choose one]
1. Paragraph style -- Concise insight/opinion (3-5 sentences, punchy)
2. Listicle -- "X things you don't need to [achieve Y]"
3. Old vs. New -- Contrast outdated approach with modern approach
4. Framework/Steps -- Tactical how-to in numbered steps
5. One-liner/Punchline -- Compressed wisdom in one powerful sentence

RULES FOR THIS FORMAT:
[Insert format-specific rules from the 5 formats section]

POSITIVE ATTRIBUTES:
- Sounds like a real person sharing hard-won insight (not a textbook)
- Includes at least one specific number or example
- Creates a "save this" or "share this" impulse
- No filler phrases ("In today's world...", "Let's dive in...")

TOPIC: [your subject]
AUDIENCE: [who should care]
TONE: [conversational/bold/analytical/vulnerable]

Generate 3 variations, each taking a slightly different angle on the topic.
```

---

## Sacred Hours Productivity Prompt

### Prompt Template
```
Help me design my Sacred Hours productivity system.

Sacred Hours = blocked chunks of uninterrupted time (minimum 2 hours)
for deep creative work.

Answer these questions to find my Sacred Hours:
1. What time am I most productive? [your answer]
2. What time can I be least responsive? [your answer]

Based on my answers, create:
1. A weekly Sacred Hours schedule (weekday + weekend blocks)
2. A pre-Sacred Hours ritual checklist (workspace prep, device management)
3. A Sacred Hours content production schedule (what to create in each block)
4. Rules for protecting Sacred Hours (what to say no to, how to communicate boundaries)
```

---

## AI Content Quality Checklist

Before publishing any AI-assisted content, verify:

- [ ] Does it sound like ME? (not generic AI voice)
- [ ] Does it contain MY unique insights? (not advice anyone could give)
- [ ] Are all stats and claims verified? (AI fabricates statistics)
- [ ] Is there at least one personal story or specific example?
- [ ] Have I removed all AI tells? (see list in SKILL.md)
- [ ] Would I be proud to put my name on this?
- [ ] Does it pass the "could a competitor have written this?" test?
- [ ] Is the hook compelling to a HUMAN (not just well-structured)?

If any answer is "no," revise before publishing. AI acceleration should save time on structure and drafting -- never on thinking and authenticity.
