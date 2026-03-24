---
name: "Lead Sourcing Tools"
description: "UpLead, Apollo, Sales Navigator, Seamless.ai, Inflact, ContactEcom, CleanLeads, RB2B, Buska.io -- setup, filters, costs, and best practices."
---

# Lead Sourcing Tools

## Database Tools (Contact Data)

### UpLead

**Best for:** B2B lead sourcing with email verification built in.
**Cost:** Plans start at ~$99/month.

**Key features:**
- Database of millions of executives with verified emails
- Filter by: industry, management level (C-suite), job function, revenue range
- Technology filter: find companies using specific tools (WordPress, Hotjar, Magento, Klaviyo)
- Auto-verifies email addresses -- download "valid only" option
- Typical yield: request 200 leads, get ~117 valid verified (58% valid rate)

**Output data fields:**
- Company name, city, website
- First name, last name, job title, email
- Management level, LinkedIn URL, employee count

**Best practices:**
- Always filter by management level (C-suite or VP+)
- Use revenue range filter to target $5M-$150M (Golden Goose)
- Technology filter is powerful for targeting specific tool users
- Download valid-only to avoid bounce issues

### Apollo.io

**Best for:** B2B contact data with integrated phone numbers.
**Cost:** ~$99/month (at time of recording), includes 50 mobile numbers/month.

**Key features:**
- Large B2B database with email and phone data
- Company and contact search with extensive filters
- Engagement tracking (email opens, clicks)
- Sequences built into the platform

**Best practices:**
- Use Apollo for phone number sourcing when cold calling
- Can use Seamless.ai to enrich Apollo data (typically returns same records)
- Export contacts as CSV for use in external sending tools

### Sales Navigator (LinkedIn Premium)

**Best for:** LinkedIn-based prospecting and trigger identification.
**Cost:** ~$99/month (LinkedIn Sales subscription).

**Key features:**
- Advanced search with Boolean operators
- Saved searches with alerts for new matching prospects
- Lead recommendations based on past activity
- Company news and insights (funding, growth, leadership changes)
- InMail credits for direct outreach

**Boolean search examples:**
- `"VP Marketing" AND "SaaS" NOT "enterprise"`
- `"Head of" AND ("Growth" OR "Demand Gen") AND "Series A"`
- `title:"CEO" AND industry:"Computer Software" AND company-size:"51-200"`

**Prospect trigger identification:**
- Job changes (recently started a new role)
- Company funding events
- Content they posted about relevant topics
- Company growth signals (hiring spree, new office)

**The "Never-Ending Rabbit Hole" technique (LinkedIn Client Lab):**
1. Find one highly qualified prospect
2. Check their connections (people like them know people like them)
3. Look at who comments on and likes their posts
4. Check "People Also Viewed" sidebar
5. Each good prospect leads to 5-10 more

### Seamless.ai

**Best for:** Real-time verified contact data with phone numbers.
**Cost:** ~$147/month.

**Key features:**
- Real-time verification (not a static database)
- Strong on mobile phone numbers
- Chrome extension for LinkedIn enrichment
- Can enrich data from other sources

**Best practices:**
- Combine with Apollo for maximum coverage
- Use primarily when you need mobile numbers for cold calling
- Chrome extension works while browsing LinkedIn profiles

---

## Specialized Lead Sourcing Tools

### ContactEcom

**Best for:** E-commerce companies running Klaviyo (hyper-specific niche sourcing).

**How it works:**
- Searches for Shopify stores using Klaviyo specifically
- Returns store owner contacts with email
- Ideal for agencies selling email marketing services to e-commerce

### CleanLeads

**Best for:** Bulk contact lookup from a domain list.

**How it works:**
- Insert a list of company domains
- Specify the job titles you want
- Returns contacts matching those titles at those companies
- Good for enriching a list of target companies with decision-maker contacts

### Inflact (Instagram Lead Sourcing)

**Best for:** Instagram DM outreach campaigns.

**How it works:**
- Search by keyword (in bio), follower count, country, gender
- Export to CSV spreadsheet
- Add tracking columns: Message 1, Message 2, Not a Fit

**Best follower ranges for cold IG DMs:**
- 500-4K followers = Best results (8-10 calls/day from this segment)
- Above 10K = Fewer calls (1-3/day) but higher quality and conversion
- Below 500 = Lower quality prospects

