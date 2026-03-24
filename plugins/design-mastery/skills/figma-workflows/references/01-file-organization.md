# Figma File Organization: Step-by-Step Setup

This is your complete walkthrough for setting up a Figma file from zero to production-ready.

---

## Pre-Setup Checklist

Before opening Figma:

- [ ] Project name finalized
- [ ] Project brief documented
- [ ] Discovery completed (complexity assessed)
- [ ] Sitemap/information architecture ready
- [ ] Wireframes done (if medium/high complexity)
- [ ] Brand colors identified
- [ ] Typography choices made
- [ ] Spacing scale agreed upon

---

## Step-by-Step Setup

### Step 1: Create Project Folder

1. Go to Drafts in Figma
2. Create new file
3. Rename: "[Project Name] - Design"
4. Move to project folder (if team has folders)
5. If starting from template, duplicate template file

### Step 2: Create Cover Page

1. Create new page: "Cover"
2. Design a cover that represents the project
3. Include:
   - Project name
   - Date
   - Your name/company
   - Project status (In Progress, Final, etc.)

**Why:** Cover page immediately signals this is organized work. Shows professionalism in stakeholder reviews.

**You can fill in details later**—it's not blocking your actual design work.

### Step 3: Create Divider Page

1. Create new page: "---"
2. Leave it mostly empty
3. Add visual divider (dashed line or empty space)

**Why:** Creates visual break between cover and working pages.

### Step 4: Create References Page

1. Create new page: "References"
2. Copy/paste everything here:
   - Competitor screenshots
   - Previous projects you want to reference
   - Inspiration from Pinterest/Dribbble
   - Color palettes you're considering
   - Typography samples
   - UI audits of competitors
   - Any research visuals

**Organization:** Don't organize this page. Mess = thinking.

**Format:** Can use vector files from past projects OR screenshots.

**Goal:** Have all inspiration in one place. No hunting through browser tabs during design.

### Step 5: Create Explorations Page

1. Create new page: "Explorations"
2. This is your playground
3. Duplicate reference elements and modify
4. Experiment freely—no polish needed
5. Try multiple directions, colors, typographies

**Organization:** None. This page should be messy.

**Purpose:** Where bad ideas become good ideas through iteration.

**Don't judge:** Every bad direction teaches you something.

### Step 6: Create Research Page (Time-Stamped)

1. Create new page: "Research - March 2nd"
2. This documents your decision-making
3. Take screenshots of key decisions
4. Annotate why you're choosing something
5. Show what you want to present to users

**When to add to this page:**
- After exploring multiple directions
- When you want to lock direction
- Before presenting to stakeholders

**Content:**
- Screenshots of chosen direction
- Comparison of 2-3 directions
- Notes on what you learned
- Color palette evolution
- Typography decisions

---

## Step 7: Create Presentations Page (Time-Stamped)

1. Create new page: "Presentation - March 3rd"
2. This is client-ready screenshots
3. Locked-in-time version for stakeholder review

**Placement:** Put BELOW milestones page. People should see actual final work first (above), then presentation context.

**Content:**
- Final design screenshots
- Specific focus areas
- Annotated interactions
- Before/after comparisons
- Call-to-actions visible

**Why time-stamp:** Shows evolution. "We tried X on March 1st, then refined to Y by March 5th."

---

## Step 8: Create Milestone Pages

1. Create divider page: "=== PRODUCTION MILESTONES ===" (to separate from working pages)
2. Create pages: M0, M1, M2, M3 (as needed)

**Naming milestones:**
- M0 = MVP or initial deliverable
- M1 = Refined version after feedback
- M2 = Second round of refinements
- M3 = Final polish

**Example naming:**
- "M0 - Home & Category Pages ✓"
- "M1 - Product Detail (In Progress)"
- "M2 - Cart & Checkout ✓"

**Mark final with ✓:**
- ✓ = locked, final version
- (In Progress) = not complete yet

**Content of milestone page:**
- Final artboards for each page
- Clean, organized frames
- All states documented (hover, active, disabled, loading, error)
- Proper naming conventions
- Components used throughout
- Spacing/alignment rules visible

---

## Organizing Within Pages

### Cover Page Example

```
[Project Name]
[Subtitle/tagline]
[Date: March 2026]
[Your Name/Company]
Status: Design in Progress
Version: 2.0
```

Keep simple. One visual focal point.

### References Page Example

No organization. Dump everything:
- Competitor 1 screenshot (full page)
- Competitor 2 screenshot
- Color palette inspiration
- Typography samples
- Logo variations
- UI patterns you like
- Previous project hero section
- All loose on the page

