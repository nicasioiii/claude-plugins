---
name: Audit Content
description: Review existing content performance and diagnose why posts are underperforming. Analyzes hooks, formats, posting patterns, and engagement metrics to produce a diagnostic report with specific fixes.
---

# /audit-content -- Content Performance Diagnostic

## INTAKE QUESTIONS (Ask All Before Auditing)

### Question 1: Platform & Account
**Which platform are you auditing?**

| Choice | Audit Focus |
|--------|-------------|
| A) Instagram (Reels, Stories, Posts) | Hook quality, reel length, hashtags, posting time, audio, visual quality |
| B) LinkedIn (text posts, carousels) | Hook first 200 chars, post structure, engagement questions, content style |
| C) YouTube (long-form + Shorts) | Thumbnails, titles, retention curves, search optimization |
| D) TikTok | Hook speed, trending audio, format trends, completion rate |
| E) Multi-platform | Cross-platform comparison, repurposing effectiveness |

### Question 2: Performance Data
**Share your recent performance metrics:**
- How many posts in the last 30 days?
- Average views or impressions per post
- Average engagement rate (likes + comments / followers)
- Best-performing post (link or description + metrics)
- Worst-performing post (link or description + metrics)

### Question 3: Content Type Breakdown
**What types of content have you been posting?**
- A) Mostly educational / how-to
- B) Mostly storytelling / personal
- C) Mostly trending / reactive
- D) A mix of everything
- E) Not sure -- I post whatever comes to mind

### Question 4: Growth Context
**What does your growth trend look like?**
- A) Flat -- same views and followers for weeks
- B) Declining -- getting fewer views than before
- C) Growing slowly -- some traction but inconsistent
- D) One post went viral but nothing else performs
- E) Brand new -- not enough data yet

### Question 5: Creator Self-Assessment
**What do YOU think the problem is?**
- A) My hooks are not grabbing attention
- B) People watch but do not follow or engage
- C) I am not posting consistently enough
- D) I do not know what to post about
- E) I have no idea what is wrong

---

## DIAGNOSTIC PROCESS

### Step 1: Hook Analysis
1. Load `write-hooks` SKILL.md
2. Load `ref-hook-writing-process.md`
3. Evaluate the hooks from their recent posts:
   - Is the topic clear in the first sentence?
   - Is "you/your" present in the first two sentences?
   - Is there a contrast (common belief vs. contrarian reality)?
   - For video: are text, spoken, visual, and audio hooks aligned?
4. Apply the CGOVE framework: Clarity, Gap, Originality, Value, Emotion
5. Score each hook on a 1-5 scale per dimension
6. Identify the weakest hook dimension across all posts

### Step 2: Content Strategy Analysis
1. Load `content-strategy` SKILL.md
2. Load `ref-idea-generation.md`
3. Evaluate content mix:
   - Are they rotating through content pillars or repeating the same angle?
   - Are they using multiple Magical Multipliers or stuck on one format?
   - Is there a balance between growth content and nurture content?
4. Check for the "content plateau" pattern: same topics, same format, same hook structure
5. Identify content gaps (missing pillars, underused formats)

### Step 3: Platform-Specific Diagnosis
1. Load the relevant platform-specific growth skill (e.g., `instagram-growth`, `youtube-growth`)
2. Load the relevant platform reference file
3. Check platform-specific factors:
   - **Instagram:** Reel length, hashtag strategy, posting time, audio usage, caption quality
   - **LinkedIn:** Post length, formatting, engagement questions, publishing cadence
   - **YouTube:** Thumbnail quality, title optimization, first-30-seconds retention, video length
   - **TikTok:** Hook speed, trend participation, completion rate indicators
4. Apply the "Why Your Reels Ain't Poppin" checklist for Instagram (from ref-content-optimization.md)

### Step 4: Growth Pattern Analysis
1. Load the relevant platform-specific growth skill
2. Load the platform's reference file for benchmarks and tactics
3. Evaluate growth fundamentals:
   - Posting consistency (frequency and schedule adherence)
   - Engagement behavior (commenting on others, community participation)
   - Profile optimization (bio, featured content, CTA clarity)
   - Content repurposing (single-platform vs. multi-platform)
4. Check for the "doubling down" signal: are they creating more of what works?

### Step 5: Competitive Benchmark
1. Ask for 2-3 creators in their niche they admire
2. Compare hook style, format mix, posting cadence, and engagement approach
3. Identify specific tactical differences between their content and successful competitors
4. Apply the Study Framework for competitor analysis

---

## OUTPUT FORMAT

Deliver a complete Content Audit Report containing:

1. **Executive Summary**: 3-sentence diagnosis of the primary issue
2. **Hook Scorecard**: CGOVE scores for their last 5 posts with specific notes
3. **Content Mix Analysis**: Pillar rotation, format variety, multiplier usage
4. **Platform Compliance Check**: Platform-specific factors scored pass/fail
5. **Growth Fundamentals Check**: Consistency, engagement, profile, repurposing scored
6. **Top 3 Issues Ranked**: Most impactful problems identified, in priority order
7. **Fix Plan**: For each issue, a specific action with example
8. **Quick Win**: One change they can make on their very next post
9. **30-Day Recovery Plan**: Week-by-week action items to improve performance
10. **Next Steps**: Recommend relevant commands -- "/write-hook to fix hooks" or "/content-plan to rebuild strategy"
