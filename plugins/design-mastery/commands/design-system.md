---
name: Design System
description: "Set up a complete design system in Figma with file structure, components, tokens, and documentation."
---

# Design System

Build a complete design system in Figma for your team. This provides file organization structure, component setup, design tokens, and documentation templates.

---

## What This Command Does

You describe your design needs, and I'll provide:
- Figma file structure and page hierarchy
- Design tokens setup (colors, typography, spacing)
- Component library organization and naming
- Variant and state patterns
- Auto layout configuration
- Documentation template
- Team onboarding guide
- Version control strategy

**Time to answer:** 3-5 minutes
**Time to receive system:** 15-20 minutes

---

## Scoping Questions

**QUESTION 1: What's your design system for?**

Choose one:
- **Website/Marketing site** (web pages, landing pages)
- **SaaS/Web App** (internal tools, dashboards)
- **Mobile App** (iOS, Android, or both)
- **E-commerce** (Shopify, product pages)
- **Brand/Multi-product** (multiple products, unified brand)
- **Component Library** (reusable components for multiple projects)

---

**QUESTION 2: Team size**

How many people will use this design system?
- 1-2 (solo designer, small team)
- 3-5 (design team)
- 6-10 (design + product team)
- 10+ (enterprise)

---

**QUESTION 3: Scope**

What components do you need to include?

*Core (always needed):*
- Buttons, links, inputs, dropdowns, forms
- Cards, containers, sections
- Navigation, headers, footers
- Typography, spacing, colors

*Optional (choose what applies):*
- Data tables, charts, graphs
- Modals, popovers, tooltips
- Sliders, carousels, tabs
- Icons, illustrations
- Animations, transitions

---

**QUESTION 4: Design tool ecosystem**

What tools does your team use?
- Figma only
- Figma + Webflow (for implementation)
- Figma + Dev handoff (to engineers)
- Figma + other design tools

---

## Design System Structure

I'll provide a complete Figma setup based on your answers. Here's the typical structure:

### FIGMA FILE ORGANIZATION

```
Design System (Master File)
├─ 📋 COVER
│  └─ Title page, versioning, team info
├─ 📚 REFERENCE
│  └─ Brand guidelines, color palette, typography specs
├─ 🎨 FOUNDATIONS
│  ├─ Colors & Tokens
│  ├─ Typography & Styles
│  ├─ Icons & Illustrations
│  ├─ Spacing & Grid
│  └─ Shadows & Effects
├─ 🧩 COMPONENTS
│  ├─ Button Library
│  ├─ Card Library
│  ├─ Form Inputs
│  ├─ Navigation
│  ├─ Modals & Overlays
│  ├─ Data Display
│  ├─ Icons
│  └─ [Project-specific components]
├─ 📱 RESPONSIVE PATTERNS
│  ├─ Desktop Breakpoint (1440px)
│  ├─ Tablet Breakpoint (768px)
│  └─ Mobile Breakpoint (375px)
├─ 🎯 PATTERNS & EXAMPLES
│  ├─ Landing Page Pattern
│  ├─ Dashboard Pattern
│  ├─ Form Pattern
│  └─ [Project-specific patterns]
├─ 🧪 PLAYGROUND
│  └─ Experimentation area (don't lock)
└─ 📋 ARCHIVE
   └─ Deprecated components, previous versions
```

---

## PAGE BREAKDOWN

### PAGE 1: COVER
**Purpose:** Overview and versioning

**Content:**
- Design System title and version (e.g., "v1.0.0")
- Last updated date
- Team members
- Key contacts (design lead, product manager)
- Quick links to sections
- Changelog (what changed since last version)

```
═══════════════════════════════════════
      DESIGN SYSTEM v1.0.0
        Last Updated: March 2026

      Lead Designer: Jane Smith
      Maintained by: Design Team

═══════════════════════════════════════

QUICK LINKS:
• Colors & Tokens
• Typography
• Components
• Responsive Patterns
• Documentation

CHANGELOG v1.0.0:
- Initial release
- 30 components
- Full responsive coverage
```

