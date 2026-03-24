# Brand Systems & Style Guides: Building Complete Identity

This reference covers how to build comprehensive brand identity systems and create professional style guides.

---

## What Is a Brand System?

**Definition:** A complete set of visual and verbal standards that ensure consistency across all brand touchpoints.

**Components:**
1. Logo and logo variations
2. Color palette with specifications
3. Typography system
4. Photography style and direction
5. Icon system (if applicable)
6. Spacing and layout standards
7. Writing style and voice
8. Usage guidelines (do's/don'ts)
9. Application examples
10. Brand governance (maintenance, updates)

**Why it matters:**
- Consistency builds brand recognition
- Team/vendor alignment (everyone knows how to apply brand)
- Faster execution (standards speed up design)
- Legal protection (clear usage rules)
- Professional appearance (controlled application)

---

## COLOR PALETTE SYSTEM

### Primary Color Selection

**Primary colors:** 1-2 colors that define brand identity

**Characteristics:**
- Most dominant color in brand
- Used in logo and primary marketing
- Should work at 100% saturation
- Must have excellent contrast for readability

**Example:** Slack uses teal-blue as primary color
- Appears in logo
- Dominates marketing materials
- Used in UI buttons and interactive elements
- Creates immediate brand recognition

**RGB vs. Hex vs. CMYK:**

| Format | Use Case | Example |
|---|---|---|
| RGB | Web, digital screens | R: 255, G: 0, B: 0 (pure red) |
| Hex | Web, CSS, design tools | #FF0000 (same red in hex) |
| CMYK | Print, commercial printing | C: 0, M: 100, Y: 100, K: 0 (red for print) |
| Pantone | Spot color printing | Pantone 185 C (standardized print red) |

**For every primary color, document:**
- RGB values (web)
- Hex values (CSS)
- CMYK values (printing)
- Pantone number (if using spot color in print)
- When to use (primary marketing, logo, CTA buttons)
- When NOT to use (secondary elements, background)

### Secondary & Accent Colors

**Secondary colors:** 1-2 colors supporting primary

- Lighter or darker version of primary, OR
- Complementary color to primary
- Less dominant than primary
- Used in secondary elements

**Accent colors:** 1-2 colors for highlights

- Status indicators (green=success, red=error)
- Interactive elements (hover states)
- Calls-to-action
- Visual emphasis

**Example palette:**
- Primary: Teal #0099FF
- Secondary: Light teal #66CCFF
- Accent 1: Orange #FF6633 (CTAs)
- Accent 2: Red #FF3333 (errors/alerts)

### Neutral Colors

**Neutrals:** Black, white, and grays for backgrounds and text

