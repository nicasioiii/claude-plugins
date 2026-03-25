---
name: Typography Systems
description: "MANDATORY TRIGGERS: font, typeface, type hierarchy, font sizing, line height, font pairing, font selection, letter spacing, tracking, kerning, typography, type scale, font weight, readability, text styles, callout design, truncation. FOR: Font selection process, sizing rules (Rule of Four), weight hierarchy, line-height values, letter-spacing/tracking, font pairing strategies, hierarchy techniques, type classification, callout systems, interactive text color, truncation patterns, text style definitions, and responsive typography. Do NOT use for color for text (use color-systems for interactive text color spectrum), layout and spacing between text blocks (use layout-spacing), Figma text styles setup (use design-systems), logo typography/logotypes (use logo-brand-identity)."
---

# Typography Systems

Design type hierarchy, select and pair fonts, and build typographic scales. Typography is the single most critical element of interface design -- it carries hierarchy, brand personality, and usability simultaneously.

## CORE PRINCIPLE: RESTRAINT CREATES CLARITY

All instructors converge on one truth: fewer type sizes, fewer fonts, and fewer weight variations produce cleaner, more professional designs. The constraint forces you to use other properties (weight, color, position) more creatively.

---

## RULE OF FOUR [MDS]

**Limit yourself to a maximum of 4 type sizes (or fewer) per screen.**

This is the single most impactful typography principle. Real-world evidence:
- Instagram home screen: only 2 type sizes
- iOS Settings: 4 sizes on main screen; sub-screens use only 2
- Twitter: only 3 type sizes for entire screen
- iOS Mail: only 3 type sizes on main screen

### Extending the Rule Without Adding Sizes

When you need more visual variety but want to stay within your size count:

| Technique | Effect | Example |
|-----------|--------|---------|
| Color change | Same size, different meaning | Black title vs. blue action link, both 17pt |
| Weight change | Same size, different hierarchy | Bold username vs. regular body text |
| Position change | Same size, different role | Left-aligned title vs. right-aligned value |
| Decoration | Action signaling without size | Underline or background color on links |
| Case change | Emphasis without size | Uppercase label adds weight at same size |

---

## THE 5 PROPERTIES FRAMEWORK [MDS]

Every text element is defined by five properties. Master these and typography becomes systematic.

### Title Properties

| Property | Values | Rules |
|----------|--------|-------|
| Size | 96-34pt (web), 34-13pt (apps) | Websites get bigger titles; headline multiples of body size (2x, 3x, 4x) [Flux] |
| Weight | Bold, Extra Bold, Black | Light weights ONLY at 60pt+; skip bold, use semi-bold [CONTRARIAN: Segall] |
| Line height | 100% +/- 10% | Never use body line-height on titles; all-caps can go as tight as 75% |
| Width | Flexible relative to body | Avoid single-word orphans on second line |
| Alignment | Left preferred | Center + left body looks odd; exception: mobile title bars |

### Body Copy Properties

| Property | Values | Rules |
|----------|--------|-------|
| Size | 16px minimum (web default) | Less text = more flexibility; more text = stick to 16-18px |
| Weight | Regular for body | Bold body needs 2-3 weight steps lighter than bold title |
| Line height | 150% baseline (130-175%) | 130% starting point [Flux]; serif fonts may need 160%+ |
| Width | 45-75 characters per line | Below 45 = too narrow; above 75 = cumbersome; sweet spot ~55-65 |
| Alignment | Left-aligned for longer text | Center only for small amounts; never justify on web [Arash] |

---

## FONT WEIGHT HIERARCHY

| Weight | CSS Value | Best Use |
|--------|-----------|---------|
| Hairline/Thin | 100 | Decorative only at 60pt+ |
| Light | 200-300 | Decorative at large sizes |
| Regular/Book | 400 | Body copy standard |
| Medium | 500 | Emphasis within body |
| Semi-bold | 600 | Headlines, nav active states |
| Bold | 700 | Headlines, primary actions |
| Extra Bold | 800 | Large display headlines |
| Black | 900 | Maximum impact display |

**Rules:**
- Bold needs 2-3 weight steps above body to appear truly bold
- Never force-bold a font without a dedicated bold weight [MDS]
- **DISAGREEMENT:** Segall says skip bold entirely, use semi-bold for more harmony. MDS/Gareis use bold as standard for titles. Resolution: Semi-bold is a refinement technique; bold is the safe default.
- Primary action = heavier weight; secondary action = lighter weight

---

## LETTER SPACING (TRACKING)

All instructors agree: tighten default letter spacing on most fonts.

| Context | Range | Notes |
|---------|-------|-------|
| Body copy | -1% to -3% | Segall: -1% to -4% on everything; Gareis: -3% to +3% |
| Headlines | -3% to -5% | Tighter for larger sizes; Gareis: -5% for compact appearance |
| All-caps sublines | up to +80% | Editorial feel; destroys paragraph readability but works for single words [Gareis] |
| Condensed fonts | Leave at default | Already have tight spacing; negative tracking causes overlap [Gareis] |
| Decorative fonts | Do NOT change | Perfectly crafted by the designer [Gareis] |

