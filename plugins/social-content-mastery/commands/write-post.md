---
name: Write Post
description: Write a social media post for LinkedIn, Instagram caption, or other text-based platform. Asks about topic, platform, audience, and goal, then produces a complete post with hook, body, CTA, and engagement question.
---

# /write-post -- Social Media Post Writer

## INTAKE QUESTIONS (Ask All Before Writing)

### Question 1: Platform
**Which platform is this post for?**

| Choice | Post Approach |
|--------|--------------|
| A) LinkedIn | Text post, max 2,800 chars, hook in first 200 chars, professional tone |
| B) Instagram caption (for Reel, carousel, or photo) | Shorter, casual tone, hashtags, CTA for comments |
| C) Twitter/X thread | Short punchy sentences, thread structure, hook in first tweet |
| D) Facebook | Conversational, storytelling, community-oriented |
| E) Other (specify) | Adapt format to platform norms |

### Question 2: Content Style
**What style of post is this?**
- A) Tips / Actionable advice (numbered steps or bullets)
- B) Stats / Data-driven insight (surprising number + analysis)
- C) Mistakes / What NOT to do (contrarian or cautionary)
- D) Lessons / What I learned (personal reflection)
- E) Examples / Case study (specific story with takeaway)
- F) Story / Personal experience (narrative arc)
- G) Opinion / Hot take (contrarian perspective)
- H) Not sure -- help me choose based on my topic

### Question 3: Topic & Main Point
**What is this post about?**
- What is the ONE main point or takeaway?
- What personal experience or angle do you have on this topic?
- What does the reader gain from reading this?

### Question 4: Target Reader
**Who is this for?**
- Describe your ideal reader in one sentence
- What is their current frustration or desire related to this topic?
- What do they currently believe about this topic?

### Question 5: Post Goal
**What do you want the reader to do after reading?**
- A) Comment with their experience or opinion (engagement)
- B) Comment a keyword for a free resource (lead gen)
- C) DM you for information (lead gen)
- D) Follow you for more (growth)
- E) Click a link in bio or comments (traffic)
- F) Save the post for later (algorithm boost)
- G) Just provide value -- no hard CTA

---

## GENERATION PROCESS

### Step 1: Hook Development
1. Load `write-hooks` SKILL.md
2. Load `ref-hook-templates.md`
3. Identify the contrast opportunity:
   - Common belief: what most people think about this topic
   - Contrarian reality: what you know that differs
4. Generate 3 hook options using archetypes appropriate to the content style:
   - Tips -> Educational, Tutorial
   - Stats -> Secret Reveal, Fortuneteller
   - Mistakes -> Contrarian, Educational
   - Lessons -> Experimentation, Contrarian
   - Story -> Experimentation, Question
5. For LinkedIn: ensure hook is under 200 characters (before "See more" truncation)
6. For Instagram: optimize for first line visibility in caption preview

### Step 2: Body Structure
1. Load `write-scripts` SKILL.md
2. Load `ref-linkedin-writing.md` (for LinkedIn) or adapt for other platforms
3. Apply the appropriate structure based on content style:
   - **Tips**: Hook -> Brief intro -> Tip 1 -> Tip 2 -> Tip 3 (to 7) -> Conclusion -> CTA
   - **Stats**: Hook -> The stat -> Why it matters -> What to do about it -> CTA
   - **Mistakes**: Hook -> Mistake 1 (+ fix) -> Mistake 2 (+ fix) -> Mistake 3 (+ fix) -> CTA
   - **Lessons**: Hook -> Context/story -> Lesson 1 -> Lesson 2 -> Lesson 3 -> Takeaway -> CTA
   - **Examples**: Hook -> Setup context -> Example with specifics -> Analysis -> CTA
   - **Story**: Hook -> Scene-setting -> Conflict/challenge -> Resolution -> Lesson -> CTA
   - **Opinion**: Hook -> Contrarian claim -> Evidence/reasoning -> Nuance -> CTA
4. Alternate formatting across sections: use short paragraphs, bullets, single-line emphasis
5. Ensure "you/your" framing appears early in the post

### Step 3: CTA & Engagement
1. Based on post goal, select CTA approach:
   - **Engagement**: End with an open question that invites personal experience sharing
   - **Lead gen (keyword)**: "Comment [KEYWORD] and I will send you my [resource]"
   - **Lead gen (DM)**: "DM me [KEYWORD] for [specific thing]"
   - **Growth**: "Follow for more [topic] breakdowns every [frequency]"
   - **Traffic**: "Link in bio for [specific resource]" or "Link in comments"
   - **Save**: "Save this for when you need it"
2. For LinkedIn: consider adding an autoplug (a pre-written comment with additional value or link)

### Step 4: Platform Optimization
1. **LinkedIn**: Check character count (under 2,800), formatting variety, no external links in body (kills reach), add hashtags only if relevant (3-5 max)
2. **Instagram**: Keep caption concise, front-load value, add 10-20 relevant hashtags, include line breaks for readability
3. **Twitter/X**: First tweet must hook, thread should be 3-10 tweets, end with recap + CTA
4. **Facebook**: More conversational, storytelling works well, questions drive comments

### Step 5: Quality Check
1. Apply "you/your" check: appears in first two sentences
2. One Main Point test: can the post be summarized in one sentence?
3. Scroll-stop test: would the hook make YOU stop scrolling?
4. Voice check: does this sound like the creator, not like generic AI?
5. Remove AI-sounding words: "transform," "revolutionize," "unlock," "elevate," "game-changer"

---

## OUTPUT FORMAT

Deliver a complete post package containing:

1. **Hook**: The opening line(s) optimized for the platform
2. **Full Post**: Complete text with formatting applied, ready to copy-paste
3. **Character Count**: Total characters with platform limit noted
4. **Content Style Used**: Which of the styles was applied
5. **Engagement Element**: End-of-post question or CTA
6. **CTA**: The specific call-to-action with format
7. **2 Alternative Hooks**: A/B testing options for the opening
8. **Hashtag Suggestions**: Platform-appropriate hashtags (if applicable)
9. **Posting Notes**: Best time to post, any platform-specific tips
10. **Autoplug Draft**: Pre-written first comment with additional value (for LinkedIn)
11. **Next Step**: "Use /write-hook to create hooks for your next post" or "Use /content-plan to plan your content calendar"