---

## Intent-Based Lead Sourcing

### RB2B -- Anonymous Website Visitor Identification

**Best for:** Reaching prospects who are actively researching your solution.
**Cost:** Free plan (LinkedIn only) / Paid plans (include work email).

**What it captures when someone visits your website:**
- Full name
- Job title
- Company information
- LinkedIn URL
- Work email (paid plans)
- Pages viewed on your site

**Legal status:** GDPR compliant, but only works for US-based visitors.

**Integration stack:** RB2B --> Slack (real-time notifications) --> Clay (enrichment + personalization)

**Slack notification data:**
- LinkedIn URL, full name, title, company name
- Employee count, ARR estimate, customer count

**Setup:**
1. Sign up at RB2B
2. Install JavaScript snippet in website header (works with GHL, WordPress, Webflow)
3. Connect Slack for real-time notifications
4. Connect Clay via webhook for automatic enrichment
5. Data flows into Clay with columns: first name, last name, LinkedIn, company, email, title

**Outreach template for RB2B leads:**
> "Hi {first_name}, noticed you were checking out {specific_page} on our site. A lot of {similar_roles} find {topic} really interesting. Would you be open to a quick chat about how we can help?"

This is warm outreach -- conversion rates are significantly higher than cold.

### Buska.io -- Social Keyword Monitoring

**Best for:** Finding prospects actively discussing your service/topic on social media.
**What it monitors:** Reddit, Twitter, LinkedIn, YouTube, Instagram, Google News, Medium, Quora, IndieHackers.

**Setup:**
1. Add 3 keywords (e.g., "lead generation," "cold emails," "B2B leads")
2. Describe customer intent (e.g., "looking for lead generation help")
3. Enter your website URL
4. Select platforms to monitor
5. Tool finds mentions with sentiment analysis

**Results:** 112 mentions found instantly for "lead generation" keywords (instructor's example).

**Export options:** CSV, LaGrowthMachine, or directly to Clay for enrichment.

---

## Reddit Inbound Funnel (Acquisition X)

### Why Reddit for B2B

- 7th most visited website globally with 433M+ active users
- Google ranks Reddit posts on page 1 for many queries (free SEO)
- Pre-qualified audience on B2B subreddits
- Completely organic and free

**Critical rules:**
- Never self-promote without contributing first
- Never use corporate language -- be conversational
- Never copy-paste same content across subreddits
- Never ask for upvotes (ban risk)

### Karma Building Strategy

**Phase 1 (Days 1-7):** Post in popular subreddits (cats, dogs, flowers). Target 200-300 karma to unlock B2B subreddits.
**Phase 2:** Comment thoughtfully in target subreddits. Use everyday language.
**Phase 3:** Post value-based content in 5-7 subreddits aligned with your ICP.

### Content Creation with AI

- Build swipe file from top posts in target subreddits (filter by "Top" + "This Year")
- Feed to AI: "Write a Reddit post for [subreddit]. My product does [X]. Use same format as these viral posts. Make it conversational, NOT salesy."
- Can create 10-15 posts in 30 minutes

### Conversion Flow

1. Post valuable content (no product mentions)
2. Interested prospects check your profile (optimized: username = brand, banner, bio, links)
3. They search your brand on Google
4. They find your website and book a call (or DM you directly)

---

## Tool Cost Summary

| Tool | Monthly Cost | Best For |
|------|-------------|----------|
| UpLead | ~$99/month | B2B email + tech stack targeting |
| Apollo.io | ~$99/month | B2B email + phone numbers |
| Sales Navigator | ~$99/month | LinkedIn prospecting + triggers |
| Seamless.ai | ~$147/month | Real-time verified mobile numbers |
| Inflact | Varies | Instagram lead sourcing by bio |
| ContactEcom | Varies | E-commerce (Shopify + Klaviyo) |
| CleanLeads | Varies | Bulk contact lookup from domains |
| RB2B | Free / Paid | Website visitor identification |
| Buska.io | Varies | Social keyword monitoring |
| NeverBounce | ~$76 per 9.5K records | Email verification |
| Clay | Varies | Lead enrichment + AI personalization |
