# Information Architecture Basics

Information architecture (IA) is the structure of your project before you design any screens. It prevents confusion, uncovers missing features, and clarifies the user journey.

---

## What is Information Architecture?

**Definition:** The structural design of information spaces to support both usability and findability of content.

**In practice:** It answers "Where do I put things? How do users find what they need?"

**Deliverables:**
- Sitemaps (page hierarchy)
- User flows (step-by-step journeys)
- Content maps (how information relates)

---

## Sitemaps: Visual Hierarchy

A sitemap shows all pages and how they relate to each other.

### Sitemap Format

```
Root (Home)
├── Section 1
│   ├── Page 1a
│   └── Page 1b
├── Section 2
│   ├── Page 2a
│   ├── Page 2b
│   └── Page 2c
└── Section 3
```

### Sitemap Rules

1. **Maximum 3 levels deep:** If you need more than 3 levels to reach content, reorganize.
   - Level 1: Home
   - Level 2: Main categories
   - Level 3: Specific content
   - Anything deeper = too buried

2. **Group related pages together:** Users should intuitively find what they're looking for
   - E-commerce example: Products, Categories, Search → grouped under Shop
   - Blog examples: Posts, Archives, Tags → grouped under Resources

3. **Include all pages/states:** Don't forget authentication pages, error pages, empty states
   - Login/Sign up (separate from main nav if appropriate)
   - 404 page
   - Search results
   - User account pages

4. **Show decision branches if complex:** Does logged-in user see different nav?
   - Use annotations: "Only visible to logged-in users"

---

## Sitemap Examples

### Simple Marketing Website

```
Home
├── About (About us, team, company story)
├── Services (What we offer, pricing)
├── Blog (Posts, archives, search)
├── Contact
└── Account (Login/Sign up, profile, settings)
```

**Depth:** 2 levels max (Home → Section → Page)

**Pages:** ~7-10 total

### E-Commerce Website

```
Home
├── Shop
│   ├── All Products (with filters, search)
│   ├── Categories (Men, Women, Kids)
│   │   └── Subcategories (Shoes, Shirts, Pants)
│   └── Product Detail (individual item)
├── Cart (review items)
├── Checkout (shipping, payment)
├── Account
│   ├── Profile
│   ├── Order History
│   └── Wishlist
├── Blog (lifestyle content)
├── FAQ
├── Contact
└── Legal (Privacy, Terms)
```

**Depth:** 3 levels (Home → Category → Subcategory → Product OR Home → Shop → Products)

**Pages:** ~20-30 total

### SaaS Dashboard

```
Home
├── Authentication
│   ├── Login
│   ├── Sign up
│   ├── Reset password
│   └── Email verification
├── Dashboard (main workspace)
│   ├── Overview (metrics, charts)
│   ├── Projects (list, detail, settings)
│   ├── Team (members, invites, permissions)
│   ├── Settings
│   │   ├── Account
│   │   ├── Billing
│   │   └── Integrations
│   └── Notifications
├── Help/Support (docs, contact)
└── Account (profile, logout)
```

**Depth:** 3-4 levels (some features within dashboard)

**Pages:** ~15-25 total

---

## User Flows: Journey Mapping

A user flow shows step-by-step how someone accomplishes a goal. Include decision points (if/then branches).

### Basic User Flow Structure

```
Start → Step 1 → Step 2 → Decision? → Path A or Path B → End
```

### Flow Example: E-Commerce Checkout

```
User clicks "Checkout"
  ↓
Logged in?
  ├─ YES → Go to shipping address
  └─ NO → Show login/sign up → Proceed to shipping address
      ↓
Enter shipping address
  ↓
Address valid?
  ├─ YES → Proceed to shipping method
  └─ NO → Show error, request correction
      ↓
Select shipping method (Standard, Express, Overnight)
  ↓
Enter payment info
  ↓
Payment valid?
  ├─ YES → Process payment
  └─ NO → Show error, request correction
      ↓
Payment successful?
  ├─ YES → Show confirmation page, send email
  └─ NO → Show error, retry or contact support
      ↓
END: Order complete
```

### Flow Symbols

- **Rectangle/Box:** Process or action step
- **Diamond:** Decision point (if/then)
- **Circle:** Start or end
- **Arrow:** Flow direction

### Key Elements to Show

1. **Happy path:** The ideal, no-errors journey
2. **Error states:** What happens if data is invalid?
3. **Alternative paths:** Different user types or statuses
4. **Exit points:** Where can user abandon?

---

## Flow Example: Content Site Blog Navigation

### Scenario: First-time visitor wants to read a blog post

