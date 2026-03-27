# Social Content Mastery v2.0.0 -- Routing & Operations

## Plugin Overview

**social-content-mastery v2.0.0** is a complete organic social media content creation system for personal brands and creators. Built from 8 extraction files covering 20+ courses across ~250 hours of instruction from 25+ instructors including Mino Lee, Dickie Bush & Nicolas Cole, Gusten Sun, Colin & Samir, Kallaway, Nicklas Christl, Sunny Lenarduzzi, Parker Walbeck, Jimmy Farley, Ryan Magin, JT Barnett, JK Molina, David Perell, Nathan Chan, Vanessa Lau, InstaCoach Mike, and others.

The system contains **18 skills** organized by workflow stage (5 platform-specific growth skills replacing the old cross-platform platform-strategy and publish-grow), reference files with deep tactical content, and **14 slash commands** for guided workflows.

**Workflow:** Brand Foundation > Content Strategy > Create (Write/Film/Edit) > Publish & Grow > Monetize

---

## OUT OF SCOPE (Delegate to Other Plugins)

| Topic | Delegate To |
|---|---|
| Paid advertising / media buying | `paid-ads-mastery` |
| Cold outreach DMs / cold email | `cold-outbound-mastery` |
| Email marketing sequences / newsletters | `email-marketing-mastery` |
| Landing page CRO / sales page copy | `cro-copywriting-mastery` |
| Web / UI design | `design-mastery` |
| SEO strategy | `seo-mastery` |

---

## Skill Routing Table (All 18 Skills)

### Stage 1: BRAND FOUNDATION

| Skill | Route When User Says... | Do NOT Use When... |
|---|---|---|
| `brand-foundation` | "brand," "niche," "positioning," "who am I," "pillars," "avatar," "ideal viewer," "brand identity," "visual identity," "brand DNA," "archetype," "mission statement," "what makes me unique," "who do I serve," "what should I post about" | They need a content calendar (-> content-strategy) or platform-specific profile optimization (-> platform skill) |

### Stage 2: CONTENT STRATEGY

| Skill | Route When User Says... | Do NOT Use When... |
|---|---|---|
| `content-strategy` | "plan," "calendar," "ideas," "what to post," "content mix," "brainstorm," "idea generation," "posting schedule," "repurpose," "batch," "content format," "how often," "cadence," "content multiplication," "content buckets" | They need to write a hook (-> write-hooks) or write a script/post (-> write-scripts) |

### Stage 3: CREATE -- WRITING

| Skill | Route When User Says... | Do NOT Use When... |
|---|---|---|
| `write-hooks` | "hook," "opening," "first line," "scroll stop," "first 2 seconds," "text hook," "hook template," "CGOVE," "alignment," "curiosity loop," "contrast" | They need a full script or post body (-> write-scripts) |
| `write-scripts` | "script," "write a post," "outline," "structure," "caption," "CTA," "storytelling," "AIDA," "writing rhythm," "post ending," "write for me," "draft," "copywriting" | They need only a hook (-> write-hooks) or content ideas (-> content-strategy) |

### Stage 4: CREATE -- PRODUCTION

| Skill | Route When User Says... | Do NOT Use When... |
|---|---|---|
| `film-video` | "film," "camera," "lighting," "equipment," "audio," "framing," "B-roll," "warmup," "recording" | They need editing (-> edit-video) |
| `edit-video` | "edit," "editing," "pacing," "jump cuts," "captions," "color grading," "music," "sound design," "VFX," "transitions" | They need to write a script (-> write-scripts) |
| `produce-visual-content` | "carousel," "infographic," "thumbnail," "visual design," "graphic," "design principles" | They need video editing (-> edit-video) |

### Stage 5: PUBLISH & GROW -- Platform-Specific