---

### PAGE 2: REFERENCE
**Purpose:** Brand guidelines and specifications

**Content:**
- Brand values and personality
- Logo usage (don't do's included)
- Color palette (all colors with hex values)
- Typography principles
- Spacing scale
- Accessibility standards (WCAG AA/AAA)
- Grid system (8px base)

```
COLORS:
Primary: #0066FF (rgb 0, 102, 255)
Secondary: #FF6B35 (rgb 255, 107, 53)
Neutral: #F5F5F5 (rgb 245, 245, 245)
Text: #1A1A1A (rgb 26, 26, 26)

TYPOGRAPHY:
Font Family: Inter (sans-serif)
Sizes: 12px, 14px, 16px, 18px, 20px, 24px, 28px, 32px, 40px, 48px

SPACING SCALE:
4px, 8px, 12px, 16px, 24px, 32px, 40px, 48px, 56px, 64px, 80px

BREAKPOINTS:
Mobile: 375px
Tablet: 768px
Desktop: 1440px
```

---

### PAGE 3: FOUNDATIONS - COLORS

**Purpose:** Design tokens for colors

**Content:**
- All brand colors with names
- HEX, RGB, CMYK values
- Color swatches
- Semantic naming (primary, secondary, success, error, etc.)
- Color usage guide

```
PRIMARY BLUE
Light:    #E6F2FF (hex)
Normal:   #0066FF (hex)  ← Main brand color
Dark:     #0052CC (hex)  ← Hover/active
Darkest:  #003D99 (hex)  ← Pressed

STATUS COLORS
Success:  #2E7D32 (green)
Warning:  #ED6C02 (orange)
Error:    #D32F2F (red)
Info:     #0288D1 (blue)

NEUTRAL
White:    #FFFFFF
Light:    #F5F5F5
Medium:   #BDBDBD
Dark:     #616161
Black:    #1A1A1A
```

---

### PAGE 4: FOUNDATIONS - TYPOGRAPHY

**Purpose:** Font styles and sizing

**Content:**
- Font files available
- Size scale with line heights
- Weight hierarchy
- Usage examples
- Character width guidelines

```
FONT: Inter (sans-serif, weights: 400, 500, 600, 700)

SIZES & USAGE:
H1: 48px, 700 bold, 1.2 line-height (page titles)
H2: 40px, 700 bold, 1.3 line-height (section titles)
H3: 28px, 600 medium, 1.3 line-height (subsection)
Body: 16px, 400 regular, 1.5 line-height (paragraphs)
Small: 14px, 400 regular, 1.4 line-height (labels, captions)
Tiny: 12px, 500 medium, 1.3 line-height (microcopy)

WEIGHT HIERARCHY:
600+ = headings, important info
500 = labels, secondary info
400 = body text, standard

MAX CHARACTER WIDTH:
60-75 chars per line (for readability)
```

---

### PAGE 5: FOUNDATIONS - SPACING & GRID

**Purpose:** Spacing scale and grid system

**Content:**
- Spacing scale values
- Grid system (8px base)
- Padding and margin guide
- Breakpoint-specific spacing

```
SPACING SCALE (8px base):
4px   (xs)
8px   (s)
12px  (m)
16px  (m)
24px  (l)
32px  (xl)
40px  (2xl)
48px  (3xl)
56px  (4xl)
64px  (5xl)
80px  (6xl)

GRID SYSTEM:
Base: 8px
Columns: 12 columns
Gutter: 16px (desktop), 12px (tablet), 8px (mobile)
Container padding: 60px (desktop), 40px (tablet), 20px (mobile)

COMPONENT SPACING:
Button padding: 8px 16px (small), 12px 24px (medium), 16px 32px (large)
Card padding: 20px or 24px
Section padding: 60-80px top/bottom (desktop)
```

---

### PAGE 6+: COMPONENTS

**Purpose:** Component library organized by category

