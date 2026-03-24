# GEO Fundamentals: How AI Search Engines Select Sources

Reference file for the `geo-ai-search-optimization` skill. Covers the mechanics of how ChatGPT, Perplexity, Google AI Overviews, Gemini, and Grok discover, evaluate, and cite web content.

---

## How ChatGPT Selects Sources (Nick Lafferty / Profound -- 250M responses, 4B citations analyzed)

### The Hybrid Index

ChatGPT switched from Bing index to a SERP API-based **hybrid index** with only 19% overlap with Google results. This means 81% of ChatGPT citations come from pages that are NOT in Google's traditional top results.

ChatGPT uses **WebGPT** (a model trained in 2021) to pre-filter SERP API results before crawling. WebGPT decides whether to fetch a page based solely on:
- URL structure and slug
- Title tag
- Meta description

If any of these three elements fail to signal relevance, the page is never fetched -- regardless of content quality.

### Semantic URL Advantage

Pages with semantic, natural-language URLs get **11.4% more citations** (comparison of top 50K vs bottom 50K cited pages). Guidance: use 5-7 word descriptive slugs.

**Good:** `/best-business-credit-cards-startups-2026`
**Bad:** `/p/12847?cat=finance&ref=nav`

### Meta Description Spoiling Strategy

Highly cited pages put the answer directly in the meta description. This is called "spoiling" because you give away the conclusion upfront.

**Example:** Instead of "Find out which business credit card is right for you," write "The best business credit card for startups is [Brand X] because of its 2% cashback and no annual fee."

WebGPT reads this meta description and determines the page contains a direct, useful answer -- increasing the likelihood of fetching and citing it.

### Recency Bias

ChatGPT appends the current year to 20-30% of its fan-out queries sent to the SERP API. This systematic year-appending means:
- Having the current year in your title/H1 significantly increases citation probability
- New content can be cited within days (1840 & Co case study: published and top-cited within one week)
- Evergreen content without date signals gets deprioritized for time-sensitive queries

### Format Preferences

25% of all AI search citations (from 2.6B citations analyzed) are listicles and comparative content -- a 2x skew toward these formats. ChatGPT preferentially selects pages that have already done the comparison work rather than assembling comparisons from multiple sources.

### Position Distribution

Google positions 5-10 get cited at similar rates to positions 1-3 in ChatGPT. This flips the traditional click-curve model where top 3 dominate human clicks. Implication: ranking on page 1 (anywhere) may be sufficient for AI search visibility.

### Citation Volume Changes

- After GPT-5 launch: referral traffic from ChatGPT dropped 52%
- Reddit citations increased 87%, Wikipedia increased 62% after GPT-5
- ChatGPT citations dropped from average 12 per response to 4-5 after September 2025 model update
- Trend: fewer citations per response but potentially higher-quality/more-targeted ones

### Reddit Effect

Reddit commenting (organic, not shilling) produced a 5% increase in LLM visibility for one customer. This is a low-effort, high-signal strategy because LLMs weight Reddit content heavily due to its training data representation.

---

## Source Diversity Across LLMs (Malte Landwehr / PKI -- 1,000 B2B SaaS prompts, 30 days)

### The Core Finding

Different LLMs cite **different pages AND different domains** for the same prompts. Some URLs rank top-2 in all LLMs, but many are top in one and absent from top-10 in others. There is no single optimization strategy that works across all platforms.

### Platform-Specific Review Preferences

| Platform | Review Source Preferred |
|----------|----------------------|
| Google AI Overviews / AI Mode | Yelp (food), G2 (software) |
| ChatGPT | Trustpilot |
| Perplexity | Varies by vertical |

**TikTok and Facebook** only appear in Google AI Overviews/AI Mode citations. They never appear in ChatGPT or Perplexity top-10 results.

### Paid Advertorials Being Cited

Paid advertorials on news sites are being cited by LLMs as authoritative sources. Case study: a competitor in insurance was #1 most cited source using advertorials from a large German newspaper.

This creates an ethically gray but currently effective shortcut: you can purchase placement in editorial content that LLMs then treat as organic, authoritative citations.

### Affiliate Commission Manipulation

If a news publisher's commercial content listicle is already being cited by LLMs, offering that publisher a higher affiliate commission can incentivize them to include your brand in the article. The LLM citation value (brand visibility, referral traffic) often exceeds the affiliate cost.

### Retail Media Influence

Retail media offerings on ecommerce sites can influence LLM citations. If an online shop's retail media includes category text mentioning your brand, LLMs may pick up the mention and cite it as brand context.

### Self-Inclusion Case Study

Financial services client went from 0% to 23% mention rate in Perplexity by adding themselves to their own competitor comparison article. They were already the top-cited source domain but were not mentioned as a brand within the comparison content itself. Simply listing themselves alongside competitors fixed the gap.

### Grok's Twitter Dependence

Grok relies incredibly heavily on X/Twitter. In one analyzed case, Grok used 25 websites plus one tweet, and almost word-for-word cited the tweet while ignoring the website content. For Grok visibility, maintaining active, informative X/Twitter presence is disproportionately important.

