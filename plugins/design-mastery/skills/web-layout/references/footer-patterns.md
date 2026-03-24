# Footer Patterns — Structure, Links, and Responsive Design

## Standard Footer Anatomy

### Multi-Column Footer (Desktop)

```
┌──────────────────────────────────────────────┐
│ [Logo]  Column 1    Column 2    Column 3     │  Main footer
│ Brand   • Link 1    • Link 1    • Link 1     │
│         • Link 2    • Link 2    • Link 2     │
│         • Link 3    • Link 3    • Link 3     │
├──────────────────────────────────────────────┤
│                  [Social icons]               │  Optional social
├──────────────────────────────────────────────┤
│ © 2026 Company, Inc.                        │  Copyright
│ Privacy Policy • Terms • Sitemap            │  Legal links
└──────────────────────────────────────────────┘
```

### Footer Sections Breakdown

1. **Logo/Brand (Top-Left)**
   - Logo: 32-40px height
   - Optional: Company tagline (12px gray)
   - Padding: 24px right

2. **Navigation Columns (Center)**
   - 3-5 columns
   - Column header: 14px bold (section title)
   - Links: 12px gray, regular weight
   - 20-30 links total per footer
   - Column width: 150-200px each

3. **Social Media (Top-Right, Optional)**
   - Icons: 24-32px
   - Common: LinkedIn, Twitter, Facebook, Instagram
   - Hover: Color change or slight scale

4. **Newsletter Signup (Optional)**
   - Email input field
   - Subscribe button
   - Positioning: Right column or separate row

