# Color Systems: Theory & Application

Color is both systematic (contrast ratios, color theory) and intuitive (emotional response). Master both to create cohesive, accessible, beautiful palettes.

---

## Color Selection Methods

### RGB (Red, Green, Blue)

**Format:** 0-255 per channel
- 255, 255, 255 = white
- 0, 0, 0 = black
- Not intuitive for designers (hard to visualize from numbers)

**When to use:** Pulling existing color values from screenshots or measurements

**Example:** RGB(255, 0, 0) = pure red (but what does that tell you visually?)

### Hex Codes (Hexadecimal)

**Format:** #RRGGBB
- Range: 00-FF per channel (0-255 in decimal)
- #000000 = black
- #FFFFFF = white
- #FF0000 = red

**Shorthand:**
- #000 = #000000
- #FFF = #FFFFFF
- #F00 = #FF0000

**Advantages:**
- Most portable (works everywhere—web, apps, design tools)
- Web standard
- Recommended as primary format

**How to read:**
- First two digits: Red channel
- Middle two digits: Green channel
- Last two digits: Blue channel

### HSL (Hue, Saturation, Lightness)

**Format:** H (0-360°), S (0-100%), L (0-100%)

**Components:**
- **Hue:** Position on color wheel (0-360°)
  - 0° = red, 120° = green, 240° = blue
- **Saturation:** How much color (0-100%)
  - 0% = gray (no color)
  - 100% = pure color
- **Lightness:** Brightness (0-100%)
  - 0% = black
  - 50% = pure color
  - 100% = white

**Advantages:** More intuitive than RGB

**Disadvantage:** Slight inconsistency between Sketch and Figma color pickers

### HSB (Hue, Saturation, Brightness) ⭐ **DESIGNER FAVORITE**

**Format:** H (0-360°), S (0-100%), B (0-100%)

**Components:**
- **Hue:** Position on color wheel (0-360°)
- **Saturation:** Whiteness level (0-100%)
  - 0% = white (no saturation)
  - 100% = pure color
- **Brightness:** Darkness level (0-100%)
  - 0% = black
  - 100% = pure color

**Advantages:**
- Most intuitive for designers
- Consistent across Figma, Sketch, Adobe CC
- Easiest to adjust and predict results
- Natural workflow: Pick hue → adjust saturation → adjust brightness

**Example:**
- Blue: H 240°, S 100%, B 100% = pure blue
- Lighter blue: H 240°, S 50%, B 100% = light blue
- Darker blue: H 240°, S 100%, B 50% = dark blue

### CMYK (Print Only)

**Format:** Cyan, Magenta, Yellow, Black (4-color print)

**Not relevant for screen design.** Only use if designing for print. RGB on screen ≠ CMYK printed.

---

## Color Contrast & Accessibility

### WCAG Contrast Scoring

**Scale: 1-21**

| Score | Level | Use Case |
|-------|-------|----------|
| 1.0 | FAIL | Same color (black on black) |
| 3.0 | AA Large | Large text only (18.5px bold or 24px regular) |
| 4.5 | AA | All body text, standard |
| 7.0 | AAA | Best practice, long reading, 20/80 vision |
| 21.0 | Maximum | Black on white |

### Vision Requirements

**20/20 vision (standard):**
- Can read at 3.0 contrast

**20/40 vision (1.5x sensitivity loss):**
- Requires 4.5:1 contrast
- Typical for aging population

**20/80 vision (legally blind):**
- Requires 7.0:1 contrast (AAA)
- Significant vision impairment

### Minimum Standards by Context

**Body copy (any size):**
- Minimum: 4.5:1 (AA)
- Recommended: 7.0:1 (AAA)
- Non-negotiable for accessibility

**Large text (18.5px bold or 24px regular):**
- Minimum: 3.0:1 (AA Large)
- Acceptable but not preferred

**Disabled/inactive states:**
- Can intentionally fail contrast
- Status shown through de-emphasis
- Communicates "inactive" to users

**Decorative elements, borders:**
- 3:1 ratio acceptable
- Not functional UI, so lower standard applies

### Testing Contrast

**Tools:**
- colorable.com (paste hex codes, instant feedback)
- Figma Contrast plugin (real-time checking)
- WebAIM contrast checker
- Browser extensions (WAVE, aXe)

