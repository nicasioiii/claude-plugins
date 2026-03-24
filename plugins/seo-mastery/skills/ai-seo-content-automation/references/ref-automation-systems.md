# Automation Systems for SEO Content

## Hyper-Localized Service Pages (Gorrono)

### Strategy
Create dedicated pages for every suburb/city/locality you service. Example: "Plumbing services in Cobra", "Plumbing services in Brunswick", etc.

### Make.com Automation Flow
1. **Google Sheets** -- list of all location names (towns/cities/suburbs)
2. **Perplexity API call** -- researches each location (attractions, property types, population, top 5 FAQs)
3. **OpenAI completion #1** -- writes history section (100-150 words, referencing only Perplexity data)
4. **OpenAI completion #2** -- writes "what to do" section
5. **OpenAI completion #3** -- writes property types / services section
6. **OpenAI completion #4** -- writes 5-question FAQ section
7. **Google Docs** -- assembles all sections with proper H2 tags
8. **OpenAI completion #5** -- creates meta description from assembled content
9. **Google Sheets** -- logs location name, SEO title, meta description, doc link

### Why Segmented Sections (Not One-Shot)
- Consistent structure across all pages (identical section layout)
- Minimizes hallucination (each call references only Perplexity research)
- Reduces variance when creating 50-100+ pages
- Max tokens set to 350 per section for tight control

### Real-World Example
RE/MAX Malta: 80+ locality pages with this exact structure. Each page exists solely for local SEO: history, attractions, property info, FAQs.

### Time Savings
What takes a person one week manually runs in minutes.

---

## Interactive HTML Tools for SEO (Gorrono)

### Why Build Tools
1. Google leaked docs confirm on-page clicks are a ranking factor
2. AI Overviews decrease blue-link CTR by up to 45%
3. Calculators/quizzes/estimators CANNOT be answered in AI Overviews
4. Interactive content converts visitors to leads better than static content

### Build Workflow
1. Use custom GPT "HTML Web App Builder" to brainstorm tool ideas (input: niche URL or service description)
2. Quick competitive research -- anyone doing a similar tool? Can you do it better?
3. Use Gemini 2.5 Pro with Canvas enabled to build the tool
4. Paste initial code from idea GPT, tell Gemini to improve as pure HTML only
5. Iterate: screenshot errors, paste into Gemini for fixes
6. Style matching: screenshot your website, paste into Gemini, ask it to match
7. Copy final HTML, inject into new page on your website (embed/custom code block)
8. Debug: if styles bleed into page, tell Gemini to scope styles to injected component

### Example Tools Built
- SERP preview tool (title/meta/URL preview with character limits and truncation)
- Salary calculator (monthly/weekly/annual with tax calculations)
- Term life insurance premium estimator (age slider, term length dropdown, coverage amount)
- Mortgage calculator
- ROI estimators

### Key Insight
"These tools generate a lot of traffic and leads. I know from personal experience and from community members."

---

## Reddit Sniper Method (GMB Crush/Mateo)

### The Complete 4-Step Pipeline

**Step 1: Reddit Data Extraction**
- Enter specific keyword (service type + city) into Reddit Sniper GPT
- Tool extracts: thread content, user opinions, competitor mentions, pricing data
- Example keyword: "plumber Los Angeles" or "dog trainer Austin TX"
- Can analyze 10, 15, or even 20 threads at once for deeper coverage

**Step 2: Pain Point Mining**
Run extraction through dedicated pain point mining prompt. Outputs:
- Specific pain points with frequency
- Sentiment patterns (positive/negative/neutral)
- Exact language users use to describe problems
- Competitor mentions with context (praise/complaints)
- Pricing intelligence (what people expect to pay)
- Market gaps (what people want but cannot find)