5. **Copyright Section (Bottom)**
   - Text: "© Year Company Name. All rights reserved."
   - Size: 11-12px
   - Color: Gray (#666 or #999)

6. **Legal Links (Bottom)**
   - Privacy Policy, Terms of Service, Sitemap
   - Size: 12px
   - Separator: • or |
   - Hover: Underline or color change

---

## Footer Sizing & Spacing

### Vertical Spacing

**Footer Sections:**
```
Main footer content
  Padding: 60-80px top/bottom
  Column gap: 40-60px horizontal

Divider line
  Border-top: 1px solid #EEEEEE
  Margin: 20px top/bottom

Copyright section
  Padding: 20px vertical, 40px horizontal
  Background: Slightly darker (#FAFAFA or transparent)
```

### Column Link Spacing

**Between Links (Vertical):**
```
• Link 1
[12px gap]
• Link 2
[12px gap]
• Link 3
```

**Line Height:** 200% or 24px (comfortable vertical spacing)

**Column Header Spacing:**
```
Column Title (14px, bold)
[12px gap]
• Link 1
• Link 2
```

### Logo Area Spacing

```
[Logo 40px height]
  12px margin-bottom
[Company tagline 12px]
```

---

## Footer Links Organization

### Typical Column Structure

**Column 1: Product/Features**
- Features
- Pricing
- Security
- Enterprise
- Roadmap

**Column 2: Company**
- About
- Blog
- Jobs
- Press
- Partners

**Column 3: Resources**
- Documentation
- Guides
- API Reference
- Community
- Help Center

**Column 4: Legal/Social**
- Privacy Policy
- Terms
- Cookies
- Security
- [Social icons]

### Link Styling

**Default State:**
- Color: Gray (#666 or #999)
- Text decoration: None
- Cursor: pointer
- Font: 12px, regular weight

**Hover State:**
- Color: Brand primary or darker gray
- Text decoration: Underline (optional)
- Smooth transition: 200ms

**Active State (Current Page):**
- Color: Brand primary
- Underline: Persistent

**Visited State:**
- Color: Purple (#663399) or same as default
- Many designers ignore visited state in footers

---

## Responsive Footer

### Desktop (1440px)

**Layout:**
```
[Logo]  [Col 1] [Col 2] [Col 3] [Social]
(All visible, horizontal alignment)
```

**Implementation:**
```css
.footer {
  display: grid;
  grid-template-columns: 200px 150px 150px 150px 100px;
  gap: 40px;
  padding: 60px 64px;
}

.footer-copyright {
  grid-column: 1 / -1;
  border-top: 1px solid #EEE;
  padding-top: 20px;
  margin-top: 20px;
}
```

### Tablet (800px)

**Layout:**
```
[Logo]      [Col 1] [Col 2]
[Social]    [Col 3] [Col 4]
```

**Changes from desktop:**
- 2-3 columns (instead of 5)
- Columns narrower (120-150px)
- Logo still top-left
- Social icons repositioned (left column, below logo)

**Implementation:**
```css
@media (max-width: 1000px) {
  .footer {
    grid-template-columns: 200px 150px 150px;
    gap: 40px;
  }

  .footer-social {
    grid-column: 1;
    grid-row: 2;
  }
}
```

### Mobile (390px)

**Layout:**
```
[Logo]
[Newsletter (optional)]
[Col 1 Title]
• Link 1, Link 2, Link 3
[Col 2 Title]
• Link 1, Link 2, Link 3
[Social icons]
[Copyright + Legal]
```

**Changes from desktop:**
- Single column layout
- All content stacked vertically
- Logo full-width
- Links in inline list or stacked
- Social icons centered or left-aligned
- Smaller text: 11px

**Implementation:**
```css
@media (max-width: 600px) {
  .footer {
    display: block;
    padding: 40px 16px;
  }

  .footer-column {
    margin-bottom: 32px;
  }

  .footer-column h3 {
    font-size: 13px;
    margin-bottom: 12px;
  }

  .footer-column ul {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
  }

  .footer-social {
    text-align: center;
    margin: 24px 0;
  }
}
```

---

## Footer Variations

### Minimal Footer (Simple Sites)

```
[Logo]  © 2026  Privacy  Terms  Social icons

Height: 80px
Single row
Text-aligned, centered or spread
```

**Use case:** Small businesses, landing pages

### Extended Footer (E-commerce)

```
[Company info column] [Products] [Support] [Follow us]
[Store info, hours]   [Categories] [Contact]
                      [New Arrivals] [FAQ]

Height: 300px+
Multiple sections, rich with links
Newsletter signup included
```

**Use case:** E-commerce sites, marketplaces

### Simple Footer (SaaS)

```
[Logo] [Company links] [Product] [Social]
© 2026 | Privacy | Terms

Minimal, scannable
2-3 columns
Links grouped logically
```

**Use case:** SaaS, startups, modern web apps

---

## Footer Content Best Practices

### What to Include

✓ Company logo/name
✓ Main navigation links (5-15 high-value links)
✓ Copyright notice
✓ Privacy Policy link (REQUIRED legally)
✓ Terms of Service link
✓ Social media icons (optional)
✓ Newsletter signup (optional)
✓ Contact information (optional)

### What to AVOID

✗ Too many links (50+ links = cluttered)
✗ Outdated copyright year (update automatically)
✗ Broken links (audit quarterly)
✗ Auto-playing videos
✗ Ads (ruins user experience)
✗ Tracking pixels visible (load scripts, not visible)

### Copyright Year Automation

**Using JavaScript:**
```html
<p>&copy; <span id="year"></span> Company, Inc.</p>
<script>
  document.getElementById('year').textContent = new Date().getFullYear();
</script>
```

---

## Newsletter Signup in Footer

### Basic Email Signup

```
Get updates
[Email input field]
[Subscribe button]
```

**Placement:** Right column or separate row
**Input:** 44-48px height, 200-250px width
**Button:** 48px height, 100px width
**Gap:** 12px between input and button

### Form on Mobile

```
Email input (full width)
[12px gap]
Subscribe button (full width)
```

### Styling

**Email input:**
- Placeholder: "your@email.com"
- Border: 1px gray
- Padding: 12px horizontal
- Corner radius: 4px

**Button:**
- Primary color background
- White text
- Cursor: pointer on hover

**Helper text (optional):**
- "We send newsletters weekly. Unsubscribe anytime."
- 11px gray, below form

---

## Social Media Icons in Footer

### Icon Sizing

**Desktop:** 24-28px
**Tablet:** 24px
**Mobile:** 20px

### Common Platforms (Order)

1. LinkedIn (B2B, corporate)
2. Twitter/X (company news)
3. Facebook (community, reach)
4. Instagram (visual brand)
5. YouTube (video content)
6. GitHub (dev/tech companies)

### Icon Styling

**Style:** Outline (not filled, less heavy)
**Color:** Gray (#666) by default
**Hover:** Brand color or darker
**Link:** Ensure external links open in new tab

```html
<a href="https://twitter.com/company" target="_blank" rel="noopener noreferrer">
  <svg>...</svg>
</a>
```

### Spacing Between Icons

**Gap:** 12-16px between icons
**Alignment:** Center or left-aligned
**Padding:** 8px around each icon (touch target)

---

## Footer Accessibility

- [ ] Logo links to homepage (expect behavior)
- [ ] All links have descriptive text (not "click here")
- [ ] Color contrast: 4.5:1 for links and text
- [ ] Links distinguishable from text (underline or color)
- [ ] Social icons have aria-labels ("Follow us on Twitter")
- [ ] Newsletter form has proper labels
- [ ] Keyboard navigation works (Tab through all links)
- [ ] Focus ring visible on all interactive elements
- [ ] No keyboard traps (can Tab out of footer)

---

## Footer Anti-Patterns

### ❌ Too Many Links

```
50+ links, 10+ columns
(Overwhelming, hard to scan)
```

**Fix:** Limit to 20-30 relevant links, 3-5 columns.

### ❌ No Clear Visual Hierarchy

```
All text same size and color
(Hard to distinguish sections)
```

**Fix:** Section headers bold, 14px; links 12px gray.

### ❌ Outdated Copyright Year

```
© 2022 Company (current year is 2026)
(Looks abandoned)
```

**Fix:** Use JavaScript to auto-update year.

### ❌ Non-responsive Footer

```
5 columns on mobile (squished, unreadable)
```

**Fix:** Redesign to single column on mobile.

### ❌ Broken Links in Footer

```
"Download Guide" links to 404 page
```

**Fix:** Quarterly audit of all footer links.

