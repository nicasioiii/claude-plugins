# Logo Production: Scale Testing, Color, and Delivery

Production-ready refinement, color systems, and quality verification for logo delivery.

---

## SCALE TESTING PROTOCOL [LogoCore]

### Required Test Sizes

| Context | Size | What to Check |
|---------|------|---------------|
| Favicon | 64x64px | Readability, detail visibility |
| App icon | 120x120px | Square composition, fill ratio |
| Website header | ~45px tall | Legibility alongside navigation |
| Business card | 85x53mm | Print proportions, clear space |
| Social profile | 400x400px | Square crop, recognition |
| Billboard/mural | Very large | Detail quality, line weight proportions |

**Process:** Use Illustrator Symbols panel -- create dynamic symbol so changing the master updates all instances across artboards.

### Acute Angle Rule [LogoCore]

Tight corners and thin intersection points vanish at small sizes.

**Fix:**
- Eliminate acute angles by widening elements
- Add breathing room between anchor points
- Move overlapping elements further apart so flat edges form at intersections

### Favicon Considerations [LogoCore]

- If full logo doesn't fit a square, create a simplified version
- Logo should fill available favicon space -- too much empty space = invisible at 64px
- Consider stacked/square composition from the start if logo will primarily appear on iOS icons

---

## COMPOSITION RULES

### Vacuum-Tight Composition [LogoCore]

1. Draw a geometric shape (rectangle/circle) around the logo
2. Measure wasted space
3. Target: less than 25% wasted space = pass
4. Over 25%: rearrange elements to minimize gaps
5. Move text closer, scale symbols up, realign stacking

### Silhouette/Container Thinking [LogoCore]

- Every logo should fit cleanly into a simple geometric shape (its "silhouette")
- The silhouette defines how the logo occupies space on business cards, favicons, social media
- Logos with irregular silhouettes waste space and scale poorly

---

## COLOR SYSTEM FOR LOGOS

### Three Rules for Logo Color [LogoCore]

1. **Use bare minimum colors.** Remove gradients, drop shadows, redundant tones unless they serve explicit purpose
2. **Apply bright/contrast colors only to the MOST IMPORTANT element.** Mute backgrounds so focal element pops
3. **Logo must work on white, black, AND mid-gray backgrounds**

### Color Versatility Requirements

Every logo must have these variations:
- Full color on white background
- Full color on black background
- Full color on mid-gray background
- Single color (monochrome) version
- Reversed (white on dark) version
- Icon-only version (if combination logo)
- Wordmark-only version (if combination logo)

### RGB vs CMYK Decision Framework [LogoCore]

| Scenario | Color Space | Notes |
|----------|-------------|-------|
| Web-only design | RGB (sRGB) | Almost everything digital is sRGB |
| Even slight chance of printing | CMYK | Colors shift when converting; design in CMYK from start |
| Both web and print | Create multiple variations | RGB with gradients for web; CMYK outline for print |

**sRGB:** Safest for web; almost everything digital is built around it.
**Adobe RGB:** Wider gamut but fewer monitors support it; conversions can look inaccurate.
**CMYK profiles:** Vary by printer/ink/paper/region. Always ask print house which profile they want.

### Pantone Spot Colors [LogoCore]

- Pantone = specific ink formulas, not simulated like CMYK/RGB
- Provides reliable, consistent color across different printers and materials
- Essential for brand color fidelity when exact reproduction matters
- Include Pantone values in style guide alongside HEX, RGB, CMYK

### Color Psychology Reference [Will Patterson]

| Color | Psychology | Example Brands |
|-------|-----------|----------------|
| Red | Strength, passion, excitement | Coca-Cola, Target, Virgin |
| Orange | Creativity, bravery, success | -- |
| Yellow | Happy, cheerful, creative | -- |
| Green | Nature, fresh, eco-friendly | Recycling icons |
| Blue | Trust, loyalty, competence | Banks, hedge funds |
| Pink | Compassion, sincerity | -- |
| Purple | Royalty, luxury | -- |
| Brown | Dependable, rugged | Farming companies |
| Black | Sophistication, formal | Apple |
| White | Perfection, honesty | Apple |

