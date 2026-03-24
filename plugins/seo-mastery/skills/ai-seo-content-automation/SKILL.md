---
name: "AI SEO & Content Automation"
description: |
  MANDATORY TRIGGERS: AI content, content automation, GPT Projects, Machined AI,
  custom blog writer, voice to blog, voice note pipeline, Make.com SEO,
  hyper-localized pages, interactive HTML tools, calculators for SEO, AI writing tools,
  Reddit Sniper, Reddit data extraction, content at scale, AI SEO workflow,
  OpenRouter, Fal.ai, DataForSEO MCP, Claude MCP, Perplexity research,
  automated blog posts, AI content quality, content automation system

  FOR: Anyone using AI tools and automation systems to create SEO content at scale.
  Covers GPT Projects SEO Sidekick, Machined AI bulk content, Custom Blog Writer V2,
  voice-note-to-blog pipeline, hyper-localized page automation, interactive tool building,
  Reddit Sniper method for content intelligence, and AI content quality guardrails.

  Do NOT use for:
  - Manual content writing process -> use content-production
  - Programmatic SEO site architecture -> use directory-programmatic-seo
  - GA4/GTM tracking setup -> use seo-analytics-reporting
  - Schema markup generation -> use schema-entity-optimization
---

# AI SEO & Content Automation

You are an AI-powered SEO content automation specialist. Help users build and operate systems for creating SEO content at scale using AI tools, automation platforms, and data-driven workflows. Be specific with tool names, model selections, cost estimates, and step-by-step setup instructions. Always emphasize quality guardrails.

---

## Core Philosophy

**"This is an extension of your writing, not a replacement."** Every AI content system in this skill operates on the same principle: AI handles 80-90% of the work (research, structure, drafting, formatting). You add your experience, unique insights, and quality control. Set-and-forget AI content is a recipe for penalties.

**Three content types that rank in the AI era (Gorrono):**
1. **Topic clusters and pillar content** -- comprehensive coverage that signals expertise
2. **Personalized/expert content** -- content only YOU can write (your data, your case studies)
3. **Interactive content** (calculators, quizzes, tools) -- cannot be answered by AI Overviews, forces click-throughs, Google leaked docs confirm on-page clicks are a ranking factor

---

## When to Read Reference Files

Read **ref-ai-content-workflows.md** when:
- Setting up GPT Projects SEO Sidekick
- Configuring Machined AI for bulk content
- Building the Custom Blog Writer V2 in Google Sheets
- Setting up the voice-note-to-blog pipeline
- Selecting AI models for different SEO tasks
- Cross-reference: content-production for manual quality standards that AI content must meet

Read **ref-automation-systems.md** when:
- Building hyper-localized service pages with Make.com
- Creating interactive HTML tools for SEO
- Implementing the Reddit Sniper method
- Setting up multi-channel content repurposing
- Cross-reference: local-seo for GBP posting automation

---

## GPT Projects SEO Sidekick (Gorrono)

### Setup (One-Time)
1. Create a ChatGPT Project
2. Upload these data files:
   - Business overview document (generate via Perplexity research prompt)
   - Site map CSV (URL, title tag, meta description, H1, H2s for every page)
   - Keyword research spreadsheet (keywords + volume, CPC, difficulty)
   - Competitor analysis XLSX (4-5 competitors with ranked keywords, traffic, referring domains)
   - Tone of voice document
   - Answer Socrates cluster CSVs

### Three Core Analyses
1. **Keyword and search intent audit** -- cross-reference keywords against site map for intent mismatches
2. **Competitor and SERP gap analysis** -- find keywords competitors rank for that you do not
3. **Content architecture and 90-day roadmap** -- generate 10-20 blog ideas per content cluster, prioritized

### Model Selection
| Task | Model | Why |
|------|-------|-----|
| Analysis and strategy | O3 or O4-mini | Reasoning tasks need chain-of-thought |
| Content generation | GPT-4o | Best balance of quality and cost |
| HTML tool building | Gemini 2.5 Pro | Best at generating complex HTML/CSS/JS |

### Starting Prompt
"I want to improve my website's SEO. I don't know where to start. With all the information you have in your knowledge base, what are some questions I should ask you?"

---

## Machined AI Bulk Content (Gorrono)

### Setup
1. Create projects per client (agency) or per content cluster (business)
2. Define topic narrowly (e.g., "Local SEO for financial advisors" not "SEO")
3. Define audience precisely
4. Choose V3 engine with experimental settings enabled
5. Choose autopilot (AI picks keywords) or manual (paste your own)
6. Select cluster size (medium recommended)

### Critical Pre-Writing Steps
1. Review ALL generated titles -- delete irrelevant ones (prevents broken interlinks)
2. Set content type per article: ultimate guide, informational, listicle, roundup, review, comparison, how-to
3. **Add custom briefs per article** -- inject your experience and unique insights. This is what separates quality from slop
4. Create/select custom voice profile (analyze 1-3 writing samples)
5. Enable AI research (especially for YMYL topics)
6. Add directed research URLs (your own relevant blog posts)
7. Choose image style and aspect ratio
8. Set internal linking to "opportunistic"
9. Select model: 4o-mini = fractions of a cent; O1 = ~$0.50/post but higher quality

### Post-Writing
- Blue links = external source citations (auto-verified for YMYL)
- Orange links = internal cluster links (auto-generated)
- Edit directly in platform -- add CTAs, custom sections, your experience
- Export markdown/HTML or publish to WordPress/Webflow via CMS connection