Messy = working.

### Explorations Page Example

```
Exploration 1 (Dark mode)
  - Color palette: Dark bg, light text
  - Typography: Bold sans-serif
  - Components: Cards, buttons, nav

Exploration 2 (Light mode, playful)
  - Color palette: Light bg, colorful accents
  - Typography: Rounded sans-serif
  - Components: Cards, buttons, nav

Exploration 3 (Minimalist)
  - Color palette: Monochromatic grays
  - Typography: Elegant serif
  - Components: Cards, buttons, nav
```

Side-by-side comparison helps see differences.

### Research Page Example (Time-Stamped)

```
Research - March 3rd
  Title: "Color Direction Decision"

  Option A (chosen):
  [Screenshot of design with colors]
  Notes: "Aligns with brand. Good contrast. Modern feel."

  Option B (tested):
  [Screenshot of design with colors]
  Notes: "Too similar to competitor. Felt dated."

  Option C (tested):
  [Screenshot of design with colors]
  Notes: "Good but too playful for this brand."
```

Documents thinking for future reference.

### Milestone Page Example (M0)

```
M0 - Home Page ✓

[Home page artboard - final]
[All assets placed]
[Typography styles applied]
[Color styles applied]
[Components used]
[Spacing documented]

[Variants shown:]
- Hero state 1
- Hero state 2
- CTA states (hover, active, disabled)
```

Production-ready, no mess.

---

## Page Ordering (Critical)

Your page order should ALWAYS be:

1. Cover
2. ---
3. References
4. Explorations
5. Research - [Date]
6. Presentation - [Date]
7. === PRODUCTION MILESTONES ===
8. M0 - [Page name] ✓
9. M1 - [Page name] (In Progress)
10. M2 - [Page name] (Pending)

**Why this order:**
- Cover first: Professional impression
- References/Explorations middle: Working pages (not shown to clients)
- Presentations/Milestones last: Final work
- Milestones at end: Developers/stakeholders look here first

---

## Creating Design System Documentation (Within File)

### Colors Page (Optional)

Create a page that shows your color palette:

```
PRIMARY
[Color box] #0066CC - Primary Blue
  Used for: CTAs, brand elements
  Contrast on white: 7.0 AAA

SECONDARY
[Color box] #FF6600 - Orange
  Used for: Accents, hover states
  Contrast on white: 5.2 AA

NEUTRALS
[Color box] #1A1A1A - Black (text)
[Color box] #757575 - Gray (secondary text)
[Color box] #F5F5F5 - Light gray (bg)
[Color box] #FFFFFF - White
```

This becomes a checklist during design.

### Typography Page (Optional)

Create a page showing all type styles:

```
H1 | 48px, 700 weight | Line height 120%
  "This is a page headline example"

H2 | 32px, 600 weight | Line height 120%
  "This is a section header example"

Body | 16px, 400 weight | Line height 150%
  "This is body copy that readers will spend time with. It should be comfortable to read for extended periods."

Small | 14px, 400 weight | Line height 150%
  "This is for secondary text and captions"
```

Reference sheet for consistency.

### Spacing Scale Page (Optional)

Create a visual reference:

```
4px spacing [visual example]
8px spacing [visual example]
12px spacing [visual example]
16px spacing [visual example]
24px spacing [visual example]
32px spacing [visual example]
```

Quick reference during component design.

---

## Asset Organization Best Practices

### Frame Naming

Name frames clearly for easy export:

```
[Component Name]-[State].png

Example:
Button-Primary-Default
Button-Primary-Hover
Button-Secondary-Default
Input-Text-Default
Input-Text-Focus
Input-Text-Error
Card-Feature
Card-Testimonial
```

Developers know exactly what each export is.

### Exporting

1. Right-click frame
2. "Export" option
3. Choose format (SVG for components, PNG for images)
4. Organize exports folder by type

**Naming structure:**
```
/components
  /buttons
    /primary
      default.svg
      hover.svg
      active.svg
    /secondary
      default.svg
/images
  /hero
    hero-1.png
    hero-2.png
```

---

## Scaling the Structure for Large Projects

### Small Project (5-10 pages)

Use basic structure above. Works fine.

### Medium Project (10-30 pages)

Add section dividers:

```
Cover
---
References
Explorations
Research - March 2nd
Presentation - March 3rd
=== PRODUCTION MILESTONES ===
M0 - Home ✓
M1 - About ✓
M2 - Services (In Progress)
M3 - Contact (In Progress)
```