**Step 3: Content Enhancement**
Run pain point data through content enhancement prompt. Generates:
1. **4-5 FAQs** based on real user pain points
2. **Conversion-focused CTAs** with stronger calls to action
3. **Comparison table** (your company vs anonymized competitors)
4. **"What to Know Before You Book" section** -- improves CRO and adds trust
5. **5 supporting content cluster topics** -- internal link targets for main page

### Step 4: AI-Optimized Content Creation
Final re-optimization to make content AI Overview ready:
- Keep original word count, force up to 4,000 tokens for detail
- Add 50-60 word summary snippet at top of page
- Prioritize clarity, confidence, semantic richness
- Include 3-4 Q&A entries in AI-extractable patterns
- Use natural phrasing (critical for AI systems)
- Voice matching rewrite: rewrite intro/CTA using Reddit thread tone

---

## Semantic Anchor Points (SAPs) -- GMB Crush

### What They Are
4-5 key phrases or facts from Reddit threads that become structural elements on the page.

### Four Usage Methods
1. **Use as H2 or H3 headings** -- helps AI Overview and ChatGPT recognize semantic structure and surface content as direct answers
2. **Write clear, focused content under each header** -- keep tightly aligned with heading, avoid vague copy
3. **Create internal links** -- link to these sections from top of page or other blog content using anchor links with matching IDs
4. **Optimize for featured snippets / AI cards** -- each SAP should answer a single user-intent question in 2-3 sentences

---

## Multi-Channel Repurposing from Reddit Data (GMB Crush)

### Google Ads
- 3-5 ad variations from user pain points and emotional triggers
- Paraphrased actual complaints or praise from threads
- Character limits enforced: 30-char headlines, 90-char descriptions
- 2-3 ad extension messages (sitelinks, callouts, snippets)
- Multi-location support with geo-targeted variations

### Facebook Ads
- 2-3 high-converting copy variations reflecting emotional tone from real users
- Short version (under 100 words) + long version (over 200 words)
- Structure: Hook > Pain > Bridge > Trust Builder > CTA
- Highlight objections, frustrations, trust gaps from Reddit data

### YouTube Shorts
- Huge SEO opportunity: Google shows 2 rows of 4 short videos per keyword = 8 slots
- Script structure: Hook (3 seconds) > Problem (Reddit complaint) > Solution > CTA
- Under 60 seconds, plain spoken, conversational
- Optional variation for TikTok/Facebook Reels

### Lead Magnets
- PDF using all Reddit insights
- Structure: cover page > introduction with surprising insight > top 3-5 pain points > solution framework > bonus FAQ/comparison > CTA page
- "Stop creating useless lead magnets. This method gives you real-value resources using the same language your audience speaks."

---

## The Reddit Data Extraction Loop

The process is iterative:
1. Extract data from 5-10 threads
2. Analyze for pain points, sentiment, competitors
3. Extract MORE threads for deeper coverage
4. Each round covers new ideas, topics, fresh data
5. Advantage compounds: every piece of content reflects real user language

This functions as micro market research by service type, product, and target location.

---

## Automated Blog-to-GBP Posts

### Integration
- When new blog posts publish, automatically create Google Business Profile posts
- Use Make.com or Zapier to trigger on RSS or webhook
- Format for GBP: short summary + link to full article
- Minimum 5 GBP posts per week (see local-seo skill)

---

## Perplexity Research Assistant Automation (Pierce)

### Workflow
- Use Perplexity with Pro Search for deep topic research
- Output as HTML for formatted delivery
- Feed research output into content generation pipelines
- Perplexity Sonar model used as default research engine in Custom Blog Writer V2

### For Keyword Research Context
Use Perplexity to research any topic before content creation. Outputs business overview with services, audience, competitive positioning.

### For Content Outlines (Pierce Method)
Perplexity analyzes target keyword and generates:
- Target word count to rank #1
- Complete page outline (SEO title, description, H1, all H2/H3/H4 sections)
- FAQ section placement and suggested questions
- Key phrases to target in each header
