# Design Systems: Setup in Figma

A design system is a living library of reusable components, styles, and patterns. These exact specifications enable teams to design consistently and developers to build efficiently.

---

## What is a Design System?

**Definition:** A connected, package-managed, version-controlled software product that contains the smallest set of components and guidelines a particular organization needs to make digital products consistently, efficiently, and happily.

**In practice:** Figma file with:
- Color styles (all brand colors)
- Typography styles (all text treatments)
- Components (reusable UI elements)
- Guidelines (documentation)

**Benefits:**
- Consistency across products
- Faster design (reuse, not rebuild)
- Easier collaboration (shared language)
- Faster development (documented specifications)
- Scalability (grow without chaos)

---

## Color Styles Setup

### Creating Color Styles

1. **Create a color** (fill, stroke, or text)
2. **Open color picker**
3. **Click the styles icon** (4 dots next to hex code)
4. **Click + button** "Create color style"
5. **Name it** using naming convention

### Color Style Naming

```
Color Type/Shade

Primary/Base
Primary/Light
Primary/Dark
Secondary/Base
Neutral/Black
Neutral/Dark
Neutral/Medium
Neutral/Light
Neutral/White
Success/Base
Error/Base
Warning/Base
```

### Color Palette Organization

**Recommended structure:**

```
Colors/
├── Brand
│   ├── Primary/Base
│   ├── Primary/Light
│   ├── Primary/Dark
│   ├── Secondary/Base
│   └── Secondary/Dark
├── Semantic
│   ├── Success
│   ├── Error
│   ├── Warning
│   └── Info
└── Neutral
    ├── Black
    ├── Dark Gray
    ├── Medium Gray
    ├── Light Gray
    └── White
```

### Using Color Styles

When designing:
- Use color styles, NOT manual colors
- If you manually pick a color: Convert to style
- Using styles = one change updates everywhere

**Workflow:**
1. Select element
2. Open fill/stroke panel
3. Click color → select style
4. Done (linked to style)

### Updating Colors

1. Right-click color style
2. "Edit color style"
3. Change hex code
4. All elements using that style update automatically

---

## Typography Styles Setup

### Creating Typography Styles

1. **Create text element** with your desired styling
2. **Set font family, size, weight, line height, letter spacing**
3. **Select text layer**
4. **Open typography panel** (right side)
5. **Click styles icon** (4 dots)
6. **Click + button** "Create text style"
7. **Name it** using convention

### Typography Style Naming

```
Text Role/Context

H1
H2
H3
Body
Body Small
Caption
Button
Label
Link
```

Or more descriptive:

```
Heading/Large (48px)
Heading/Medium (32px)
Heading/Small (24px)
Paragraph/Standard (16px)
Paragraph/Small (14px)
Small Text/Caption (12px)
Button Text (14px, semi-bold)
```

### What to Include in Style

**Required:**
- Font family
- Font size
- Font weight
- Line height

**Recommended:**
- Letter spacing (if using tight spacing)
- Text transform (if always uppercase)

**Don't include:**
- Color (use separate color styles)
- Opacity (override as needed)

### Typography Style Organization

```
Typography/
├── Headings
│   ├── H1 (48px)
│   ├── H2 (32px)
│   ├── H3 (24px)
│   └── H4 (20px)
├── Body
│   ├── Large (18px)
│   ├── Standard (16px)
│   ├── Small (14px)
│   └── X-Small (12px)
├── Interactive
│   ├── Button (14px, semi-bold)
│   ├── Link (16px, regular)
│   └── Label (12px, regular)
└── Special
    ├── All Caps (12px, bold, -2% letter spacing)
    ├── Hero (96px, bold)
    └── Caption (11px, gray)
```

### Using Typography Styles

When designing:
1. Create text element
2. Select text layer
3. Open typography panel
4. Click the style icon
5. Select from list

**Example:** "Body/Standard" applies 16px, regular weight, 150% line height automatically.

### Updating Typography

1. Right-click typography style
2. "Edit text style"
3. Change any property
4. All text using that style updates automatically

---

## Component Library Documentation

### Component Naming Convention (Recap)

