---
name: Design Audit
description: "Review and critique an existing design with systematic checklist, specific issues, and recommended fixes."
---

# Design Audit

Review any design (website, app, component) with a systematic critique methodology. Identify specific issues and get actionable recommendations for improvement.

---

## What This Command Does

You provide a design (screenshot, link, or description), and I'll:
- Conduct a systematic visual audit using design principles
- Identify specific typography, color, layout, and hierarchy issues
- Provide concrete fixes with before/after comparisons
- Explain why issues matter and how to improve them
- Rate overall design quality with rationale
- Suggest which skills to dive into for deeper improvement

**Estimated Time:** 10-20 minutes depending on complexity

---

## Setup Questions

To conduct the best audit, answer these briefly:

**QUESTION 1: What is the design?**
Share a screenshot, link, or description. What is this design for? (website, app, component, etc.)

---

**QUESTION 2: What's the context?**
Who is the target user? What is the primary goal? (This helps me critique appropriately.)

*Examples: "Mobile app for fitness tracking, primary goal is daily workout logging," "E-commerce product page, goal is to convert browsers to buyers"*

---

**QUESTION 3: What aspect to focus on?** (Optional)
Is there a specific area you want me to focus on? (typography, layout, color, interactions, etc.) Or should I do a full comprehensive audit?

---

## The Audit Methodology

I'll review the design systematically across these categories:

### 1. TYPOGRAPHY AUDIT
✓ Font sizes (are there too many? do they create clear hierarchy?)
✓ Font weights (is hierarchy obvious?)
✓ Line heights (is text readable?)
✓ Font families (do they work together?)
✓ Contrast (text vs. background readable?)
✓ Character width per line (readable length?)

**Red flags:**
- ❌ More than 3 font sizes
- ❌ More than 2 font families
- ❌ Line height less than 1.4x font size
- ❌ Text contrast fails WCAG AA standards
- ❌ Line length over 75 characters (desktop)

---

### 2. COLOR AUDIT
✓ Color harmony (primary/secondary/neutral well-defined?)
✓ Contrast ratio (text meets WCAG AA minimum 4.5:1?)
✓ Consistency (are colors used intentionally?)
✓ Emotional alignment (do colors match brand/purpose?)
✓ Accessibility (no color-only information?)

**Red flags:**
- ❌ Contrast below 4.5:1 for body text
- ❌ More than 5 primary colors
- ❌ Colors used inconsistently
- ❌ Status communicated by color alone
- ❌ Pastel text on light background

---

### 3. LAYOUT & SPACING AUDIT
✓ Alignment (is everything aligned to a grid?)
✓ Negative space (is whitespace used effectively?)
✓ Grouping (related items grouped visually?)
✓ Hierarchy (important elements stand out?)
✓ Responsive behavior (how does it scale?)

**Red flags:**
- ❌ Random spacing (not consistent increments)
- ❌ Everything crammed together
- ❌ Alignment appears accidental
- ❌ No clear visual grouping
- ❌ Doesn't scale to mobile

---

### 4. COMPONENT CONSISTENCY AUDIT
✓ Buttons (all similar buttons styled identically?)
✓ Cards (are cards consistent?)
✓ Forms (consistent input styles?)
✓ Icons (icon set cohesive?)
✓ States (hover, active, disabled consistent?)

**Red flags:**
- ❌ Similar components look different
- ❌ Buttons have inconsistent sizes/colors
- ❌ No visible hover states
- ❌ Disabled state not clear
- ❌ Mixed icon styles

---

### 5. VISUAL HIERARCHY AUDIT
✓ Most important element draws eye first?
✓ Secondary elements clear?
✓ Supporting information de-emphasized?
✓ CTA prominent?
✓ Content scannability?

**Red flags:**
- ❌ Important info buried
- ❌ Everything same visual weight
- ❌ Multiple CTAs compete for attention
- ❌ Can't scan page in 5 seconds
- ❌ Focal point unclear

---

### 6. ACCESSIBILITY CHECK
✓ Color contrast adequate?
✓ Text sizes readable?
✓ Form labels present?
✓ Interactive elements clear?
✓ Mobile usable?

**Red flags:**
- ❌ Contrast below WCAG AA
- ❌ Text too small
- ❌ Unlabeled form inputs
- ❌ Hover-only information
- ❌ Not mobile responsive

---

## The Output

Based on the audit, you'll receive:

### ✓ OVERALL SCORE
**A (90-100):** Strong design, minor refinements
**B (80-89):** Good design, clear improvement areas
**C (70-79):** Acceptable design, needs attention
**D (Below 70):** Significant issues to address

---

