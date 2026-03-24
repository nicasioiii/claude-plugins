# Intent Classification Framework

Deep-dive on understanding search intent and mapping it to content strategy and monetization.

## The Four Intent Types

### Commercial Intent (Revenue-Generating Keywords)

**Definition:** User is ready to take action (buy, sign up, pay for service).

**Identifying Phrases:**
- Modifiers: "best," "top," "recommended," "vs," "comparison," "review"
- Action words: "buy," "purchase," "order," "price," "cost," "where to"
- Decision-phase: "which," "should I," "worth it," "how much"

**Real-world examples:**
- "Best dog food for sensitive stomach" (buying decision)
- "Ryzen 5 vs i7 comparison" (choosing between products)
- "iPhone 15 price UK" (ready to research price)
- "Creatine monohydrate supplement review" (evaluating specific product)
- "Best SEO software for agencies 2026" (buying guide intent)

**Content type:**
- Product reviews (detailed feature analysis)
- Comparison articles (feature-by-feature vs.)
- Buying guides (which product for which use case)
- Roundups ("5 best tools for X")
- Where-to-buy guides

**Monetization methods:**
- Affiliate commissions (highest ROI)
- Display ads (secondary)
- Direct product sales (if ecommerce)
- Sponsored product mentions (if brand collaboration)

**Publishing priority:** 70% of content. These keywords drive revenue.

**Ranking difficulty:** Typically medium-to-high (KD 35-50) because commercial keywords are competitive. But ranked commercial keywords = traffic that converts.

**Fact:** One commercial keyword ranking can generate more revenue than 10 informational keywords.

### Informational Intent (Authority-Building Keywords)

**Definition:** User is learning or researching; no immediate purchase intent.

**Identifying phrases:**
- "How to," "what is," "guide to," "explain," "definition"
- Learning words: "tutorial," "beginner," "basics," "fundamentals"
- Research: "why," "benefits of," "pros and cons," "should I"

**Real-world examples:**
- "How to choose a dog food" (learning what makes good food)
- "What causes dog skin allergies" (understanding problem, not buying)
- "Dog food protein requirements" (educational, informational)
- "History of SEO" (pure information, no action intent)
- "Is grain-free dog food healthy?" (considering option, not buying yet)

**Content type:**
- Educational guides (comprehensive, 2000+ words)
- Tutorials and how-tos
- Expert interviews
- Research and data analysis
- Conceptual explainers
- Pros/cons analysis

**Monetization methods:**
- Link building asset (cite-worthy content = backlinks)
- Topical authority signal (establishes expertise)
- Retargeting funnel (learn today, convert tomorrow)
- Display ads (if traffic is high enough)

**Publishing priority:** 20% of content. Essential for topical authority but lower revenue ROI.

**Ranking difficulty:** Typically lower (KD 20-35) than commercial keywords. Broader audience, less competition from brands.

**Strategic value:** Informational content ranks faster, builds domain authority quicker, and creates internal linking opportunities to commercial content.

### Navigational Intent (Brand Keywords)

**Definition:** User is searching for a specific brand, tool, or resource they already know about.

**Identifying phrases:**
- Brand name alone or brand + modifier
- "[Brand] login," "[Brand] review," "[Brand] alternative"
- "[Tool] tutorial," "[Service] pricing"

**Real-world examples:**
- "Ahrefs" (user looking for Ahrefs specifically)
- "ChatGPT alternatives" (looking for specific competitor)
- "Shopify pricing" (seeking specific tool)
- "Amazon dog food" (navigating to brand site)

**Content type:**
- Brand reviews (if not your brand)
- Alternative guides (comparing to your brand)
- Competitor comparisons
- Tool overviews

**Monetization methods:**
- Affiliate (if reviewing other brands)
- Link building (if brand mentions you)

**Publishing priority:** Only 5-10% of content, and only if:
- You own the brand, OR
- The brand has an affiliate program AND high commission, OR
- You have a competitor offering you'd rather promote

**Ranking difficulty:** Varies. Branded keywords usually rank easy (no competition) but generate no new traffic.

**Fact:** Skip most navigational keywords. User already knows what they want; ranking won't change their mind.

### Transactional Intent (Hybrid)

