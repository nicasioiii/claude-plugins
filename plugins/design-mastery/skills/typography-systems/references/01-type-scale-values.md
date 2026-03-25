---
name: Type Scale Values & Quick Reference
description: |
  When to Read: Setting up a type scale for a new project, choosing specific size/weight/line-height values, or checking body copy width rules.
  Cross-references: typography-systems SKILL.md (decision framework), 02-font-classification-pairing.md (font selection), layout-spacing (spacing between text elements).
---

# Type Scale Values & Quick Reference

## WEB TYPOGRAPHY QUICK REFERENCE [MDS + Flux + Gareis]

| Element | Size Range | Weight | Line Height | Letter Spacing |
|---------|-----------|--------|-------------|----------------|
| Hero title | 60-96px | Bold-Black (or Light at 60px+) | 75-100% | -3% to -5% |
| Section title | 34-48px | Bold-Extra Bold | 100-120% | -3% to -5% |
| Subsection title | 24-32px | Semi-bold-Bold | 100-120% | -2% to -3% |
| Body copy | 16-18px | Regular | 130-175% (start 150%) | -1% to -3% |
| Body copy (large) | 18-24px (screen) | Regular | 130-150% | -1% to -2% |
| Metadata/caption | 12-14px | Regular-Medium | 120-150% | 0% to +1% |
| All-caps label | 10-12pt | Medium-Semi-bold | 120%+ | +5% to +80% |
| Button text | 14-16px | Medium-Semi-bold | 100-120% | 0% to +1% |

## APP TYPOGRAPHY QUICK REFERENCE [MDS]

| Element | Size (pt) | Weight | Line Height | Notes |
|---------|----------|--------|-------------|-------|
| Large title (iOS) | 34pt | Bold | 100% | Messages, Settings headers |
| Standard title | 17pt | Semi-bold/Bold | 100% | Extremely common, used everywhere |
| Body | 15-17pt | Regular | Auto/150% | Instagram uses 15pt |
| Small metadata | 13pt | Regular | Auto | Supporting info |
| Tiny labels | 12pt | Regular-Medium | Auto | Story names, tab labels |

**iOS pattern:** Only 3-4 sizes needed for most apps.

## HEADLINE SIZING METHOD [Flux]

Use multiples of body size for headlines:
- Body: 16px
- Small heading: 24px (1.5x)
- Medium heading: 32px (2x)
- Large heading: 48px (3x)
- Hero heading: 64px (4x)

Then pick the nearest number on your 8-pixel grid.

**Not "a little bigger" -- dramatic contrast.** Creates geometric relationship between sizes.

## BODY COPY WIDTH RULES

| Metric | Minimum | Sweet Spot | Maximum |
|--------|---------|-----------|---------|
| Characters per line | 45 | 55-65 | 75 |
| Words per line [Flux] | 7 | 10-12 | 15 |

- Below 45 characters = too narrow, excessive eye jumps
- Above 75 characters = hard to track back to start of next line
- **Not a hard law but strongly recommended** [MDS]

## PARAGRAPH SPACING [Flux]

- Paragraph spacing = same pixel value as point size
- Tighter than double line-break
- Double-break = amateur tell

## BODY COPY EMPHASIS RULES [Flux]

- Choose ONE emphasis method: bold OR italic
- Multiple emphasis (bold + italic + underline) = design crime
- Use actual italic font, never software skew/"false italic"

---

## FONT WEIGHT HIERARCHY RULES [MDS]

| Weight Name | CSS Value | Use Case |
|-------------|-----------|----------|
| Hairline/Thin | 100 | Only at 60pt+ (e.g., weather display) |
| Light | 200-300 | Only at 34pt+; avoid for UI text |
| Regular/Book | 400 | Body copy, standard text |
| Medium | 500 | Captions, metadata emphasis |
| Semi-bold | 600 | Small headings, nav items |
| Bold | 700 | Headlines, primary actions |
| Extra Bold | 800 | Section titles, impact |
| Black | 900 | Hero titles, maximum emphasis |

### Weight Rules
- Primary action = heavier weight; secondary action = lighter weight (e.g., bold "Send" vs. regular "Cancel")
- Bold needs at least 2-3 weight steps difference from body to appear truly bold
- Never force-bold a font that does not have a dedicated bold weight -- the computer-generated version looks terrible
- Body copy should use Regular, Book, or Medium weight
- Bold body copy is acceptable only if it matches a specific brand style

### Creating Visual Weight Beyond Font Weight [MDS]
- Negative space surrounding text gives it implied weight and significance
- Background color (dark background with reversed-out text) creates more visual weight than font weight alone
- Combination: large type + bold weight + uppercase + extra line breaks + negative space = maximum emphasis
- White background with dark text has less visual weight than dark background with white text (same size)

---

## INTERACTIVE TEXT COLOR SYSTEM [MDS]

- Pick a primary color for interactive text (brand color or blue)
- Pick a secondary color for less-important interactive elements (lighter gray)
- Pick a danger/destructive color (red) for delete/dangerous actions
- Never overuse your interactive color -- if too many things are blue, the signal weakens
- Blue is the go-to color for interactive text -- universal convention
- Position-based interactivity: navigation items at the top do not need color to look clickable (learned pattern)
- Color alone should NOT be the only way to convey information/action -- combine with underline, weight, position, or icons

---

## CALLOUT SYSTEM [MDS]

### Callout Elevation Ladder (least to most prominent)
1. Style/Color -- bold, italic, or colored text
2. Lock-up elements -- combine with quotation marks, logos, avatars, borders, background colors
3. A thin 1-4px colored vertical line as left border = simple, elegant block quote indicator
4. Larger typeface + bold weight + quotation mark graphic + background color + avatar + name lock-up = maximum callout impact

## TEXT STYLE SYSTEM TEMPLATE

Define 6-8 styles for an entire project:

```
TEXT STYLE SYSTEM
─────────────────
Display:     [font] / [size]px / [weight] / [line-height]% / [tracking]
Heading 1:   [font] / [size]px / [weight] / [line-height]% / [tracking]
Heading 2:   [font] / [size]px / [weight] / [line-height]% / [tracking]
Heading 3:   [font] / [size]px / [weight] / [line-height]% / [tracking]
Body:        [font] / [size]px / [weight] / [line-height]% / [tracking]
Body Small:  [font] / [size]px / [weight] / [line-height]% / [tracking]
Caption:     [font] / [size]px / [weight] / [line-height]% / [tracking]
Label:       [font] / [size]px / [weight] / [line-height]% / [tracking]
```

## TRUNCATION PATTERNS [MDS]

### Apple Podcasts System

Elegant variable truncation:
- 3-line title: truncate with ellipsis, no description
- 2-line title: show 1 line of description (truncated)
- 1-line title: show 2 lines of description (truncated)
- All occupy the same vertical space

### Truncation Rules

- Always test with: (1) very short content, (2) maximum-length content
- Consider: truncation vs. line wrapping vs. abbreviation
- Right-align numeric values so they stay fixed when number length varies
- User-generated content (usernames, titles, descriptions) can be any length -- design must account for this