### ✓ ISSUE SUMMARY
List of specific issues organized by category:

**Critical Issues** (must fix)
- Issue description
- Why it matters
- Recommended fix

**Important Issues** (should fix)
- Issue description
- Why it matters
- Recommended fix

**Nice-to-Haves** (could improve)
- Suggestion
- Why it would help
- How to implement

---

### ✓ DETAILED RECOMMENDATIONS

For each issue:
1. **The Problem:** What's wrong?
2. **Why It Matters:** Impact on user experience
3. **The Fix:** Specific recommendation
4. **Before/After:** Visual comparison (described)
5. **How to Implement:** Specific steps

---

### ✓ PRIORITY ROADMAP

Issues ranked by impact:
1. High-impact, quick fixes
2. High-impact, bigger changes
3. Medium-impact improvements
4. Polish and refinement

---

### ✓ WHICH SKILLS TO USE

Based on issues found, I'll recommend which skills to dive into:
- **visual-foundations** — Typography, color, hierarchy issues
- **ui-components** — Component consistency
- **web-layout** — Layout and spacing
- **animation-interactions** — Interaction feedback
- **web-design-audit** — Deep dive into methodology

---

## Common Issues I Look For

### Typography Issues (40% of designs)
- ❌ Too many font sizes (lack of constraint)
- ❌ Hierarchy unclear (size differences too small)
- ❌ Line height too tight (hard to read)
- ❌ Font pairing awkward (don't work together)
- ❌ Contrast too low (gray on light gray)

### Spacing Issues (35% of designs)
- ❌ Spacing not consistent (some 8px, some 12px, some 16px)
- ❌ Elements crowded (no breathing room)
- ❌ Elements disconnected (grouping unclear)
- ❌ Margins vs. padding confused
- ❌ Whitespace wasted (too much empty space)

### Color Issues (25% of designs)
- ❌ Too many colors (5-6 primary colors)
- ❌ Contrast fails (text unreadable)
- ❌ Colors used inconsistently (primary button sometimes blue, sometimes green)
- ❌ Emotional mismatch (playful colors for financial app)
- ❌ Status only by color (red = error, but what about colorblind users?)

### Hierarchy Issues (30% of designs)
- ❌ Everything same size
- ❌ Important info tiny
- ❌ CTA doesn't stand out
- ❌ Multiple competing focal points
- ❌ Can't scan in 5 seconds

### Component Consistency (40% of designs)
- ❌ Buttons look different
- ❌ Cards have inconsistent styling
- ❌ Form inputs not aligned
- ❌ Hover states missing
- ❌ Icons don't match in style

---

## Example Audit Outcome

**Design:** E-commerce product page

**Overall Score:** B- (78/100)

**Critical Issues:**
1. Text contrast: Gray text (#888) on light gray background (#f5f5f5) = 2.1:1 contrast (needs 4.5:1)
   - Fix: Use #333 for body text (7.2:1 contrast)

2. Form inputs: No visible focus state or label
   - Fix: Add blue border on focus, label above input

**Important Issues:**
3. Button sizing: Primary button 32px height, secondary button 28px height (inconsistent)
   - Fix: Standardize to 40px for all buttons

4. Spacing: Product description section has 20px top margin, related products has 40px (inconsistent rhythm)
   - Fix: Use consistent 24px spacing between sections

**Skills to Reference:**
→ **visual-foundations** for contrast and hierarchy
→ **ui-components** for button and form standardization
→ **web-layout** for spacing consistency

---

## Pro Tips for Better Audits

**For Screenshots:**
- Full page screenshot preferred (shows entire context)
- Multiple screens help (shows consistency across sections)
- Mobile AND desktop recommended (different layouts)

**For Links:**
- Share actual URL (I can review live and responsive)
- Mention specific page if large site

**For Descriptions:**
- "I have a Shopify store" is vague
- "Shopify store selling fitness gear, main issue is product page feels cramped" is helpful

**For Context:**
- Telling me the target user helps me critique appropriately
- "This is for corporate executives" vs. "This is for Gen Z" = different standards

---

## Ready to Audit?

Share:
1. Screenshot, link, or description of the design
2. What it's for and who uses it
3. Any specific areas to focus on (optional)

I'll conduct a comprehensive systematic audit and give you specific, actionable recommendations!

---

## Next Steps After Audit

Based on issues found, jump to:
- **visual-foundations** skill to learn typography, color, spacing rules
- **ui-components** skill to fix component consistency
- **web-layout** skill to redesign layout and spacing
- **animation-interactions** skill to add missing hover/interaction feedback

Use the audit issues as your checklist for what to improve!