### Large Project (30+ pages)

Use file structure + multiple design files:

**Main file structure:**
```
Design-System.fig (shared colors, typography, components)
Home-Pages.fig (home, hero, features, testimonials)
Product-Pages.fig (product listing, detail, reviews)
Authentication.fig (login, signup, password reset)
Checkout-Flow.fig (cart, shipping, payment, confirmation)
```

**Within each file:** Follow template structure (Cover, References, Explorations, Research, Presentations, Milestones)

---

## Moving from One Project to Next

After project launches:

1. Archive explorations page (keep for reference)
2. Move final milestones to "Completed" section
3. Remove date-stamps from "Presentation" page
4. Create final documentation page
5. Set file to view-only for historical reference
6. Start NEW file for next project (don't reuse)

---

## Common Organization Mistakes

1. **Everything on one page:** Hundreds of frames = impossible to navigate
   - **Fix:** Use template page structure above

2. **No naming convention:** Frames called "Frame 1," "Rectangle," "Group"
   - **Fix:** Name frames descriptively (Component-State format)

3. **No time-stamps:** Can't tell when decisions were made
   - **Fix:** Date-stamp research and presentation pages

4. **Final work mixed with explorations:** Can't find real deliverables
   - **Fix:** Separate into dedicated Milestones section with checkmarks

5. **Emojis everywhere:** Distraction, hard to parse
   - **Fix:** Use sparingly (✓ = done, others minimal)

6. **No asset exports:** Developers can't find what to build
   - **Fix:** Export organized, named assets to folder structure

---

## File Naming Best Practices

### Project File Naming

```
[Client Name] - [Project Type] - Design
[Client Name] - [Project Type] - Components Library
[Client Name] - [Project Type] - Designs v2.0
```

Examples:
```
Acme Co - Website Redesign - Design
Acme Co - Design System v1.0
Acme Co - Mobile App - Design v2.0
```

**Why clear naming:**
- Easy to find in team workspace
- Version control visible (v1.0, v2.0)
- Multiple projects won't get confused

### Version Numbering

When creating v2.0:

1. Duplicate v1.0 file
2. Rename to v2.0
3. Keep v1.0 for reference
4. Don't update v1.0 (it's history)

**Why:** You can always revert to previous version for comparison.

---

## Handoff Organization

When ready to hand off to developers:

### Prepare the File

1. Clean up any stray elements
2. Ensure all components are organized
3. Hide/delete reference/exploration elements (or move to separate pages)
4. Lock production pages (protect from accidental edits)
5. Create handoff documentation

### Create Export Checklist

Document what to export:
```
BUTTONS
- [ ] Primary/Default
- [ ] Primary/Hover
- [ ] Primary/Active
- [ ] Secondary/Default

CARDS
- [ ] Feature Card
- [ ] Testimonial Card

ICONS
- [ ] Navigation/Home
- [ ] Navigation/Search
- [ ] Navigation/User
```

### Share with Developers

1. Give view-only access to Figma file
2. Provide export folder with all assets
3. Include spacing/sizing spec doc
4. Document color palette (hex codes)
5. Document typography (font families, sizes, weights)
6. Annotate interactions (where animations occur)

---

## File Hygiene Checklist

Before considering file complete:

- [ ] All pages named and ordered correctly
- [ ] Cover page created
- [ ] References page has inspiration
- [ ] Explorations page separate from finals
- [ ] Research page dated and documented
- [ ] Presentation page dated
- [ ] Milestones marked with ✓ if final
- [ ] All frames named clearly
- [ ] Components organized with naming convention
- [ ] Colors documented and styled
- [ ] Typography documented and styled
- [ ] Spacing documented visually
- [ ] No stray elements or "Frame 1" naming
- [ ] Asset exports organized
- [ ] Handoff documentation created

---

## Tools & Shortcuts

**Keyboard shortcuts:**
- Cmd+A (Mac) / Ctrl+A (Windows): Enable auto layout
- Cmd+Shift+G: Group selection
- Cmd+D: Duplicate selection
- Cmd+T: Add text
- Cmd+K: Create component

**Plugins to consider:**
- Figma Tokens (design token management)
- Master (find and replace)
- Rename It (batch rename frames)
- Autoflow (auto-connect frames in prototypes)

---

## Final Note

Your file structure is a communication tool. When someone opens your file 6 months later, they should understand:
- What the project is (Cover)
- What you researched (References)
- What you tried (Explorations)
- What you learned (Research)
- What you presented (Presentations)
- What was built (Milestones)

Good organization makes design collaboration seamless.