```
User visits home
  ↓
Click "Blog"
  ↓
Landing on blog index (showing 10 recent posts)
  ↓
User can:
  ├─ Search by keyword → Filtered results → Click post
  ├─ Browse categories → Category page → Click post
  └─ Scroll → Click post directly
      ↓
Reading blog post
  ↓
At bottom, suggest:
  ├─ Related articles
  ├─ Subscribe button
  └─ Share buttons
      ↓
User can click another post or return to blog index
```

---

## Flow Example: SaaS User Creates Project

```
User logs in → Dashboard
  ↓
Click "+ Create Project"
  ↓
Fill form: Project name, description, visibility
  ↓
Click "Create"
  ↓
Project created successfully?
  ├─ YES → Redirect to project page
  │        Show project details, invite team members
  └─ NO → Show error message
         Suggest: Retry, contact support
      ↓
User can:
  ├─ Invite team members
  ├─ Configure settings
  └─ Start creating content
```

---

## Content Maps: Information Relationships

For content-heavy sites, create a content map showing how information relates.

### Content Map Example: Help/Knowledge Base

```
Knowledge Base
├── Getting Started
│   ├── Create an account
│   ├── Set up profile
│   └── First project
├── Features
│   ├── Project management
│   ├── Team collaboration
│   ├── Reporting
│   └── Integrations
├── Troubleshooting
│   ├── Common errors
│   ├── Performance issues
│   └── Data recovery
└── FAQ
    ├── Billing questions
    ├── Account management
    └── Technical questions
```

**Why useful:** Helps identify:
- Missing documentation
- Orphan content (content with no path to it)
- Organizational clarity

---

## Decision: How Many Pages?

### Rule of Thumb

- **Tiny (5-10 pages):** Marketing site, portfolio, landing page
- **Small (10-20 pages):** Startup website, single-product site
- **Medium (20-50 pages):** Established business, multi-section site
- **Large (50+ pages):** Enterprise, e-commerce, extensive content

**Don't confuse:** Page count with screen count
- A homepage might have 3-5 sections but is 1 page
- A product detail page is 1 page (even with scroll)
- Account settings might be multiple pages (Profile, Billing, Notifications)

---

## IA Review Checklist

Before moving to wireframes, verify:

- [ ] **Sitemap is 3 levels or fewer** (maximum depth)
- [ ] **Clear page hierarchy:** Parent-child relationships obvious
- [ ] **All pages accounted for:** Including edge cases (login, 404, empty states)
- [ ] **User flows for key journeys:** Checkout, sign up, search results
- [ ] **No orphan pages:** Every page is reachable from home or another page
- [ ] **Consistent naming:** Page titles make sense (no confusion between similar names)
- [ ] **Stakeholder alignment:** Everyone agrees on structure before design
- [ ] **Mobile consideration:** Same structure works on mobile (or modifications documented)

---

## Common IA Mistakes

1. **Too many levels:** 5+ levels deep = users get lost
   - **Fix:** Reorganize. What can be at same level instead of nested?

2. **Missing authentication pages:** Forgot login, sign up, password reset
   - **Fix:** Add these to sitemap

3. **No user flows:** Only sitemap, no journeys
   - **Fix:** Map key user paths (purchase, sign up, search)

4. **Unclear page purpose:** "Dashboard" could mean 5 different things
   - **Fix:** Name pages descriptively (Project Dashboard, Analytics Dashboard, etc.)

5. **Mobile not considered:** Desktop-only structure doesn't work on mobile
   - **Fix:** Design IA mobile-first or explicitly note mobile changes

---

## Tools for Creating IA Artifacts

### Sitemaps
- **Figma:** Shapes and text (simple, visual)
- **Miro/Mural:** Collaborative whiteboarding
- **Lucidchart:** Formal diagram tool
- **Draw.io:** Free, simple

### User Flows
- **Figma:** Shapes, connectors, text
- **Miro:** Whiteboarding with sticky notes
- **Lucidchart:** Professional diagrams
- **FigJam:** Figma's collaborative whiteboard

### Documentation
- **Google Docs:** Collaborative writing
- **Notion:** Database + documentation
- **Confluence:** Enterprise documentation

---

## From IA to Wireframes

Once IA is approved, you're ready for wireframes (if medium/high complexity).

**Next steps:**
1. Take your sitemap and create wireframes for each page
2. Use your user flows to design the interaction steps
3. In Figma: Create pages for each page in your sitemap
4. Add annotations: Content blocks, spacing, interactions

**Time investment:**
- Sitemap: 1-2 hours
- User flows: 2-3 hours
- IA review/iteration: 1-2 hours
- **Total:** 4-7 hours before wireframes

This prevents 15-30 hours of rework during design. Worth it.