**Essential neutrals:**
- Pure white (#FFFFFF)
- Pure black (#000000) — OR slightly lighter black (#1A1A1A) if pure black feels harsh
- Light gray (#F5F5F5) — For backgrounds
- Medium gray (#999999) — For secondary text
- Dark gray (#333333) — For body text
- Off-white (#FAFAFA) — For alternating backgrounds

**Why important:**
- Text readability (contrast ratio WCAG standards)
- Background color options
- Disabled states (grayed out)
- Borders and dividers

### Color Contrast Standards (WCAG)

**WCAG contrast requirements:**

| Standard | Ratio | Use Case |
|---|---|---|
| WCAG AA | 4.5:1 | Body text, critical information |
| WCAG AAA | 7:1 | Accessibility best practice |
| Large text | 3:1 | Text 18px+ or 14px bold+ |

**How to calculate contrast ratio:**
- Use WebAIM contrast checker (webakm.org/contrastchecker)
- Enter foreground color (text) and background color
- Tool displays ratio and WCAG compliance

**Common color combinations to test:**
- Primary color text on white background
- White text on primary color background
- Secondary color text on light gray
- Accent color for buttons

**Document results:**
- Passing combinations (✓ 4.5:1 ratio)
- Failing combinations (✗ doesn't meet standards)
- Recommended uses (when to use each combination)

### Color Swatch Documentation

**Format for style guide:**

```
PRIMARY COLOR: Brand Teal
RGB: 0, 153, 255
Hex: #0099FF
CMYK: 100, 40, 0, 0
Pantone: Pantone 3005 C

USAGE:
- Primary logo color
- Main CTA buttons
- Active navigation states
- Primary brand marketing

DO NOT USE:
- Body text (insufficient contrast)
- Large background (too dominant)
- Secondary UI elements
```

---

## TYPOGRAPHY SYSTEM

### Font Selection Strategy

**Best practice:** 1-2 typefaces maximum

**Typical combination:**
1. Heading typeface (distinctive, readable at large sizes)
2. Body typeface (highly readable at small sizes)

**Why 2 fonts?**
- Heading font can be more stylized (less readable at small size)
- Body font must prioritize readability (needs to be neutral, clean)
- Together they create visual interest with consistent personality

**Example:** Slack brand
- Headings: Slack Sans (custom typeface)
- Body: Use system fonts (San Francisco, Segoe UI)

### Heading Hierarchy

**Standard 4-level hierarchy:**

| Level | Size | Weight | Use |
|---|---|---|---|
| H1 | 48px | Bold (700) | Page title, hero section |
| H2 | 32px | Bold (700) | Section headings, major groupings |
| H3 | 24px | Semi-bold (600) | Subsection headings |
| H4 | 18px | Semi-bold (600) | Card titles, smaller headings |

**Why this structure?**
- Clear visual hierarchy (largest = most important)
- Helps readers scan and understand content
- Provides structure for accessibility
- Works at responsive sizes (scale down proportionally on mobile)

**Line height for headings:**
- H1-H2: 1.2 line height (tighter, more dramatic)
- H3-H4: 1.3 line height (slightly more space)

**Letter spacing for headings:**
- Usually negative or default (headings don't need extra spacing)
- Exception: All-caps headings benefit from +5-10% letter spacing

### Body Text Standards

**Font size:** 16px minimum (web standard)
- Smaller sizes (14px) are acceptable but less accessible
- Larger sizes (18px, 20px) improve readability

**Font weight:** 400 (regular) or 300 (light)
- Avoid thin fonts (below 300) for body text
- Emphasis use semi-bold (600) for important passages, not bold (700)

**Line height:** 1.5-1.6 (critical for readability)
- 1.5 = 16px × 1.5 = 24px spacing between lines
- Tight line height (1.4) hurts readability
- Loose line height (1.8+) makes reading harder (eyes lose place)

**Line length:** 50-75 characters per line (optimal reading width)
- Too short (30 characters): Eyes work too hard, fatigue
- Too long (100+ characters): Eyes can't track across
- Web standard: 60-70 characters per line with 16px font

**Example body copy rules:**
```
BODY TEXT
Font: Inter (or similar neutral sans-serif)
Size: 16px
Weight: 400 (regular)
Line height: 1.6
Letter spacing: 0 (default)
Color: #333333 (dark gray)
Max width: 600px (to maintain line length)

EMPHASIS TEXT (still body copy, emphasized)
Size: 16px (same)
Weight: 600 (semi-bold, not 700 bold)
Color: primary color or darker gray

SMALL TEXT (captions, labels)
Size: 14px
Weight: 400
Color: #666666 (lighter gray)
Line height: 1.5
```

### Web Font Performance

**Critical:** Load fonts efficiently to avoid slow performance

**Best practices:**
1. **Limit to 2 typefaces, 2-3 weights max**
   - Default (400)
   - Bold (700)
   - Optional: Semi-bold (600) or Light (300)

2. **Use system fonts when possible**
   - System fonts (SF Pro Display, Segoe UI, -apple-system) load instantly
   - No file download required
   - Native fonts to each platform

3. **If using custom fonts, optimize**
   - Use WOFF2 format (modern, smaller file size)
   - Load only essential weights
   - Implement font-display: swap (show text while font loads)
   - Subset fonts to Latin characters (if applicable)

**Example CSS:**
```css
@font-face {
  font-family: 'Brand Sans';
  src: url('brand-sans-regular.woff2') format('woff2');
  font-weight: 400;
  font-display: swap;
}

@font-face {
  font-family: 'Brand Sans';
  src: url('brand-sans-bold.woff2') format('woff2');
  font-weight: 700;
  font-display: swap;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Brand Sans', sans-serif;
  font-size: 16px;
  line-height: 1.6;
}
```

---

## SPACING & LAYOUT STANDARDS

### 8px Grid System

**Most design systems use 8px as base unit:**

| Increment | Value | Use |
|---|---|---|
| xs | 4px | Micro spacing (rare) |
| sm | 8px | Small padding, tight spacing |
| md | 16px | Default padding, standard spacing |
| lg | 24px | Larger padding, section spacing |
| xl | 32px | Large spacing between sections |
| 2xl | 48px | Major section spacing |
| 3xl | 64px | Hero/large sections |

**Why 8px base?**
- Divisible by 2, 4, 8 (scales smoothly)
- Matches common device sizes (mobile, tablet, desktop)
- Creates visual rhythm and consistency

**Example spacing application:**

```
PADDING (inside elements)
Button padding: 8px (top/bottom) × 16px (left/right)
Card padding: 24px
Section padding: 48px (top/bottom)

MARGIN (between elements)
Paragraph margin: 16px (bottom)
Section margin: 64px (bottom)
Button group spacing: 8px between buttons

GAP (flex/grid spacing)
Card grid gap: 24px
Button row gap: 8px
Navigation item gap: 16px
```

### Responsive Breakpoints

**Standard breakpoints for responsive design:**

| Breakpoint | Min Width | Device | Grid Columns |
|---|---|---|---|
| Mobile | 320px | Small phones | 1-2 columns |
| Mobile+ | 480px | Large phones | 2-3 columns |
| Tablet | 768px | Tablets | 3-4 columns |
| Desktop | 1024px | Small desktop | 4 columns |
| Desktop+ | 1440px | Large desktop | 4-6 columns |
| Ultra | 1920px+ | Ultra-wide | 6+ columns |

**Spacing adjustments at each breakpoint:**

```
MOBILE (320px - 767px)
Section padding: 16px
Card gap: 16px
Typography: Slightly smaller (14px body)

TABLET (768px - 1023px)
Section padding: 24px
Card gap: 20px
Typography: Standard (16px body)

DESKTOP (1024px+)
Section padding: 48px
Card gap: 24px
Typography: Standard (16px body)
```

---

## PHOTOGRAPHY & IMAGERY STYLE

### Photography Direction

**Define photo style across these dimensions:**

**1. Subject Matter**
- What types of photos represent the brand? (People, products, abstract, nature?)
- Lifestyle vs. studio shots?
- Real photography vs. illustrated?

**Example:** Slack uses photos of real people in work environments, diverse, authentic

**2. Composition**
- Tight crops or wide shots?
- Centered subjects or off-center?
- Portrait or landscape orientation?
- Variety of framing or consistent approach?

**3. Lighting**
- Natural light vs. studio lighting?
- Bright and airy vs. moody and dramatic?
- Golden hour photography vs. flat overcast?
- Shadows present or minimized?

**4. Color Grading**
- Warm or cool color temperature?
- Saturated or desaturated colors?
- Consistent color grade applied?
- Specific color emphasis (more warm tones, less blue)?

**5. Diversity & Representation**
- Include diverse people (race, age, gender, ability)?
- Authentic representation or staged/stock?
- Inclusive imagery in marketing?

**Example photo style guide:**
```
PHOTOGRAPHY STYLE
- Real people in authentic work environments
- Natural lighting, golden hour preferred
- Warm color temperature, slightly saturated
- Tight to medium crops (not wide shots)
- Diverse representation required
- No stock photography (original photos only)
- Lifestyle over studio (authentic over polished)

DO NOT USE:
- Cheesy smiling stock photos
- Corporate cliches (awkward high-fives)
- Over-processed or heavily filtered images
- Exclusively white/male representations
- Staged or fake-looking scenarios
```

### Icon System Standards

**If brand uses custom icons:**

**Grid & Sizing:**
- Icon grid: 16px, 24px, 32px, 48px, 64px (multiples of 8)
- Stroke width: Consistent across all icons (e.g., 2px)
- Corner radius: Consistent (e.g., 2px rounded corners)
- Padding: Consistent internal padding within grid

**Construction:**
- All icons built on same grid
- Stroke weight consistent (no mix of thin/thick)
- Corner radius consistent
- Viewbox/padding standardized

**Example icon specifications:**
```
ICON SYSTEM
Grid size: 24px × 24px
Stroke width: 1.5px
Corner radius: 2px
Padding: 2px (internal to 24px grid)
Format: SVG (vector)
Outline style (not filled)

USAGE:
- Primary navigation: 24px
- Buttons: 16px or 24px
- Small UI: 16px
- Large UI: 32px or 48px
```

---

## STYLE GUIDE DOCUMENT STRUCTURE

### Recommended Table of Contents

**1. Introduction / Brand Story**
- 1-2 page overview
- Brand mission, values, personality
- Who the brand serves
- What makes it different

**2. Logo Guidelines**
- Logo mark (full color)
- Minimum size (typically 1" or 100px)
- Clear space (spacing around logo)
- Logo variations (icon-only, wordmark-only)
- Monochrome and reversed versions
- Do's and don'ts for logo use

**3. Color Palette**
- Primary color(s) with specs (RGB, Hex, CMYK, Pantone)
- Secondary colors with specs
- Accent colors with specs
- Neutral palette (blacks, whites, grays)
- Contrast ratios and accessibility notes
- Color combinations for specific uses

**4. Typography**
- Heading typeface and weights
- Body typeface and weights
- Size scale (H1-H4, body, small text)
- Line height and letter spacing standards
- Web font specifications and loading

**5. Imagery & Photography**
- Photography style and direction
- Approved photography sources
- Photo mood examples
- What not to use (stock cliches, etc.)

**6. Icon System**
- Icon grid and sizing
- Stroke weight and construction
- Icon library/examples
- When to use icons vs. text

**7. Spacing & Layout**
- 8px grid explanation
- Padding and margin standards
- Responsive breakpoints
- Section spacing
- Component spacing

**8. Writing Style & Voice**
- Brand voice (tone, personality)
- Vocabulary preferences
- Do's and don'ts for copy
- Examples of on-brand writing

**9. Applications & Examples**
- Business card mockup
- Website header mockup
- Email signature example
- Social media profile mockup
- App interface mockup
- Print collateral examples

**10. Do's & Don'ts**
- Logo distortions (stretching, rotating)
- Color misuse (wrong primary color)
- Typography mistakes (too many fonts)
- Spacing violations (elements too close)
- Inappropriate applications
- Common misuses with visual examples

**11. Maintenance & Governance**
- Who maintains brand standards?
- Process for brand evolution
- Approval process for new applications
- Contact for brand questions
- Version history of guide

### Style Guide Formats

**Common delivery formats:**

1. **PDF** — Static, printable, good for distribution
2. **Figma** — Interactive, easy to share, live editing
3. **Website** — Self-hosted, most flexible, best for teams
4. **Component library** — For developers (Storybook, etc.)

**Best practice:** Digital version (Figma or website) + PDF export for archival

---

## BRAND USAGE GUIDELINES

### Logo Do's & Don'ts

**DO:**
- [ ] Use provided logo files (don't recreate manually)
- [ ] Maintain clear space around logo (minimum 1/4 of logo height)
- [ ] Use brand colors consistently
- [ ] Test contrast and readability at actual size
- [ ] Use at least minimum specified size

**DON'T:**
- [ ] Stretch or distort logo (keep proportions)
- [ ] Change colors (use brand colors only)
- [ ] Add effects (shadows, gradients, outlines)
- [ ] Rotate logo unnecessarily
- [ ] Outline or border logo
- [ ] Use on backgrounds without contrast
- [ ] Combine with other logos
- [ ] Create new versions

### Typography Do's & Don'ts

**DO:**
- [ ] Use specified typefaces only (no substitutions)
- [ ] Maintain hierarchy (H1 > H2 > H3 > Body)
- [ ] Use specified sizes and weights
- [ ] Maintain adequate line height (1.5-1.6)
- [ ] Ensure text contrast meets WCAG standards

**DON'T:**
- [ ] Mix multiple typefaces
- [ ] Use unapproved fonts
- [ ] Make text too small (below 14px)
- [ ] Reduce line height below 1.3
- [ ] Justify text in long paragraphs
- [ ] Use all caps for body text
- [ ] Create custom fonts without approval
- [ ] Mix different font weights arbitrarily

### Color Do's & Don'ts

**DO:**
- [ ] Use brand color palette
- [ ] Verify contrast ratios before use
- [ ] Use color consistently across applications
- [ ] Test in monochrome (works in black & white?)

**DON'T:**
- [ ] Create new colors outside palette
- [ ] Use colors interchangeably (primary ≠ secondary)
- [ ] Place text on low-contrast backgrounds
- [ ] Use accent colors for large areas
- [ ] Rely solely on color to convey meaning (use pattern or shape too)

---

## Brand System Governance

### Approval Process

**For any new brand application:**

1. **Designer creates mockup** (website section, email template, packaging, etc.)
2. **Submit for brand review** (does it follow guidelines?)
3. **Get approval** from brand manager/lead
4. **Execute and implement**
5. **Archive** mockup for future reference

### Maintenance & Updates

**Guidelines should evolve but core should stay consistent:**

**Core elements (rarely change):**
- Logo
- Primary color
- Primary typeface
- Brand personality/voice

**Secondary elements (can evolve):**
- Secondary colors
- Icon library
- Photography direction
- Website layout

**Update frequency:**
- Review annually
- Update if brand evolves
- Maintain version history
- Notify teams of changes

### Common Questions & Approvals

**Create FAQ section:**
- Can we use a different blue? (No, use brand blue)
- Can we modify the logo? (No, use provided files)
- Can we add more fonts? (No, maximum 2 fonts)
- Can we use different photography style? (Only if brand approved)

---

## Style Guide Distribution

**Who needs the style guide?**
- All internal teams (marketing, design, product, sales)
- Agency partners and contractors
- Vendors (printers, developers, etc.)
- All stakeholders in brand execution

**Distribution methods:**
1. **Figma link** (for designers, easy to update)
2. **PDF export** (for non-designers, static reference)
3. **Website URL** (if hosting brand portal)
4. **Email archive** (backup)

**Best practice:** Centralized location, version control, easy access

---

## Example: Complete Color Palette Documentation

```
PRIMARY COLOR: Brand Blue
HEX: #0066FF
RGB: 0, 102, 255
CMYK: 100, 60, 0, 0
Pantone: Pantone 2171 C

USAGE:
Primary brand color
Logo color
CTA buttons
Active navigation states
Brand accent in headers

CONTRAST RATIOS:
#0066FF on white (#FFFFFF): 5.2:1 ✓ WCAG AAA
#0066FF on light gray (#F5F5F5): 4.8:1 ✓ WCAG AA
#FFFFFF text on #0066FF: 8.5:1 ✓ WCAG AAA

DO NOT USE:
Large background areas (too dominant)
Body text (unless verified contrast)
Small-size accent (disappears)

APPROVED COMBINATIONS:
#0066FF buttons with white text
#0066FF on white backgrounds
#0066FF in logo

AVOID:
#0066FF on dark backgrounds (insufficient contrast)
#0066FF for large text areas
Multiple uses of #0066FF (too much saturation)
```

---

## Summary: Brand System Checklist

Before finalizing style guide, verify:

- [ ] Logo guidelines (all variations documented)
- [ ] Color palette (RGB, Hex, CMYK, Pantone)
- [ ] Contrast ratios verified (WCAG standards)
- [ ] Typography system (2 fonts max, sizes, weights)
- [ ] Spacing standards (8px grid, padding, margin)
- [ ] Photography direction (mood, style, examples)
- [ ] Icon system (if applicable)
- [ ] Writing voice & tone guidelines
- [ ] Usage examples (business card, website, email, etc.)
- [ ] Do's and don'ts visual examples
- [ ] Approval process documented
- [ ] Distribution and maintenance plan

A comprehensive brand system ensures consistency, speeds up design execution, and protects brand integrity across all touchpoints.