**Workflow:**
1. Pick foreground color (text)
2. Pick background color
3. Paste hex codes into tool
4. Get score instantly
5. Adjust color if below 4.5

### Example: Gray on Black

**Common problem:** Using #666666 on black background

```
Foreground: #666666 (medium gray)
Background: #000000 (black)
Contrast ratio: 3.0 (BARELY passing, not recommended)
```

**Better options:**

```
#757575 on #000000 = 4.5 (safe standard)
#999999 on #000000 = 7.0+ (excellent)
#CCCCCC on #000000 = 16.0 (very light gray, very high contrast)
```

### Creating Accessible Color Palettes

**Process:**
1. Pick base colors you love
2. Create test matrix: All colors × All potential backgrounds
3. Check contrast for each combination
4. Mark "AA" (3:1) or "AAA" (4.5:1)
5. Adjust colors while maintaining brand essence

**Key rule:** Never rely on color alone. Pair with:
- Text labels
- Patterns/patterns
- Icons
- Size/weight differences

---

## Color System Structure

### Primary Color

**Definition:** Your brand color, most used, core interactive element

**Characteristics:**
- Commands attention
- Used for CTAs (buttons, links)
- Key interactive states
- Usually 1-2 shades for variation

**Example:** Blue for a SaaS platform, green for an eco-brand, purple for a creative brand

### Secondary Color

**Definition:** Complement to primary, less frequent, alternative actions

**Characteristics:**
- Supports primary
- Used for secondary CTAs
- Alternative states or actions
- Usually 1 shade

**Example:** Orange paired with blue, or pink paired with teal

### Neutral Colors

**Definition:** Grays for structure, text, backgrounds

**Characteristics:**
- Range from near-black to near-white
- For body text, backgrounds, dividers, borders
- Accessibility-focused (must meet contrast)

**Typically 5-7 shades:**
- #000000 / #1A1A1A (black/near-black for text)
- #333333 / #404040 (dark gray)
- #757575 (medium gray, good for secondary text)
- #999999 / #AAAAAA (light gray for hints)
- #CCCCCC / #E0E0E0 (light gray for borders)
- #F5F5F5 / #FAFAFA (near-white for backgrounds)
- #FFFFFF (white)

### Interactive Colors

**Definition:** Colors specific to states and feedback

**Variations:**
- Hover state (usually lighter/darker variant of primary)
- Active state (usually darker/more saturated)
- Disabled state (gray or very muted)
- Success (green)
- Error (red)
- Warning (orange/yellow)
- Info (blue)

---

## Color Definition Reference

### Complete Color Set Template

```
PRIMARY
  - Base: #0066CC (blue)
  - Light: #E6F2FF (for backgrounds)
  - Dark: #003D99 (for hover states)

SECONDARY
  - Base: #FF6600 (orange)
  - Light: #FFE6CC
  - Dark: #CC5200

NEUTRAL - TEXT
  - Black: #000000 or #1A1A1A
  - Dark gray: #333333
  - Medium gray: #757575
  - Light gray: #999999

NEUTRAL - BACKGROUNDS
  - Dark bg: #0F0F0F or #1A1A1A
  - White: #FFFFFF
  - Light bg: #F5F5F5

SEMANTIC
  - Success: #2E7D32 (green)
  - Error: #D32F2F (red)
  - Warning: #F57C00 (orange)
  - Info: #1976D2 (blue)

STATES
  - Hover: Darker or lighter version of primary
  - Disabled: Gray or 50% opacity
  - Focus: Primary with border or outline
```

---

## Creating Accessible Palettes

### Step 1: Pick Base Colors

Choose colors you love. Don't worry about contrast yet.

### Step 2: Create Shades & Tints

Once base palette established, create darker/lighter versions:

**Using Tailwind Color Generator:**
- Input hex color → get complementary shades
- Creates 50-900 variants
- Use for hover states, disabled states, backgrounds

**Manual creation:**
- Light: Add lightness in HSL, or add white in RGB
- Dark: Remove lightness in HSL, or add black in RGB

### Step 3: Test Contrast Matrix

Create spreadsheet: All colors × All backgrounds