**Color-industry stereotypes [LogoCore]:**
- Red on white = medical/hospital (Western culture)
- White on red = Swiss products/travel
- Same colors reversed trigger completely different industry associations

### Color Extraction from Mood Board [Will Patterson]

1. Screenshot mood board
2. Bring into Illustrator
3. Eyedropper colors from real imagery to build palette
4. Use Coolors extension to generate harmonious schemes around a locked base color

**Rule:** Design in black and white first. Add color as the last layer.

---

## CONSISTENCY CHECKS

### Angle Consistency [LogoCore]

- If one element uses 10-degree slant, ALL slants must match
- Plot gridlines on both horizontal and vertical axes to verify
- Use Illustrator guides (right-click > Make Guides) for precision

### Stroke Width Consistency [LogoCore]

- All similar elements share identical stroke widths
- Use offset paths to generate consistent outlines from single paths
- Fluctuating widths look inconsistent

### Color Count [LogoCore]

- Limit to 2-3 colors maximum for production logos
- Use Edit > Edit Colors > Recolor Artwork to test and limit
- Natural to accumulate 5+ colors during design; reduce for production

---

## LOGO CHECKLIST (Pre-Delivery)

### Visual Quality
- [ ] Works at 16px (favicon), 32px, 64px, 256px, and large print
- [ ] Readable in monochrome (black on white, white on black)
- [ ] Distinctive from top 5 competitors
- [ ] Conveys brand personality in form, not decoration
- [ ] Memorable after seeing once or twice
- [ ] Timeless (won't look dated in 5 years)

### Technical Quality
- [ ] Vector format (scalable without distortion)
- [ ] Minimal anchor points (clean paths)
- [ ] Consistent stroke widths throughout
- [ ] Consistent angles throughout
- [ ] Vacuum-tight composition (less than 25% wasted space)
- [ ] Clear space defined around mark

### Variations
- [ ] Full color version
- [ ] Single color (monochrome) version
- [ ] Reversed (white on dark) version
- [ ] Icon-only version (if combination logo)
- [ ] Wordmark-only version (if combination logo)
- [ ] Works on white, black, and mid-gray backgrounds

### Stereotype Check [LogoCore]
- [ ] Industry association testing passed
- [ ] No negative visual associations identified
- [ ] Positive stereotype alignment verified

---

## INDUSTRY STEREOTYPE REFERENCE [LogoCore]

### Common Visual Associations by Industry

| Industry | Common Stereotypes | Avoid If Wrong Industry |
|----------|-------------------|----------------------|
| Medical/Health | Red cross, heart, caduceus | Red on white = hospital association |
| Travel | Globe, airplane, compass | Swiss cross + briefcase = medical, not travel |
| Tech | Circuit patterns, angular shapes, blue | Blue circle = too generic |
| Food/Restaurant | Fork/knife, chef hat, leaf | Green leaf = eco, not always food |
| Finance | Shield, column, graph lines | Green = sustainability confusion |
| Education | Book, graduation cap, owl | Apple = tech, not education |
| Legal | Scales, gavel, shield | Shield can also mean security/military |
| Real Estate | House, key, skyline | Generic house outline = undistinguished |
| Fitness | Human figure, dumbbell, heart | Heart can be medical |
| Nature/Eco | Leaf, tree, water drop | Green leaf overused across all "green" industries |

### Stereotype Testing Process [LogoCore]

1. Design the logo without checking stereotypes first (avoid subconscious copying)
2. After design: Google/Pinterest search industry terms
3. Check Flat Icon for basic icon representation of industry keywords
4. Verify logo is NOT confused with wrong industry
5. If wrong associations found, pivot specific elements while preserving concept
6. Goal: 100% correct industry association

### Color-Industry Associations to Watch [LogoCore]

- Red on white = medical/hospital (Western culture)
- White on red = Swiss products/travel
- Blue + shield = financial/security
- Green + leaf = environmental/organic
- Purple + crown = luxury/royalty
- Orange + flame = energy/creativity
- Same colors reversed trigger completely different associations