```
ComponentName/Variant/State

Button/Primary/Default
Button/Primary/Hover
Button/Secondary/Default
Card/Feature/Default
Card/Feature/Hover
Input/Text/Default
Input/Text/Focus
Input/Text/Error
Navigation/Desktop/Default
Navigation/Mobile/Closed
Navigation/Mobile/Open
```

### Component Organization

```
Components/
├── Foundations
│   ├── Icon/Small
│   ├── Icon/Medium
│   ├── Icon/Large
│   ├── Badge
│   └── Divider
├── Buttons
│   ├── Button/Primary
│   ├── Button/Secondary
│   ├── Button/Ghost
│   └── Button/Icon
├── Cards
│   ├── Card/Feature
│   ├── Card/Testimonial
│   ├── Card/Product
│   └── Card/Small
├── Forms
│   ├── Input/Text
│   ├── Input/Select
│   ├── Input/Checkbox
│   └── Input/Radio
├── Navigation
│   ├── Navigation/Desktop
│   ├── Navigation/Mobile
│   └── MenuDropdown
└── Modals
    ├── Modal/Confirmation
    ├── Modal/Alert
    └── Modal/Form
```

### Component Specifications

For each component, document:

```
## Button/Primary

**Purpose:** Primary call-to-action button

**Use when:**
- Main action on a page
- Form submission
- Enrollment or signup
- Primary CTA

**Don't use for:**
- Secondary actions (use Button/Secondary)
- Links or navigation (use Link component)
- Tertiary actions (use Button/Ghost)

**States:**
- Default: Normal, ready to click
- Hover: Color change, slight scale up
- Active: Darker shade, pressed feel
- Disabled: Gray, no interaction
- Loading: Spinner replaces text

**Size:** Medium (standard)
- Height: 40px (48px tap target)
- Padding: 12px vertical, 16px horizontal
- Min-width: 100px

**Typography:** Button/Medium (14px, semi-bold)
**Color:** Primary/Base
**Border Radius:** 4px
**Icon:** Optional, 16px, left of text
**Spacing:** 8px gap between icon and text

**Variations:**
- Size: Can be Small (32px), Medium (40px), Large (48px)
- Icon: With or without icon
- Width: Fixed or full-width
```

---

## Design Tokens Documentation

Create a living document of all design decisions:

### Token Categories

```
# Design Tokens

## Colors
- Primary: #0066CC
- Primary Light: #E6F2FF
- Primary Dark: #003D99
- Secondary: #FF6600
- Success: #2E7D32
- Error: #D32F2F
- Warning: #F57C00
- Neutral Black: #1A1A1A
- Neutral Gray: #757575
- Neutral Light: #F5F5F5
- Neutral White: #FFFFFF

## Typography
- Heading 1: 48px, 700 weight, 120% line height
- Heading 2: 32px, 600 weight, 120% line height
- Heading 3: 24px, 600 weight, 120% line height
- Body: 16px, 400 weight, 150% line height
- Small: 14px, 400 weight, 150% line height
- Caption: 12px, 400 weight, 150% line height

## Spacing
- 4px: Micro adjustments
- 8px: Small padding
- 12px: Button padding
- 16px: Standard padding
- 24px: Section gap
- 32px: Medium section
- 40px: Large gap
- 60px: Hero section
- 80px: Page section

## Sizing
- Icon Small: 16px
- Icon Medium: 24px
- Icon Large: 32px
- Button Small: 32px height
- Button Medium: 40px height
- Button Large: 48px height

## Border Radius
- Sharp: 0px
- Subtle: 4px
- Standard: 8px
- Moderate: 12px
- Round: 16px
- Very Round: 24px

## Shadows
- Subtle: 0 2px 4px rgba(0,0,0,0.1)
- Elevation 1: 0 4px 8px rgba(0,0,0,0.12)
- Elevation 2: 0 8px 16px rgba(0,0,0,0.15)
- Elevation 3: 0 12px 24px rgba(0,0,0,0.18)
```

---

## Design System File Structure

### Recommended Setup

```
File: [Company] Design System v1.0

Pages:
├── Cover
│   [Logo, version, last updated]
├── ---
│   [Visual divider]
├── Overview
│   [System description, usage guidelines]
├── Colors
│   [All color styles visualized]
├── Typography
│   [All text styles visualized]
├── Spacing
│   [Visual spacing scale]
├── Components
│   [All master components organized]
├── Patterns
│   [Common layout patterns]
└── Changelog
   [Version history, recent updates]
```