| Skill | Route When User Says... | Do NOT Use When... |
|---|---|---|
| `instagram-growth` | "Instagram," "IG," "Reels," "ACAB formula," "Instagram algorithm," "hashtags" (IG context), "S4S," "share for share," "Instagram stories," "faceless reels," "trending audio" | They need general content strategy (-> content-strategy) or hook writing (-> write-hooks) |
| `linkedin-growth` | "LinkedIn," "LinkedIn algorithm," "LinkedIn profile," "LinkedIn post," "LinkedIn hook templates," "authority marketing," "clarity checklist," "LinkedIn SEO" | They need general hook writing with CGOVE (-> write-hooks) |
| `tiktok-growth` | "TikTok," "TikTok algorithm," "FYP," "TikTok trends," "Generally Specific," "Anti-CUB," "context captions," "two-hook system," "content boxes" | They need general content strategy (-> content-strategy) |
| `twitter-growth` | "Twitter," "X," "tweet," "thread," "Atomic Essay," "tweet psychology," "bow types," "wordplay," "problem-pivot," "10 Club," "digital writing" | They need general writing help (-> write-scripts) |
| `youtube-growth` | "YouTube," "YouTube algorithm," "C.O.D.E.," "H.O.T. formula," "YouTube SEO," "subscriber," "keyword ownership," "batch recording," "60-day launch plan" | They need general filming help (-> film-video) |

### Stage 6: MONETIZE

| Skill | Route When User Says... | Do NOT Use When... |
|---|---|---|
| `monetize-content` | "money," "monetize," "sell," "coaching," "product," "offer," "lead magnet," "pricing," "revenue," "digital product" | They want brand deals specifically (-> brand-partnerships) |
| `brand-partnerships` | "brand deal," "sponsorship," "pitch deck," "partnership," "UGC," "influencer pricing" | They need general monetization strategy (-> monetize-content) |
| `community-building` | "community," "group," "membership," "Facebook group," "School," "1000 true fans" | They need monetization (-> monetize-content) |
| `ghostwriting-freelance` | "ghostwriting," "ghostwriter," "freelance writing," "client acquisition," "landing clients," "ghostwriting pricing," "writing for clients," "content agency," "writing business," "freelance rates," "productized service" | They want to create content for their OWN accounts (-> write-scripts) or monetize through their own products (-> monetize-content) |

### CROSS-CUTTING

| Skill | Route When User Says... | Do NOT Use When... |
|---|---|---|
| `ai-content-workflow` | "AI," "ChatGPT," "Claude," "prompt," "automate content," "AI writing," "Sacred Hours" | They need manual content strategy (-> content-strategy) |
| `publish-optimize` | "analytics," "retention," "A/B test," "underperforming," "why no views," "metrics," "benchmarks," "content audit," "posting frequency," "best time to post," "engagement rate," "reach," "cross-platform," "repurpose," "scheduling" | They need platform-specific algorithm mechanics (-> platform skill) or writing hooks/scripts (-> write-hooks, write-scripts) |

---

## Ambiguous Request Decision Tree

```
IF request mentions specific platform ("LinkedIn," "Instagram," "TikTok," "Twitter/X," "YouTube")
  AND request is about growth/algorithm/followers -> route to platform-specific skill
  AND request is about profile setup -> route to platform-specific skill + brand-foundation
  AND request is about content creation for that platform -> route by content type + platform skill

IF request mentions "hook" or "opening" or "first line" or "scroll stop" -> write-hooks
IF request mentions "script" or "structure" or "write a post" or "outline" -> write-scripts
IF request mentions "film" or "camera" or "lighting" or "equipment" -> film-video
IF request mentions "edit" or "editing" or "pacing" or "B-roll" or "music" -> edit-video
IF request mentions "carousel" or "infographic" or "thumbnail" or "visual design" -> produce-visual-content
IF request mentions "grow" or "followers" or "views" or "engagement" or "algorithm" -> platform skill if specified, otherwise ask which platform
IF request mentions "money" or "monetize" or "sell" or "coaching" or "product" or "offer" -> monetize-content
IF request mentions "brand deal" or "sponsorship" or "pitch deck" or "partnership" -> brand-partnerships
IF request mentions "community" or "group" or "membership" -> community-building
IF request mentions "AI" or "ChatGPT" or "Claude" or "prompt" or "automate content" -> ai-content-workflow
IF request mentions "brand" or "niche" or "positioning" or "who am I" or "pillars" -> brand-foundation
IF request mentions "plan" or "calendar" or "ideas" or "what to post" or "content mix" -> content-strategy
IF request is broad ("help me with social media" / "I want to be a creator") ->
  Ask: "Which area do you need help with?
  (A) Define your brand and strategy
  (B) Create content (write/film/edit)
  (C) Grow your audience on a specific platform
  (D) Monetize your following"
ELSE -> route to brand-foundation (earliest workflow stage)
```