**Structure:**
```
BUTTONS
├─ Button Primary (Large, Medium, Small)
├─ Button Secondary
├─ Button Tertiary
├─ Button Danger
├─ Button Disabled
└─ Button States (Default, Hover, Active, Loading, Error)

FORMS
├─ Text Input
├─ Email Input
├─ Select Dropdown
├─ Checkbox
├─ Radio Button
├─ Toggle Switch
├─ Textarea
└─ Form States (Default, Focused, Filled, Error, Disabled)

CARDS
├─ Card Basic
├─ Card with Image
├─ Card Feature
├─ Card Testimonial
└─ Card States (Default, Hover)

NAVIGATION
├─ Top Navigation Bar
├─ Sidebar Navigation
├─ Breadcrumbs
├─ Tabs
├─ Dropdown Menu
└─ Mobile Hamburger Menu

MODALS & OVERLAYS
├─ Modal Dialog
├─ Alert Dialog
├─ Popover
├─ Toast Notification
└─ Tooltip

DATA DISPLAY
├─ Data Table (with sorting, pagination)
├─ Metric Card
├─ Chart/Graph (line, bar, pie)
├─ Status Badge
└─ Progress Bar

ICONS
├─ Icon Set (16px, 24px, 32px)
└─ Icon Usage Guidelines
```

**For Each Component:**

1. **Master Component** (the source)
   - Base style (default state)
   - All variants (primary, secondary, small, medium, large, etc.)
   - All states (default, hover, active, disabled, loading, error)

2. **Component Documentation**
   - What is it for?
   - When to use
   - Do's and don'ts
   - States and variations
   - Color and sizing options

3. **Copy to Projects**
   - Instructions for designers to use component
   - How to swap variants
   - How to customize if needed

---

## DESIGN TOKENS SETUP

**In Figma:**

### Color Tokens
```
Primary Blue:      hex #0066FF
Primary Blue Hover: hex #0052CC
Text Dark:         hex #1A1A1A
Text Light:        hex #666666
Background:        hex #FFFFFF
Border:            hex #E0E0E0
```

### Spacing Tokens
```
Space XS: 4px
Space S:  8px
Space M:  12px / 16px
Space L:  24px / 32px
Space XL: 40px / 48px
Space 2XL: 56px / 64px / 80px
```

### Typography Tokens
```
Heading Large:   48px, 700, 1.2 line-height
Heading Medium:  32px, 700, 1.3 line-height
Heading Small:   24px, 600, 1.4 line-height
Body:           16px, 400, 1.5 line-height
Label:          14px, 500, 1.4 line-height
Caption:        12px, 400, 1.3 line-height
```

**In Webflow:**
- Create CSS variables for colors, spacing, typography
- Reference variables in all components
- Update one place, affects entire site

---

## COMPONENT NAMING CONVENTION

**Use a consistent naming pattern (BEM-inspired):**

```
ButtonPrimary
ButtonPrimary/Small
ButtonPrimary/Medium
ButtonPrimary/Large
ButtonPrimary/State=Hover
ButtonPrimary/State=Disabled
ButtonPrimary/State=Loading

CardFeature
CardFeature/ImagePosition=Top
CardFeature/ImagePosition=Side
CardFeature/State=Hover

FormInput
FormInput/Type=Text
FormInput/Type=Email
FormInput/State=Focused
FormInput/State=Error
```

**Pattern:** `ComponentName/Property=Value`

---

## FIGMA BEST PRACTICES

### Auto Layout Setup
- Use Auto layout on all components
- Set consistent spacing (from token scale)
- Set alignment (center, space-between, etc.)
- Document how components resize

### Variants
- Use Figma variants for states
- Group similar variants together
- Document what each variant does
- Show all variants on same artboard

### Component Organization
- Use groups for related components
- Alphabetical ordering within groups
- Lock master components (prevent edits)
- Archive old components (keep history)

### Documentation
- Add description to each component
- Link to usage guidelines
- Show do's and don'ts
- Include interaction details

---

## TEAM ONBOARDING GUIDE

**New team member should learn:**