**Synthesis:** Start at -2% for body, -3% for headlines. Adjust by eye. Inter at default spacing looks amateur; at -2% it transforms into a beautiful font. [Segall]

---

## LINE HEIGHT REFERENCE

| Element | Starting Point | Range | Source Consensus |
|---------|---------------|-------|-----------------|
| Hero titles | 100% | 75-110% | All agree: tight |
| Section titles | 100% | 90-120% | Strong consensus |
| Body copy (web) | 150% | 130-175% | MDS: 150%; Flux: 130% start; Gareis: check by eye |
| Body copy (app) | Auto/150% | 120-160% | Platform defaults often work |
| All-caps titles | 75-100% | -- | Can go tighter than mixed case |
| Metadata/captions | Auto | 120-150% | Keep compact |

**Key insight [Gareis]:** 16pt font with 22pt line height can outperform 20pt font with 20pt line height. Smaller font + more line spacing is often better than larger font + tight spacing.

---

## FONT SELECTION PROCESS

### Step 1: Define the Mood [Gareis]

Never start by browsing font websites -- this wastes time and rarely leads to good results. Begin by thinking about mood, context, and purpose.

Every typeface has its own personality. If there is a mismatch between font personality and content, people feel something is wrong even if they cannot explain it.

### Step 2: Match Personality to Classification

See `references/02-font-classification-pairing.md` for the full classification guide with favorite fonts per category.

### Step 3: Verify Technical Quality [Gareis]

- Does the font have good built-in kerning pairs?
- Is character design consistent across all glyphs?
- Does it include all necessary special characters?
- How does it perform across different sizes?
- Does it have enough weight variations for your hierarchy needs? [MDS]

### Step 4: Test at Actual Sizes

Test at actual sizes on actual devices before committing. Buy the family, not just one weight. [MDS]

---

## FONT PAIRING RULES

**Consensus:** Maximum 2-3 font families for an entire project. All instructors agree.

**DISAGREEMENT:**
- [CONTRARIAN] Gareis: "There are NO rules dictating font selection for specific audiences. Be open to intentionally break away and explore new paths." Even "incompatible-looking" fonts can produce fantastic results.
- Segall/Flux: Max 2-3, be deliberate, pair serif + sans-serif for clear contrast.
- **Resolution:** Default to 2-3 with intentional contrast. Advanced designers may break this rule when the project context supports it.

### Five Pairing Strategies [Flux + Gareis]

1. **Same typeface, different weights** -- safest pair; go up 2+ weights
2. **Same typeface, different widths** -- condensed + regular from same family
3. **Two distinct typefaces (max 3)** -- must be clearly distinct, not similar-but-different
4. **Complementary features** -- similar proportions, era, mood
5. **One decorative maximum** -- headlines only; body gets standard faces

### Pairing Test

Do the fonts look like they belong in the same era/world? If one screams medieval and the other screams futuristic, they clash.

See `references/02-font-classification-pairing.md` for specific pairing examples.

---

## HIERARCHY TECHNIQUES (6 Methods) [Gareis]

1. **Size and Scale** -- larger = higher importance; dramatic differences create bold hierarchy
2. **Font Weight and Style** -- bold attracts; light de-emphasizes; italic for editorial character
3. **Contrast** -- color contrast (headline in accent color), font contrast (serif + sans = structural separation)
4. **White Space** -- elements need space to breathe; more space = more importance
5. **Text Alignment** -- left (default), center (headings/titles only), justified (editorial long-form)
6. **Indentation** -- first-line indent for paragraphs; block indent for excerpts; drop cap for editorial personality

**Creating hierarchy with only two font sizes is possible and often preferable.** [Gareis]

---

## TEXT STYLE SYSTEM [MDS]

Define a limited set of text styles for your entire project:

- **Limit total styles to ~6-8 for an entire app**
- Define each with: font family, size, weight, line-height, letter-spacing, color
- iOS example: only 3 main text sizes used throughout entire apps (18, 16, 14)

---

## ANTI-PATTERNS

- Using more than 4 type sizes per screen
- Body copy wider than 75 characters per line
- Using body line-height (150%) on title text
- Light/hairline weights at body copy sizes
- Center-aligning long-form body copy
- Force-bolding a font without a dedicated bold weight
- Default letter-spacing on fonts that need tightening
- Using more than 3 font families per project
- Making hierarchy differences too subtle (gray to slightly-darker-gray instead of gray to red)

---

## RELATED SKILLS

- **color-systems:** Interactive text color system (blue for links, red for destructive actions)
- **layout-spacing:** Spacing between text blocks, negative space as hierarchy tool
- **design-systems:** Creating Figma text styles and typography tokens
- **mood-board-brand-vibe:** Font selection after brand direction is established
- **design-critique:** Common typography mistakes from the Critique Vault
- **logo-brand-identity:** Typography for logotypes and brand marks
