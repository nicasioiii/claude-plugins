# Sketching & Vectorization Methodology

## Sketching Methodology

### The Sketching Mindset

Sketching is about **quantity, not quality**. Goal: 50-100 sketch variations in 2-3 weeks.

**Rules:**
- Sketch by hand (pen/pencil, not digital)
- No erasing (mistakes stay, you move forward)
- Don't judge while sketching (evaluate later)
- Fill pages fast (4-8 logos per page)
- Iterate on themes that feel promising

**Why hand-sketch first?** Because sketching is fast and forces clarity. You can explore 50 directions in the time digital takes to explore 5.

### Sketch Categories to Explore

**For wordmark-based logos:**
1. Letterform modifications (extend letters, overlap, negative space)
2. Hand-lettering variations (script, geometric, organic)
3. Letter combinations (ligatures, monograms, interlocking)
4. Decorative elements (flourishes, accents, supporting marks)

**For icon-based logos:**
1. Literal representations (object shape directly)
2. Abstract simplifications (distill to essence)
3. Geometric constructions (circles, triangles, grids)
4. Negative space concepts (clever use of white space)

**For combination logos:**
- Icon + wordmark in various arrangements (side-by-side, stacked, integrated)

### Hand-Lettering Fundamentals

If creating a custom wordmark:

**Baseline & Cap Height:**
- Keep consistent x-height across all letters
- Align baselines (don't let letters float)
- Match cap height unless intentionally varied

**Letterform Relationships:**
- Similar letters (O, C, G) should relate proportionally
- Weight consistency (all strokes same thickness unless modulating intentionally)
- Spacing: "optical spacing" not mechanical (letters should look equally spaced even if not)

**Common hand-lettering mistakes:**
- Inconsistent stroke weight
- Letters that don't feel related
- Poor spacing (uneven gaps between letters)
- Over-decorated (too many flourishes)
- Not actually readable at small sizes

## Vectorization Process

### Step 1: Prepare Your Sketch

- Scan sketch at high resolution (600 DPI minimum)
- Clean up image (increase contrast, remove noise)
- Place sketch in new Illustrator document as locked template layer
- Set opacity to 50% so you can see what you're drawing over it

### Step 2: Trace the Outline

**Using Illustrator Pen tool:**
1. Create new layer above template
2. Use pen tool to trace main shape
3. Click to create anchor points at corners and curves
4. For curves: click and drag to create control handles
5. Close the path (last point connects to first)

**Alternative:** Use Image Trace feature (Object > Image Trace) for quick auto-tracing, then hand-refine

### Step 3: Refine the Curve

**Bezier curves fundamentals:**
- Each curve has 4 control points: 2 end points + 2 handles
- Handle length = curve amplitude
- Handle angle = curve direction

**Refinement moves:**
- Simplify path (Object > Path > Simplify) to reduce anchor points
- Delete unnecessary points (fewer = cleaner)
- Adjust handle angles to make curves smooth
- Check for sharp points that should be smooth (and vice versa)

### Step 4: Finalize Details

- Stroke vs. fill: Decide if outline or solid shape
- Remove stroke, use fill (cleaner for logos)
- Unify all fills to single color while refining
- Test at small sizes: Scale down to 16px, 32px, 64px and check readability

### Step 5: Create Variations

Once base logo is finalized:
1. **Icon-only version** (remove wordmark, if applicable)
2. **Wordmark-only version** (remove icon, if applicable)
3. **Monochrome version** (black version on white)
4. **Reversed version** (white on black)
5. **Color version** (final color)
6. **Grayscale version** (all black/gray/white)

Test each at multiple sizes to ensure versatility.
