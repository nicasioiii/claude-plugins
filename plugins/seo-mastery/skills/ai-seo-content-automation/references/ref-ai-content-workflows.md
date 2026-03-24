# AI Content Workflows (Complete)

## GPT Projects SEO Sidekick Setup (Gorrono)

### Data Files to Upload
1. **Business overview document** -- generate via Perplexity Pro Search research prompt. Covers services, target audience, competitive positioning
2. **Site map CSV** -- URL, title tag, meta description, H1, H2s for every page
3. **Keyword research spreadsheet** -- main keywords + sub-keywords with volume, CPC, difficulty
4. **Competitor analysis XLSX** -- ranked keywords, estimated monthly traffic, referring domains for 4-5 competitors
5. **Tone of voice document** -- writing style analysis from existing content samples
6. **Answer Socrates cluster CSVs** -- keyword clusters with aggregate volume and competition

### Three Core Analyses (Dedicated Prompts)
1. **Keyword and search intent audit** -- cross-reference keyword research against existing site map. Find intent mismatches and optimization opportunities
2. **Competitor and SERP gap analysis** -- identify keywords competitors rank for that you do not. Find untapped content opportunities
3. **Content architecture and 90-day roadmap** -- generate 10-20 blog ideas per content cluster, prioritized by difficulty and opportunity

### Model Selection Guide
| Task Type | Recommended Model | Reasoning |
|-----------|------------------|-----------|
| Analysis/strategy | O3 or O4-mini | Chain-of-thought reasoning for complex analysis |
| Content generation | GPT-4o | Best quality/cost balance for writing |
| HTML tools/apps | Gemini 2.5 Pro | Superior code generation, especially with Canvas |
| Research | Perplexity Sonar | Always use for research -- real-time web access |
| Blog outlines | Claude Sonnet | Strong at structured outlining |

### Cold Start Prompt
"I want to improve my website's SEO. I don't know where to start. With all the information you have in your knowledge base, what are some questions I should ask you?"

---

## Personalized Content with GPT Projects + Canvas (Gorrono)

### Tone of Voice Document Creation
1. Paste a LinkedIn post, blog post, or newsletter you like into a custom TOV GPT
2. GPT outputs detailed tone analysis: vocabulary, sentence structure, humor, formality
3. Download as TOV_document.txt
4. Upload to your copywriter GPT Project

### The Collaborative Workflow
1. Tell GPT the topic (or ask for ideas from site map gaps)
2. GPT asks follow-up questions: content type, format, word count, first-hand experiences to include
3. GPT provides rough outline for approval
4. Approved -> GPT creates first draft in Canvas (slide-out editor)
5. Select specific sections and request rewrites -- only that section changes
6. Ask GPT to review site map and suggest internal links
7. Adjust length, reading level, tone as needed
8. Final review: verify all internal links work, external sources are accurate

### Key Principle
"This isn't a set-and-forget. AI writes 80-90% of the content. You add your experience, your two cents." Canvas allows selective editing without regenerating the entire post.

---

## Machined AI Bulk Content Setup (Gorrono)

### Project Configuration
1. Create projects per client (agency model) or per content cluster (business)
2. Define topic as narrow as possible: "Local SEO strategies for financial advisors" not "SEO"
3. Define audience precisely: "financial advisors in the US looking to start doing their own local SEO"
4. Choose V3 engine (enable experimental settings if not visible)
5. Choose autopilot (AI picks keywords) or manual (paste your own keyword list)
6. Select cluster size (medium recommended for most use cases)

### Critical Pre-Writing Steps (Do Not Skip)
1. **Review all generated titles** -- delete irrelevant ones. Machined auto-interlinks, so irrelevant titles create broken internal links
2. **Set content type per article** -- ultimate guide, informational, listicle, roundup, review, comparison, how-to
3. **Add custom briefs per article** -- inject your experience, unique insights, specific points to cover. This single step separates quality from generic slop
4. **Create/select voice profile** -- analyze 1-3 writing samples for style replication
5. **Enable AI research** -- especially for YMYL topics (health, finance, legal)
6. **Add directed research URLs** -- point to your own relevant blog posts and pages
7. **Choose image style** -- Stability AI with preferred aspect ratio
8. **Set internal linking** to "opportunistic"
9. **Select model** -- 4o-mini for volume (fractions of a cent), O1 for quality (~$0.50/post)

