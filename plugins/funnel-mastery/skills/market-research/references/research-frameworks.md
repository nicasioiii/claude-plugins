---
name: Research Frameworks
description: >
  Product-Market Awareness Assessment prompt template, Competitor Research prompt
  template, Psychographic Research 19-question framework, Curiosity/Corruption/External
  Barrier angle frameworks, Unified Research Document creation prompt, and AI-powered
  research workflows.
  When to Read: User needs to conduct formal market research, wants prompt templates
  for AI-assisted research, is building a research brief, or needs angle frameworks
  for copy development.
  Cross-references: After research is complete, create the unified research document
  and feed into vsl-sales-copy or sales-page-copy. For unique mechanism development
  specifically, see vsl-sales-copy references/unique-mechanism.md.
---

# Research Frameworks (Georgi -- RMBC II)

## Product-Market Awareness Assessment

**Purpose:** Determine where the majority of your target market falls on the Schwartz awareness spectrum. This single assessment drives all downstream funnel and copy decisions.

**AI Prompt Template:**

```
I want your help evaluating the level of market awareness for a product in [YOUR NICHE]. The specific product is [YOUR PRODUCT]. I would like for you to deep dive to help me understand the current level of market awareness for this product in [GEOGRAPHY].

Optional: Here are more details about the market: [DEMOGRAPHIC DETAILS]

To do this, we can look at the classic levels of product and market awareness often attributed to Eugene Schwartz...

For the intents of this exercise, let's not consider "product-aware" or "most-aware" to be our specific product and brand. Instead, let's consider it to be awareness about similar and nearly identical products and brands that offer those products.

In order to make this assessment, please utilize a variety of signals including social media chatter, articles and blog posts, influencer content, search trends, any available sales data on the product category and its growth, and so on.

Additionally, please provide an overview of the estimated Total Addressable Market (TAM) for this product and a rough estimate of what percentage of the TAM falls into each category of product market awareness.

At the end of your review, please give me a final selection for which stage of product market awareness the majority of individuals within the market fall.
```

**Case Study Outputs:**

**Injectable NAD+:**
- 50% problem-aware, 30% unaware, 15% solution-aware, 5% product-aware
- TAM funnel: 78M interested adults -> 15.6M high disposable income -> 3.9M aware of NAD+ -> 585K willing to try injectables

**Airbnb Arbitrage Coaching:**
- 40% problem-aware, 30% unaware, 20% solution-aware, 10% product/most-aware
- TAM for niche coaching: 1-3M individuals

---

## Competitor Research

**Purpose:** Map the competitive landscape to find messaging gaps, positioning opportunities, and hooks that are overused vs. underused.

**AI Prompt Template:**

```
I want your help doing competitor research for a product in the [YOUR NICHE] space. The specific product is [PRODUCT] and we are focused on competitors in [GEOGRAPHY].

Specifically, we're looking for D2C brands who primarily sell online through eCommerce or Direct Response sales funnels.

For each competitor you find, I want to understand:
- Who is the target demo they speak to?
- What are their main new customer acquisition funnels?
- What is their core messaging in their ads, advertorials, and other advertising assets?
- What are examples of their advertisements or landing page assets if available?
- Are there any recurring or repetitive hooks/angles/big ideas you see consistently appearing in their advertising assets?
- What is their pricing structure?
- What do customers love and what do customers dislike about them (use reviews, social signals, social media platforms, etc)?
- If available, what is their estimated overall business revenue and revenue for their hero product(s)?

Optional: Here are more details about the market [DETAILS]
```

---

## Psychographic Research Framework (19 Questions)

The original "R" from RMBC. These questions build the deep customer understanding that powers all copy.

### Insights Into Demographic (Questions 1-7)

1. **Who Is Your Customer?** (Demographics + psychographics)
2. **What Attitudes Do They Have?** (Religious, Political, Social, Economic)
3. **What Are Their Hopes and Dreams?**
4. **What Are Their Victories and Failures?**
5. **What Outside Forces Do THEY Believe Have Prevented Their Best Life?**
6. **What Are Their Prejudices?**
7. **Sum Up Their Core Beliefs About Life, Love, and Family In 1-3 Sentences**

### Other Existing Solutions (Questions 8-13)