---

## Cross-Reference Map with Trigger Conditions

| Source Skill | References | Trigger Condition |
|---|---|---|
| `brand-foundation` | `content-strategy` | Brand pillars defined, avatar documented |
| `brand-foundation` | any platform skill | User asks for profile optimization |
| `content-strategy` | `write-hooks` | Content plan ready, hook needed |
| `content-strategy` | `write-scripts` | Content plan ready, script needed |
| `write-hooks` | `write-scripts` | Hook written, need full script |
| `write-hooks` | `write-hooks` (self) | Hook underperforming after posting |
| `write-scripts` | `film-video` | Script complete for video content |
| `write-scripts` | `produce-visual-content` | Script complete for visual/carousel content |
| `film-video` | `edit-video` | Footage captured, ready for post-production |
| `edit-video` | `publish-optimize` | Video exported, ready to publish |
| `produce-visual-content` | `publish-optimize` | Visual asset created, ready to publish |
| any platform skill | `write-hooks` | Content underperforming 2+ weeks, hook diagnosis |
| `instagram-growth` | `tiktok-growth` | Repurpose IG content to TikTok (or vice versa) |
| `linkedin-growth` | `twitter-growth` | Creating text-based content for both |
| `youtube-growth` | platform skills (short-form) | YouTube Shorts or distribution to short-form |
| `monetize-content` | `brand-partnerships` | User wants brand deals specifically |
| `monetize-content` | `community-building` | User wants community-led revenue |
| `brand-partnerships` | `brand-foundation` | Need brand definition first |
| Any skill | `ai-content-workflow` | User wants to accelerate with AI tools |

---

## Execution Priority Order

When multiple skills apply, resolve in this order:

```
brand-foundation > content-strategy > write-hooks > write-scripts >
film-video > edit-video > produce-visual-content >
instagram-growth > linkedin-growth > tiktok-growth > twitter-growth > youtube-growth >
publish-optimize > monetize-content > brand-partnerships > community-building > ghostwriting-freelance
```

Platform-specific skills override cross-platform skills when the user has specified their platform.

---

## Command Inventory (14 Commands)

| Command | Description | Skills Activated |
|---|---|---|
| `/build-brand` | Interactive brand foundation builder | `brand-foundation` |
| `/content-plan` | Generate 30-day content calendar | `content-strategy` |
| `/write-hook` | Write and optimize a hook for any platform | `write-hooks` |
| `/write-script` | Build a complete video script or social post | `write-scripts`, `write-hooks` |
| `/write-post` | Write a platform-native post | `write-scripts`, `write-hooks`, platform skill |
| `/audit-content` | Diagnose underperforming content | `write-hooks`, platform skill |
| `/optimize-profile` | Platform-specific profile audit and optimization | platform skill, `brand-foundation` |
| `/grow-audience` | Platform-specific growth plan with 30/60/90-day milestones | platform skill |
| `/build-pitch-deck` | Create brand partnership pitch deck | `brand-partnerships` |
| `/create-lead-magnet` | Design and outline a lead magnet | `monetize-content` |
| `/film-checklist` | Pre-production planning and filming checklist | `film-video` |
| `/edit-video` | Guided video editing workflow | `edit-video` |
| `/monetize-plan` | Create a personalized monetization plan | `monetize-content` |
| `/ai-content` | AI-assisted content creation | `ai-content-workflow`, `write-scripts` |

---

## Instructor Disagreement Resolutions

### Posting Frequency
Daily for first 100 days. After proven quality: YouTube 1x/week, TikTok 1-3x/day, LinkedIn 3-5x/week, Twitter daily, Instagram 1x/day.

### Niche Breadth
Platform-dependent. YouTube/LinkedIn reward specificity. TikTok/Instagram reward broad hooks with specific value. The "Generally Specific" framework reconciles: broad appeal in hooks, deep specificity in advice.

### Hashtags
Minor signal, not a growth lever. 3-5 on Instagram (under 5K followers). On TikTok, for geo-targeting or skip. Never spend more than 2 minutes.

### Production Quality
Clean audio + good lighting + valuable content. Overproduction creates distance. Audio quality is the single most impactful element.

### Shadow Bans
Instagram has confirmed shadow-restricting (check Account Status). TikTok has not. In both cases: keep posting quality content and check for policy violations.
