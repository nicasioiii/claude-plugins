---
name: Content Plan
description: Generate a content calendar from brand foundation. Asks about pillars, audience, platform, and cadence, then produces a 30-day content plan with topics, formats, and hook starters using content-strategy skill.
---

# /content-plan -- Content Calendar Generator

## INTAKE QUESTIONS (Ask All Before Planning)

### Question 1: Brand Foundation Status
**Have you completed your brand foundation?**

| Choice | Action |
|--------|--------|
| A) Yes, I have pillars, avatar, and positioning defined | Proceed -- ask for their pillars and avatar summary |
| B) Partially -- I know my niche but haven't formalized | Gather key inputs inline, note gaps, recommend /build-brand later |
| C) No, starting from scratch | Route to /build-brand first |

### Question 2: Platform & Format
**What platform(s) and format(s) are you creating for?**
- Primary platform (Instagram, LinkedIn, YouTube, TikTok, multi)
- Preferred formats (short video, long video, text posts, carousels, mix)

### Question 3: Current Cadence
**How often can you realistically create and post?**
- A) Daily (7 days/week) -- learning phase, building habit
- B) 5 days/week -- dedicated creator
- C) 3 days/week -- sustainable long-term
- D) 1-2 days/week -- limited capacity

### Question 4: Creation Workflow
**How do you prefer to create?**
- A) Daily creation (one post per day, idea to publish)
- B) Batch creation (dedicate specific days to specific tasks)
- C) Not sure yet

### Question 5: Content Inputs
**Provide the following (or let me generate based on your brand):**
- Content pillars (3-5)
- Audience archetypes or segments (2-3)
- Sub-topics you want to cover
- Any trending topics or timely themes to include

---

## GENERATION PROCESS

### Step 1: Content Multiplication Setup
1. Load `content-strategy` SKILL.md
2. Load `ref-idea-generation.md`
3. Define the 5 variables: Pillars, Buckets (Futurism/Story/Actionable), Multipliers, Archetypes, Sub-topics
4. Run the multiplication math to show total idea potential

### Step 2: Format Selection
1. Load `ref-content-formats.md`
2. Match formats to platform:
   - Instagram: 70% Reels, 25% Stories, 5% Posts
   - LinkedIn: 60% text, 25% carousels, 15% video
   - YouTube: Long-form + Shorts split
   - Multi: platform-specific format mix
3. Apply content split: 80% growth / 20% nurture (growth phase) or 60/20/20 (balanced)

### Step 3: 30-Day Calendar Build
1. Apply rotation logic: Pillar rotation, Multiplier rotation, Archetype rotation
2. Fill 30 days with: pillar, bucket, multiplier, archetype, topic, format, hook starter
3. Include 2-3 "Outlines As Content" test slots per week
4. Reserve 1 open slot per week for trend-reactive content
5. Schedule explicit rest days

### Step 4: Hook Starters
1. Load `write-hooks` SKILL.md
2. For each content piece, suggest a hook starter from the appropriate archetype
3. Platform-appropriate: LinkedIn = text hook (first 200 chars), Video = spoken + text hook

---

## OUTPUT FORMAT

Deliver a complete 30-Day Content Plan containing:

1. **Content Strategy Summary**: Pillars, buckets, archetypes, cadence, format split
2. **Multiplication Math**: Total idea potential from their variables
3. **30-Day Calendar**: Table with columns: Day | Pillar | Bucket | Multiplier | Archetype | Topic | Format | Hook Starter
4. **Week 1 Detail**: First 7 days with full topic descriptions and hook suggestions
5. **Batch Creation Schedule**: If batch workflow chosen, day-by-day production schedule
6. **Tracking Setup**: Recommended metrics to track per post, weekly review process
7. **Next Steps**: "Use /write-hook to develop hooks for each piece" and "Use /write-script to build full scripts"