**Definition:** User is ready to complete a specific transaction (different from commercial).

**Difference from commercial:** More specific and immediate action

**Examples:**
- "Buy dog food online" (want to purchase NOW)
- "Sign up for Ahrefs free trial" (ready to convert)
- "Download Photoshop" (immediate action)
- "Book a hotel in London" (transaction imminent)

**Content type:**
- Product pages
- Checkout process
- Service booking pages
- Download pages

**Monetization:** Direct conversion (sales, leads, signups)

**Note:** Transactional is really commercial intent in its most urgent form. Treat with same priority.

## Intent Classification Workflow

### Spreadsheet Classification System

Create a keyword list with this structure:

| Keyword | Base Intent | Modifiers Present | User Stage | Content Type | Monetization | Priority |
|---|---|---|---|---|---|---|
| Best dog food for sensitive stomach | Commercial | "best" | Decision | Buying guide + reviews | Affiliate | HIGH |
| Dog food for sensitive stomach | Commercial | None (but commercial context) | Consideration | Comparison | Affiliate | HIGH |
| How to choose dog food | Informational | "how to" | Awareness | Guide | Links + ads | MEDIUM |
| Dog food ingredients | Informational | None (but educational context) | Awareness | Explainer | Ads | MEDIUM |
| Purina dog food | Navigational | Brand name | Navigation | N/A (brand owned) | N/A | LOW |

**Auto-classification formula (Google Sheets):**
```
=IF(OR(ISNUMBER(SEARCH("best",A2)),ISNUMBER(SEARCH("review",A2)),ISNUMBER(SEARCH("vs",A2)),ISNUMBER(SEARCH("buy",A2)),ISNUMBER(SEARCH("price",A2))),"Commercial",IF(OR(ISNUMBER(SEARCH("how to",A2)),ISNUMBER(SEARCH("what is",A2)),ISNUMBER(SEARCH("guide",A2))),"Informational","Navigational"))
```

### Nuance: Intent Overlap

Real keywords often blend intents:

**"How to choose the best dog food for sensitive stomach"**
- Primary: Commercial (buyer ready to choose)
- Secondary: Informational (still learning)- Treatment: Create comprehensive buying guide that educates AND recommends

**"Dog food for sensitive stomach vs wet food"**
- Primary: Commercial (comparison = decision)
- Secondary: Informational (comparing options)
- Treatment: Detailed comparison article with specific product recommendations

**Rule:** If blended, follow the PRIMARY intent (what the user will likely click next). A commercial-primary keyword should lead to product recommendations, even if educational content precedes it.

## Intent-to-Content Mapping

### Commercial Intent Content Structure

**Optimal outline for "Best X for Y" keywords:**