### Post-Writing QA
- Blue links = external source citations (auto-verified for YMYL)
- Orange/yellow links = internal cluster links (auto-generated)
- Edit directly in platform: add CTAs, custom sections, personal experience
- Export as markdown/HTML or publish direct to WordPress/Webflow

### Publishing Strategy
- 5-10 articles at a time (because they interlink within the cluster)
- Use Link Whisperer for automatic internal linking as posts publish
- Stagger publishing over 1-2 weeks rather than all at once

---

## Custom Blog Writer V2 (Gorrono)

### Architecture
Google Sheets + Apps Script connecting to:
- **OpenRouter** (one API key for all LLMs -- GPT, Claude, Gemini, Mistral, etc.)
- **Fal.ai** (one API key for all image models -- Flux, SDXL, etc.)

### 9-Step Workflow (All From Google Sheets)
1. Enter keyword, blog type (informational, listicle, etc.), additional context
2. **Generate research summary** -- uses Perplexity Sonar model (always)
3. **Generate blog outline** -- choose any model via OpenRouter (e.g., Claude Sonnet 3.5)
4. **Add internal + external links** -- manually input or auto-suggest
5. **Generate full blog post** -- creates formatted Google Doc in your Drive
6. **Generate image prompt** -- describes ideal hero image
7. **Generate image** -- Flux 1.1 Pro Ultra via Fal.ai
8. **Generate alt tag** -- SEO-optimized alt text
9. **Generate meta description** -- under 160 characters with keyword

### Multi-Language Support
Change language in settings tab. Entire output (including research step) adapts to target language.

### Cost Per Blog Post
~$0.12 total including image generation.

---

## Voice-Note-to-Blog Pipeline (Gorrono)

### Flow
1. Record a voice note about a topic you know well
2. Automation transcribes the recording
3. AI structures transcription into SEO-optimized blog post
4. Outputs to Google Doc or directly to CMS

### Why This Matters for E-E-A-T
- Captures authentic expertise and first-hand experience
- AI handles formatting, SEO structure, and polish
- The fastest way to inject real experience into content
- Especially valuable for YMYL topics where demonstrating personal experience is critical
- Voice notes capture details and anecdotes you would never remember to type

---

## Claude MCP + DataForSEO Integration (Gorrono, Pierce)

### Setup
1. Download Claude Desktop (Mac or Windows)
2. Install Node.js
3. Open Claude Settings > Developer > Edit Config File
4. Paste DataForSEO MCP server configuration JSON
5. Insert DataForSEO email and API password
6. Restart Claude

### What This Enables
- Natural language conversation with real-time SEO data
- Ask: "Tell me all keywords this website ranks for and what long-tail keywords they should target"
- Build custom SEO dashboards with data visualizations
- Run competitive analysis via conversation
- Claude Projects + MCP = persistent SEO advisor with live data access

### Preview of the Future
This is what SEO tools will look like: conversational interfaces with real-time data, replacing traditional dashboard-based tools.

---

## AI Content Quality Guardrails (Synthesized)

### The Non-Negotiable Rules
1. **Never set-and-forget** -- AI writes 80-90%, you add experience and review
2. **Custom briefs per article** -- generic keyword + "write about this" = slop
3. **Voice profiles** -- train on 20+ post examples for social, 5+ blog posts for long-form
4. **Fact verification** -- CNET published AI-written, human-fact-checked articles still riddled with errors
5. **Differentiation** -- if everyone publishes the same AI content, none ranks
6. **E-E-A-T signals** -- real experience, real author bios, real data

### Model Selection by Task
| Task | Model | Cost |
|------|-------|------|
| Research | Perplexity Sonar | Included in API |
| Blog outlines | Claude Sonnet | ~$0.003/article |
| Long-form writing | GPT-4o / O1 | $0.01-0.50/article |
| Image generation | Flux 1.1 Pro Ultra via Fal.ai | ~$0.02/image |
| HTML tools | Gemini 2.5 Pro | Free (Canvas) |
| Analysis/strategy | O3 / O4-mini | Varies |