---

## Crawler Analytics (Gijs de Groot / PromptWatch)

### Three ChatGPT Bot Types

1. **Citation bot** -- handles real-time user queries. Most important for visibility
2. **Search bot** -- operates during the "searching the web" phase
3. **Training bot** -- collects data for model training

The citation bot is what drives immediate visibility. Optimize for this bot first.

### Most Crawled Page Types by AI Bots

1. Homepage
2. Listicles
3. Statistics and unique data pages
4. Free tools
5. Downloadable content (PDFs, programs)

### Technical Requirements for High Citation

- No JavaScript runtime required (AI crawlers do not interact with JS)
- Server response time under 300ms
- Static pages preferred over dynamically rendered content

### AI Search Click-Through Rates

| Page Type | CTR from AI Search |
|-----------|-------------------|
| Average across all pages | 0.1% |
| Purchase/pricing pages | ~0.5% |
| Homepage | ~0.5% |
| Free tools | Highest CTR |

### llms.txt Assessment

llms.txt has **no measurable impact** in PromptWatch data. Structured data (schema) is used as metadata to assess content usefulness instead. Standard robots.txt works fine for LLM crawlers.

### URL-First Selection Process

AI models look at URL slugs FIRST to select an initial 10 candidate pages, then analyze content to pick the top 3. This reinforces the importance of semantic, descriptive URLs.

### Top-of-Funnel Content Warning

Top-of-funnel informational content is already in LLM training data. LLMs answer these questions without citations. Focus on **unique data sources** that force LLMs to cite you: proprietary statistics, original research, fresh comparison data, pricing information.

### Quora and LinkedIn

- Quora at 0.5% of Google AI Overview citations is significant
- Don't only focus on Reddit (1.3%) -- diversify across community platforms
- LinkedIn Pulse is a "sneaky good" place for AI search optimization

---

## Michael King's AI Search Framework (iPullRank Keynote)

### Deterministic to Probabilistic

Traditional search was deterministic: same query, same results. AI search is probabilistic: same query can produce different results each time. This fundamentally changes how we measure and optimize.

### Content Ecosystem Model

AI search answers come from a content ecosystem, not single pages. Think "raffle tickets" where you want as many entries as possible. This means distributing content and brand mentions across:
- Your own website (multiple relevant pages)
- Reddit threads
- YouTube videos
- LinkedIn posts
- Review platforms
- Industry publications

### Hyper-Personalization

Google and ChatGPT are doing hyper-personalization via vector representations of users based on Gmail, purchase history, and browsing behavior. Two users asking the same question may see different sources cited. Brand familiarity becomes a ranking signal at the individual user level.

### Application Integrations

Application integrations (e.g., Zillow's ChatGPT app, apartment searches in Gemini) dramatically change visibility. These integrations bypass traditional rankings entirely. Monitor whether your vertical has LLM application integrations and pursue them.

### The Measurement Reframe

AI search channels are branding channels, not performance channels. Impressions matter more than clicks. If clicks-focused, track rankings + clicks. If brand-focused, track brand visibility (brand mentions, not just URL appearances).

### Wikipedia Traffic Insight

Wikipedia traffic **increased** after ChatGPT launched (users fact-checking AI) but **decreased** after AI Overviews launched. AIOs are the real traffic killer for informational content, not standalone LLMs.

### AI Overview Traffic Impact

Predicted and confirmed AIO traffic loss: 20-60% depending on vertical. Only 1% of users click on links in AI Overviews (Pew Research). Google refuted this without sharing data.

### The Industry Warning

The SEO community saying "it's just SEO" is having a Blockbuster-vs-Netflix moment. SEO still works but there is a better version emerging. Proposed reframe: **"Relevance Engineering"** -- the confluence of AI, information retrieval, UX, content strategy, and digital PR.

---

## AI Overview Prevalence Data (Tom Capper / Moz, STAT)

### Growth Trajectory

- January 2025: 11% of US commercial SERPs
- October 2025: 19% of US commercial SERPs
- UK started lower but caught up
- EU went from 0% to matching highest markets in months

### YMYL Has the MOST AIOs

Contrary to expectations, YMYL keywords (law/government, health, science/nature) have the highest AIO prevalence. Google is NOT being cautious with high-risk topics.

### Position Variability

1 in 7 AIOs are now position 2 or lower (not in position 1). This is an increasing trend where organic results appear above the AIO. Google Search Console reports AIOs as position 1 for average rank but does not separate AIO traffic from regular organic.

### The Zero-Click Overlap

Moz case studies showed AIOs hitting keywords that were already zero-click. The traffic loss may be lower than feared because these queries were not driving clicks anyway. This is a contrarian but data-supported finding.

### Measurement Method

Triangulate AIO impact using: GA4 hash parameters (from AIO link fragments) + rank tracker AIO detection + GSC keyword data to determine whether specific AIOs drive traffic.