### Keeping Systems Up to Date

**Schedule:**
- Monthly review: Are components being used?
- Quarterly update: Any new components needed?
- Annual refresh: Evaluate system effectiveness

**Documentation:**
```
# Changelog

## v1.1 (March 2026)
- Added Card/Small variant
- Updated Button/Primary color (darker shade for better contrast)
- Deprecated Button/Tertiary (use Button/Ghost instead)
- Added Modal/Confirmation component
- Updated Typography: H4 added (20px, 600 weight)

## v1.0 (January 2026)
- Initial system launch
- 30 components
- 8 color styles
- 6 typography styles
```

---

## Sharing Design Systems

### Internal Sharing (Team)

1. Create main file in team workspace
2. Give team "View" access (prevents accidental edits)
3. Create separate "Working" file for new components
4. Move tested components to main system
5. Update version number

### Publishing for Developers

1. Export component specs: Create handoff document with each component
2. Include hex codes: All colors with hex values
3. Include sizing: All measurements in px and em
4. Include font specs: Font family, size, weight, line height
5. Create visual library: Screenshot of all components

---

## Design System Best Practices

### Before Adding Components to System

Ask:
- Is this used 2+ times?
- Will this stay consistent across products?
- Is it stable (not changing weekly)?
- Does it solve a specific design problem?

### Naming Consistency

- Same naming across colors, typography, components
- If using "Primary/Secondary" for buttons, use for cards too
- If using "Large/Medium/Small" for buttons, use for all sized components

### Documentation

Every component needs:
- Clear name and description
- Visual example
- When to use it
- When NOT to use it
- States and variations
- Sizing and spacing specifications

### Maintenance Schedule

- **Weekly:** Monitor component usage
- **Monthly:** Review requests for new components
- **Quarterly:** Evaluate system effectiveness
- **Annually:** Major version refresh if needed

### Version Control

When making major changes:
- Create v2.0 (don't modify v1.0)
- Document breaking changes
- Give teams time to migrate
- Support both versions during transition

---

## Common Design System Mistakes

1. **Too many components:** 200+ components = overwhelming, hard to find what you need
   - **Fix:** Start with 30-40 core components. Add as needed.

2. **Inconsistent naming:** Components organized randomly
   - **Fix:** Establish naming convention before creating components

3. **Under-documented:** Components exist but no one knows when to use them
   - **Fix:** Add detailed descriptions to every component

4. **Never updated:** System becomes stale, outdated
   - **Fix:** Schedule monthly reviews, update quarterly

5. **Over-engineered:** Components try to solve every possible use case
   - **Fix:** Keep components simple. Create new variants instead.

6. **Not used:** Design system exists but designers don't use it
   - **Fix:** Train team, make components easy to find, demo regularly

---

## Evolution: From Single File to Shared System

### Phase 1: Personal Project (Month 1)

```
Single Figma file
├── Cover
├── Components (all masters)
├── Home page (using components)
├── About page (using components)
└── Product page (using components)
```

### Phase 2: Team Project (Month 2-3)

```
Design System file (main library, shared, view-only)
├── Components
├── Colors
├── Typography
└── Documentation

Working file (team members edit here)
├── Home page (uses system components)
├── About page (uses system components)
└── Product page (uses system components)
```

### Phase 3: Multi-Product System (Month 4+)

```
Design System file (core library)
├── Components (30-50 core)
├── Colors
├── Typography
└── Patterns

Product A file (uses system)
Product B file (uses system)
Product C file (uses system)
Marketing file (uses system)
```

All reference same design system.

---

## Tools for Design Systems

- **Figma:** Primary tool for building systems
- **Zeroheight:** Design documentation platform
- **Storybook:** Component library documentation (for developers)
- **Notion:** Design system documentation wiki
- **Figma Tokens:** Design token management
- **Chromatic:** Component testing

---

## Next Steps

Once design system is established:

1. **Train team:** Show how to use it
2. **Enforce usage:** Make it the standard
3. **Monitor:** Track component usage
4. **Evolve:** Add components as needs change
5. **Document:** Keep system documentation current
6. **Share:** Make accessible to developers