### Publishing Cadence
5-10 articles at a time (because they interlink). Use Link Whisperer for auto internal linking.

### Cost
~$0.50/article with O1, fractions of a cent with 4o-mini.

---

## Custom Blog Writer V2 (Gorrono)

### Architecture
Google Sheets + Apps Script + OpenRouter (all LLMs with one API key) + Fal.ai (all image models with one API key)

### Workflow (All From Google Sheets)
1. Enter keyword, blog type (informational, etc.), additional context
2. Generate research summary (Perplexity Sonar model -- always for research)
3. Generate blog outline (choose any model via OpenRouter, e.g., Claude Sonnet)
4. Add internal + external links
5. Generate full blog post (creates formatted Google Doc in your Drive)
6. Generate image prompt
7. Generate image (Flux 1.1 Pro Ultra via Fal.ai)
8. Generate alt tag
9. Generate meta description

### Multi-Language Support
Change language in settings tab -- entire output (including research) adapts.

### Cost
~$0.12 per blog post (including image generation).

---

## Voice-Note-to-Blog Pipeline (Gorrono)

### Flow
Record voice note about a topic > automation transcribes > AI structures into SEO-optimized blog post > outputs to Google Doc/CMS

### Why It Matters
- Captures authentic expertise and first-hand experience (E-E-A-T signals)
- AI handles formatting, SEO structure, and polish
- Fastest way to inject real experience into AI-generated content
- Especially valuable for YMYL topics where personal experience matters

---

## Personalized Content with GPT Projects + Canvas (Gorrono)

### Setup
1. Create tone-of-voice document: paste a writing sample into a custom TOV GPT for analysis
2. Download as TOV_document.txt
3. Create GPT Project "Copywriter [Business Name]"
4. Upload TOV document + site map CSV
5. Add copywriting system prompt

### The Collaborative Writing Workflow
1. Tell GPT the topic (or ask for ideas)
2. GPT asks follow-ups: content type, format, word count, first-hand experiences
3. GPT provides rough outline
4. Once approved, first draft in Canvas (slide-out editor)
5. Select specific sections for rewrites -- only that section changes
6. GPT reviews site map and suggests internal links
7. Adjust length, reading level, tone
8. Final review: verify internal links and external sources

---

## Interactive HTML Tools for SEO (Gorrono)

### Why Tools Are an SEO Power Play
1. Google leaked docs: clicks on a page are a ranking factor
2. AI Overviews decrease blue-link CTR by up to 45%
3. Calculators/quizzes CANNOT be answered in AI Overviews -- users must click through
4. Interactive content converts visitors to leads better than static content

### Build Workflow
1. Use custom GPT "HTML Web App Builder" to brainstorm tool ideas
2. Quick competitive research -- anyone doing similar?
3. Use Gemini 2.5 Pro with Canvas to build the tool
4. Iterate: screenshot errors, paste into Gemini for fixes
5. Style match: screenshot your website, ask Gemini to match
6. Copy final HTML, inject into page on your website
7. Debug: if styles bleed, tell Gemini to scope styles to injected component

### Example Tools
- SERP preview tool (title/meta/URL with character limits)
- Salary calculator (monthly/weekly/annual with tax)
- Insurance premium estimator (sliders + dropdowns)

---

## Reddit Sniper Method (GMB Crush/Mateo)

### The Complete 4-Step Pipeline

**Step 1: Extract Reddit Thread Data**
- Enter specific keyword (service + city) into Reddit Sniper GPT
- Extracts thread content, user opinions, competitor mentions, pricing data

**Step 2: Pain Point Mining**
- Run extraction through pain point mining prompt
- Outputs: pain points, sentiment patterns, language used, competitor mentions, pricing intelligence

**Step 3: Content Enhancement**
- Generate: 4-5 FAQs from real user pain points, conversion-focused CTAs, comparison tables, "What to Know Before You Book" sections, 5 supporting cluster topics

**Step 4: AI-Optimized Content Creation**
- 50-60 word summary snippet at top of page
- 3-4 Q&A entries in AI-extractable patterns
- Voice-matched rewrite using Reddit language
- Semantic anchor points (4-5 key phrases as H2/H3 headings)

### Semantic Anchor Points (SAPs)
4-5 key phrases from Reddit threads become structural page elements:
1. Use as H2/H3 headings
2. Write focused content under each (tightly aligned)
3. Create anchor-linked internal links
4. Optimize each for featured snippets (2-3 sentence answers)

### Multi-Channel Repurposing
Same Reddit data powers: Google Ads (3-5 variations), Facebook Ads (short + long), YouTube Shorts (under 60 seconds), lead magnet PDFs.

---

## AI Content Quality Guardrails

### The Non-Negotiable Rules
1. **Never set-and-forget** -- AI writes 80-90%, you add experience and review
2. **Custom briefs per article** -- inject unique insights, not just keywords
3. **Voice profiles** -- train on 20+ examples for social, 5+ blog posts for long-form
4. **Fact verification** -- AI is confidently wrong. Verify all stats and claims
5. **Differentiation** -- if 100 sites publish the same AI content, none ranks. Add what only you know
6. **E-E-A-T signals** -- inject real experience, real author bios, real data

### Content Homogenization Risk (Maddy Osman)
AI produces the most likely answer, not the best one. Everyone using AI for the same topics gets identical outputs. Your competitive advantage is what you add on top of AI output.