8. **What is the Market Already Using?** (List all competing solutions)
9. **What Has Their Experience Been Like?**
10. **What Does the Market Like About Existing Solutions?**
11. **What Does the Market Dislike About Existing Solutions?**
12. **Are There Horror Stories About Existing Solutions?**
13. **Does the Market Believe Existing Solutions Work? If Not, Why?**

### Angle Development (Questions 14-19)

14. **Has Someone Tried to Solve This In A Very Unique Way? What Was The Result?** (Curiosity angle seed)
15. **Is There A Conspiratorial Story Behind Why Old Solutions Didn't Work?** (Curiosity angle seed)
16. **Are There Any Older Attempts to Solve the Problem (Pre-1960) That Are Unique?** (Curiosity angle seed)
17. **Is There A Belief That the Pain Point Used To Not Exist, Or Used To Not Be So Bad?** (Corruption angle seed)
18. **Is There A Belief That It's Been Recently Exacerbated By Outside Forces?** (Corruption angle seed)
19. **If So, What Are Those Forces And What's The Reason Behind Their Presence?** (Corruption angle seed)

---

## Psychographic Angle Frameworks

### The Curiosity Angle -- Rediscovered Solutions
1. Identify a historical attempt to solve the problem that was unique/effective
2. Explain why this solution was lost to history (suppressed? forgotten? replaced by inferior modern methods?)
3. Position your product as rediscovering or improving upon this forgotten wisdom

**Use when:** Market is solution-aware but jaded by modern options. Taps into nostalgia and the appeal of hidden knowledge.

### The Corruption Angle -- Paradise Lost
1. Suggest the pain point used to be less severe until corrupting forces made it worse
2. Tap into nostalgia and righteous indignation
3. Position product as returning to a better way that was lost or taken

**Use when:** Market believes external forces (big pharma, big food, government, corporations) have made their problem worse. Very powerful in health, food, and financial markets.

### The External Barrier Angle
1. Acknowledge forces the market believes are stacked against them (toxins, microplastics, the economy, algorithms, etc.)
2. Validate that these barriers are real
3. Position product as something that works DESPITE these obstacles

**Use when:** Market feels victimized by forces beyond their control. Powerful because it removes self-blame and positions the product as the equalizer.

---

## Unified Research Document

**Purpose:** Single consolidated reference combining all research for feeding to LLMs when generating marketing assets.

**Key components:**
1. Target Market Demographic Overview
2. Target Market Psychographic Overview (focused on problem-aware and solution-aware)
3. Language and Communication Style (specific language to use AND avoid)
4. Primary Promises and Objections
5. Existing Solutions Analysis

**Creation Prompt:**

```
I'm working on a marketing campaign in [niche], the product is [product], and we focus on [customers] in [region]. So far, I have performed research around product market awareness levels, competitors, and psychographic research. I'm going to upload several PDFs that contain this research.

What I want you to do is go through these PDFs in depth and then create one unified research brief that contains all of the key elements that would be needed in order to successfully implement this campaign.
```

---

## Ingredient Deep Research for Claims (Supplement/DTC)

**When you know the unique mechanism and have done deep research:**

```
These are the ingredients for [PRODUCT] I'll be doing sales copy for: [LIST INGREDIENTS]

I'm attaching two documents for reference. One is an overview of the market and their pain points. The second is the unique mechanism I'll be using.

What I want for you to do is come up with a list of claims for each ingredient that can be tied back to specific studies or research. This research needs to come from stuff published on NCBI or other scientific journals, and cannot include things from random blogs or websites. Give preference to RCTs with humans.

Claims should be focused on:
1. How the ingredient supports the unique mechanism of the solution (when applicable)
2. Additional studies of how the ingredient helps alleviate pain points of the market

Please keep the claims digestible with references. I just need accurate claims showing the best efficacy and results possible for each ingredient.
```

**Best practice:** Run research BOTH with and without mechanism context -- each approach yields different valuable data. Combine findings from Perplexity (speed/statistics) and ChatGPT (mechanism-connected claims).

---

## Multi-LLM Research Strategy (Georgi)

- **Gemini 2.5 Pro:** Deep research, large document processing
- **Perplexity:** Ingredient research, fast statistics, NCBI citations
- **ChatGPT:** Mechanism-connected claims, context integration
- **Claude:** Writing and unified document creation
- Run same prompts across multiple LLMs, then merge best outputs

**Speed-depth balance:** LLMs get you 95-99% of the way. The final percentage requires your expertise and critical thinking. There will always be insights that get missed when you summarize with LLMs.