1. **Opening hook** (50 words)
   - Establish problem (your audience's pain)
   - Promise solution (what article delivers)
   - Credibility signal (why you're qualified)

2. **Quick answer** (100-150 words)
   - Single best recommendation
   - Why it wins
   - Price and where to buy

3. **Comparison table** (visual)
   - Top 3-5 products side-by-side
   - Key features/price/ratings
   - Affiliate links

4. **Individual reviews** (200-300 words each, 3-5 products)
   - Product name, price, key features
   - Pros and cons
   - Who it's best for
   - Where to buy (affiliate link)

5. **How to choose** (300-400 words)
   - What to look for
   - Feature explanations
   - Decision criteria specific to keyword
   - Buying checklist

6. **FAQ** (200-300 words)
   - Address common objections
   - "Is X worth it?"
   - Comparison questions
   - Guarantee/return policies

7. **Final recommendation** (100 words)
   - Restate best choice
   - Call to action (buy now link)

**Total word count:** 1200-1800 words

**Monetization checkpoints:**
- Multiple affiliate links (not obtrusive)
- Links in comparison table (high visibility)
- Explicit "where to buy" sections
- Call-to-action buttons

### Informational Intent Content Structure

**Optimal outline for "How to," "What is," "Guide to" keywords:**

1. **Opening** (100 words)
   - Define the topic
   - Why it matters
   - What reader will learn

2. **Table of contents** (visual)
   - Breaks content into sections
   - Helps navigation
   - Shows comprehensiveness

3. **Foundational section** (300-400 words)
   - Background/history if relevant
   - Basic concepts
   - Context-setting

4. **Main sections** (3-5 sections, 300-400 words each)
   - Deep-dive on each aspect
   - Real examples
   - Expert quotes if available
   - Data and research

5. **Practical application** (400-500 words)
   - How to implement/use this knowledge
   - Common mistakes
   - Tips and tricks
   - Real case studies

6. **Advanced topic** (300-400 words)
   - Go one level deeper
   - Advanced strategies
   - Expert variations
   - Next-level thinking

7. **Resources & further reading** (200 words)
   - Tools mentioned
   - Recommended courses/books
   - Related articles on your site (INTERNAL LINKING)

8. **FAQ** (200 words)
   - Answering remaining questions
   - Clarifying concepts

**Total word count:** 2000-2500 words (depth signals expertise)

**Link building hooks:**
- Original research or data
- Unique framework or methodology
- Comprehensive resource (commonly cited)
- Expert interviews

## The Intent-Funnel Mapping

Map all keywords to buyer journey:

**Awareness Stage (Top of Funnel)**
- Intent: Informational
- Keywords: "What is dog food," "Dog nutrition basics," "Types of dog food"
- Content: Educational guides, explainers
- Monetization: Ad revenue, link building

**Consideration Stage (Middle of Funnel)**
- Intent: Commercial (comparisons) + Informational
- Keywords: "Limited ingredient vs hydrolyzed dog food," "Best dog food for allergies," "How to choose dog food"
- Content: Comparison articles, detailed buying guides
- Monetization: Affiliate links (moderate)

**Decision Stage (Bottom of Funnel)**
- Intent: Commercial (specific)
- Keywords: "Royal Canin Hydrolyzed review," "Purina ProPlan price," "Where to buy Merrick dog food"
- Content: Product reviews, pricing guides
- Monetization: Affiliate links (high ROI)

**Best Practice:** Balance all three stages. A site targeting ONLY decision-stage keywords starves itself of funnel traffic. Targeting ONLY awareness leaves money on the table.

## Intent Classification Pitfalls

**Pitfall 1: Assuming one intent, ignoring searcher nuance**
- Searcher for "best dog food" could be:
  - Brand new dog owner (needs education first)
  - Returning customer (wants specific product recommendation)
  - Veterinarian (researching for client)
- Solution: Write comprehensive guide addressing all angles

**Pitfall 2: Publishing commercial content for informational keywords**
- Keyword: "What is dog food sensitivity?" (educational)
- Wrong content: Product review (doesn't match intent)
- Right content: Explanation of sensitivity + types of sensitivities + how to identify

**Pitfall 3: Publishing informational content for commercial keywords**
- Keyword: "Best dog food for sensitive stomach" (commercial)
- Wrong content: Definition of sensitivity (doesn't help decision)
- Right content: Specific product recommendations with buying details

**Pitfall 4: Over-monetizing informational content**
- Stuffing affiliate links into educational articles backfires
- Readers seeking education resent hard sell
- Solution: Monetize with ads or links to commercial articles

**Pitfall 5: Ignoring user stage progression**
- User searching "how to identify dog allergies" today may search "best dog food for allergies" tomorrow
- You want BOTH keywords to link to each other
- Solution: Always internally link from awareness → consideration → decision content

## Tool-Based Intent Detection

Some keyword research tools flag intent automatically:

**Ahrefs:**
- Intent shown in Keyword Explorer
- Flags: Commercial, Informational, Navigational
- Accuracy: ~85% (requires manual review)

**SEMrush:**
- "Intent" column in Keyword Magic
- Categories: Commercial, Informational, Transactional, Navigational
- Accuracy: ~80%

**Moz Keyword Explorer:**
- Does NOT flag intent
- Requires manual review

**Google Search Console:**
- Shows real queries your site appears for
- Filter by query type in performance report
- Most accurate (real user data)

**Rule:** Always validate tool flags with manual SERP check. A keyword showing "Informational" may have commercial results ranking. Use tools as guide, not gospel.

---

*Synthesis from: Nicolas Gorrono (Intent-based Content Strategy), AuthorityHacker (Monetization Alignment), Koray Tugberk Gubur (User Behavior Semantics)*