1. **File Structure** (where everything lives)
2. **Component Library** (how to use components)
3. **Design Tokens** (colors, spacing, typography rules)
4. **Naming Conventions** (component names, layer names)
5. **Updating Components** (how to modify shared components)
6. **Versioning** (how to handle updates)
7. **Handoff to Dev** (how to prepare for engineering)

**Onboarding Checklist:**
- [ ] Access to design system file
- [ ] Walkthrough of file structure
- [ ] How to find components
- [ ] How to use variants
- [ ] How to handle colors/spacing tokens
- [ ] What to do if component is missing
- [ ] How to request component updates
- [ ] Design critique process

---

## MAINTENANCE & VERSIONING

**Version numbers:** Major.Minor.Patch (e.g., 1.2.3)

**When to increment:**

- **Major (1.0 → 2.0):** Breaking changes (button colors change completely)
- **Minor (1.0 → 1.1):** New components, new features
- **Patch (1.0 → 1.0.1):** Bug fixes, small tweaks

**Changelog:** Keep in COVER page
```
v1.2.1 (March 15, 2026)
- Fixed button hover state contrast
- Added new tooltip component
- Updated spacing token documentation

v1.2.0 (March 1, 2026)
- Added data table component
- New metric card variants
- Updated typography scale

v1.0.0 (January 1, 2026)
- Initial release
- 25 core components
```

---

## IMPLEMENTATION: WEBFLOW INTEGRATION

**Bridge Figma to Webflow:**

1. **Use same naming** (Figma names match Webflow class names)
2. **Document breakpoints** (show responsive behavior in Figma)
3. **Show states** (hover, focus, active, disabled in Figma)
4. **Provide design specs** (padding, colors, font sizes exact)
5. **Export assets** (buttons as images, icons as SVG)

**Handoff Document:** Create a Figma page titled "HANDOFF" that shows:
- Component specs (exact measurements)
- Color values (HEX for CSS)
- Typography (font, size, weight, line-height)
- Spacing (all padding/margin values)
- Interactions (hover effects, animations)

---

## Complete Setup Checklist

**Foundations:**
- [ ] Cover page created
- [ ] Reference/guidelines page created
- [ ] Color tokens defined (with hex values)
- [ ] Typography scale defined
- [ ] Spacing scale defined
- [ ] Grid system documented

**Components:**
- [ ] All core components created
- [ ] All variants defined
- [ ] All states documented
- [ ] Component naming consistent
- [ ] Master components locked
- [ ] Component usage documented

**Documentation:**
- [ ] Component library page created
- [ ] Do's and don'ts examples
- [ ] Responsive breakpoint examples
- [ ] Team onboarding guide
- [ ] Changelog started

**Team:**
- [ ] All team members have access
- [ ] Team trained on system
- [ ] Update process documented
- [ ] Feedback mechanism established

---

## Next Steps

Based on your design system setup:

1. **Use `/responsive-layout`** to create responsive patterns with components
2. **Use `/component-pattern`** to refine individual component designs
3. **Use `figma-workflows` skill** for deeper Figma techniques
4. **Use `animation-interactions`** to add component animations

---

## Pro Tips

**For Design Systems:**
- **Start small** (5-10 core components, not 100)
- **Document as you go** (don't defer documentation)
- **Get feedback early** (validate with team before going too far)
- **Version from the start** (makes updates easier)
- **Keep it organized** (naming and structure consistency matters)

**For Maintenance:**
- **Review quarterly** (what's missing? what's outdated?)
- **Gather feedback** (surveys, tickets, discussions)
- **Update proactively** (don't let system become stale)
- **Communicate changes** (notify team of new components)
- **Archive deprecated** (don't delete, keep history)

---

## Ready?

Tell me:
1. **What's your design system for** (website, SaaS, mobile, etc.)?
2. **How many people** will use it?
3. **What components** do you need?
4. **Will it integrate** with Webflow or other tools?

I'll create:
- Complete Figma file structure
- Component organization plan
- Design tokens setup
- Documentation templates
- Team onboarding guide
- Maintenance schedule

Let's build your design system!
