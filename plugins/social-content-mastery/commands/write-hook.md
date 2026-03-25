---
name: Write Hook
description: Write and optimize a hook for any social platform. Asks about topic, platform, format, and target audience, then produces 3-5 hook variations with alignment analysis using write-hooks skill.
---

# /write-hook -- Hook Generator & Optimizer

## INTAKE QUESTIONS (Ask All Before Writing)

### Question 1: Topic & Main Point
**What is the video or post about?**
- What is the ONE main point or takeaway?
- What transformation or value does the viewer get?

### Question 2: Platform
**Which platform is this hook for?**

| Choice | Hook Approach |
|--------|--------------|
| A) Instagram / TikTok (short-form video) | 4-component hook: text + visual + spoken + audio |
| B) LinkedIn (text post) | Text-only hook, first 200 characters |
| C) YouTube (long-form) | Hook works WITH thumbnail, first 10 seconds |
| D) YouTube Shorts | Same as Instagram/TikTok approach |

### Question 3: Content Format
**What type of content is this?**
- A) Educational / How-to
- B) Story / Personal experience
- C) Challenge / Experiment
- D) Reaction / Commentary
- E) List / Comparison
- F) Skit / Entertainment

### Question 4: Target Viewer
**Who is this for?**
- Describe your ideal viewer in one sentence
- What is their current pain point or desire related to this topic?
- What do they currently believe about this topic (that you might challenge)?

### Question 5: Visual Context (Video Only)
**What visual assets do you have or plan to create?**
- A) Creator on camera (A-roll)
- B) B-roll footage available
- C) Screenshots or graphics
- D) Not sure yet -- help me decide

---

## GENERATION PROCESS

### Step 1: Analyze Contrast Opportunity
1. Load `write-hooks` SKILL.md
2. Identify the common belief (what most viewers think about this topic)
3. Identify the contrarian reality (what you know that differs)
4. Determine contrast type: Stated (name both) or Implied (only state contrarian)

### Step 2: Generate Spoken Hooks
1. Load `ref-hook-templates.md`
2. Select 3-5 archetypes that fit the topic:
   - Educational content -> Tutorial, Educational, Secret Reveal
   - Story content -> Experimentation, Contrarian
   - Trending content -> Fortuneteller, Question
3. Write each hook using the archetype structure
4. Apply "you/your" framing in first sentence
5. Ensure rapid context (topic clear in first sentence)

### Step 3: Generate Text Hooks (for video)
1. Write corresponding text overlays for each spoken hook
2. Fewest words possible, largest font mentally possible
3. Must elicit curiosity or emotional reaction

### Step 4: Suggest Visual Hooks (for video)
1. Based on visual context (A-roll, B-roll, graphics)
2. Recommend visual movement and layout
3. Ensure visual aligns with spoken + text message

### Step 5: Alignment Check
1. Apply 3-part alignment test to each variation
2. Apply CGOVE revision check
3. Flag any comprehension risks

---

## OUTPUT FORMAT

For each of 3-5 hook variations, deliver:

1. **Archetype Used**: Which spoken hook archetype
2. **Spoken Hook**: The exact words to say (1-2 sentences)
3. **Text Hook**: The on-screen text overlay (for video) or first 200 chars (for LinkedIn)
4. **Visual Suggestion**: Recommended visual approach (for video)
5. **Audio Suggestion**: Music/SFX recommendation (for video)
6. **Contrast Analysis**: Common belief vs. contrarian reality identified
7. **CGOVE Score**: Brief assessment of Clarity, Gap, Originality, Value, Emotion

### Summary Section
- **Recommended Top Pick**: Which variation is strongest and why
- **A/B Test Suggestion**: Which 2 variations to test against each other
- **Platform Note**: Any platform-specific adaptation needed
- **Next Step**: "Use /write-script to build the full script around this hook"