```
| Color | White Bg | Gray Bg | Dark Bg | Notes |
|-------|----------|---------|---------|-------|
| #0066CC | 7.0 AAA | 5.5 AA | 2.0 FAIL | Use on white/gray only |
| #FF6600 | 5.2 AA | 3.8 FAIL | 4.1 AA | Use on white/dark |
| #333333 | 15.0 AAA | 8.0 AAA | 1.2 FAIL | Use on light only |
```

### Step 4: Create Style Library

Once tested, add to Figma:
- Color styles with meaningful names
- Document contrast ratios
- Create component library using these colors

### Step 5: Document Standards

Share with team:
- Approved color combinations
- When to use each color
- Contrast scores for each pair
- Exceptions (if any)

---

## Color Theory Quick Reference

### Complementary Colors

Colors opposite on color wheel (contrast-heavy, vibrant).
- Red + Green (often too intense)
- Blue + Orange (balanced, common in design)
- Yellow + Purple (high energy)

### Analogous Colors

Colors adjacent on color wheel (harmonious, cohesive).
- Blue + Blue-green + Green (cool, nature-like)
- Red + Red-orange + Orange (warm, energetic)

### Triadic Colors

Three colors evenly spaced on color wheel (dynamic, balanced).
- Red + Yellow + Blue (primary colors, bold)
- Orange + Green + Purple (secondary colors, sophisticated)

---

## Common Color Mistakes

1. **Inaccessible contrast:** Text hard to read
   - **Fix:** Test all combinations. Minimum 4.5:1

2. **Too many colors:** Rainbow palette looks chaotic
   - **Fix:** Limit to 3-5 main colors + neutrals

3. **Ignoring brand personality:** Colors don't reflect brand
   - **Fix:** Ensure colors evoke intended emotions

4. **Assuming color means understanding:** Colorblind users miss meaning
   - **Fix:** Use color + pattern/text/icon always

5. **Not testing print:** RGB on screen ≠ CMYK in print
   - **Fix:** Test printed proofs before production

---

## 60-30-10 Color Rule

**Distribution for visual balance:**
- **60%:** Dominant color (usually background/white)
- **30%:** Secondary color (usually content text/elements)
- **10%:** Accent color (brand color that pops)

**Note:** Guidelines to start with, not rigid rules. Break them intentionally.

### Example: SaaS Dashboard

```
60% - White/light gray backgrounds
30% - Dark gray text and UI elements
10% - Blue primary buttons and accent elements
```

### Example: Bold Brand Website

```
60% - Dark background (charcoal)
30% - Brand color (purple) for text and cards
10% - Accent color (neon pink) for CTAs
```

---

## Semantic Color Usage

**Not just aesthetic—colors communicate meaning:**

**Red = Error/Stop**
- Error messages
- Delete buttons
- Invalid inputs

**Green = Success/Go**
- Success confirmations
- Valid checkmarks
- Completion states

**Orange/Yellow = Warning**
- Deprecation notices
- Need attention
- Caution

**Blue = Info**
- Informational messages
- Help text
- Loading states

**Gray = Disabled/Inactive**
- Disabled buttons
- Archived content
- Inactive states

---

## Color Palette Documentation Template

```
# Brand Color System

## Primary
- Base: #0066CC (RGB: 0, 102, 204)
- Contrast on white: 7.0 (AAA)
- Contrast on gray: 5.5 (AA)
- Use for: Primary CTAs, key UI elements, brand identity

## Secondary
- Base: #FF6600 (RGB: 255, 102, 0)
- Contrast on white: 5.2 (AA)
- Use for: Secondary CTAs, alternative actions

## Success
- Base: #2E7D32 (RGB: 46, 125, 50)
- Contrast on white: 6.2 (AAA)
- Use for: Confirmations, success states

## Error
- Base: #D32F2F (RGB: 211, 47, 47)
- Contrast on white: 5.2 (AA)
- Use for: Errors, destructive actions

## Neutral Grays
- Black: #1A1A1A (for body text)
- Medium: #757575 (for secondary text)
- Light: #F5F5F5 (for backgrounds)
- White: #FFFFFF (for primary backgrounds)
```

---

## Tools

- **Color generation:** Coolors.co (space bar generates, lock favorites)
- **Color palettes:** Tailwind color generator, Color Hunt
- **Contrast testing:** Colorable.com, Figma plugin
- **Colorblind simulation:** WebAIM color contrast checker, Chrome extensions
- **Palette organization:** Figma color styles, design system docs
