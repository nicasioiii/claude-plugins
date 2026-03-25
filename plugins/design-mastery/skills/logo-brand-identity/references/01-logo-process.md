# Logo Process: Research, Sketching, and Vectorization

Quick-reference for the end-to-end logo workflow from research through vectorization.

---

## RESEARCH PHASE FRAMEWORK

### Creative Brief Sections [Will Patterson]

| Section | What to Capture |
|---------|----------------|
| About the client | Business description, industry, size, history |
| Brand values/mission | Core values, mission statement, personality traits |
| Target audience | Demographics, psychographics, pain points |
| Project goals | What the logo must achieve; measurable outcomes |
| Competitors | Top 5-10 competitors; visual landscape analysis |
| Deliverables | Exact outputs (logo, style guide, mockups, file formats) |
| Due date | Add 2 extra weeks to any estimate; underpromise, overdeliver |
| Budget | Agree before starting; include typeface licensing costs |

**Rule:** Write the brief FOR the client, send back for sign-off. Use their exact language.

### Competitive/Positioning Map [Will Patterson]

Plot competitors on sliding scales:
- Casual <-------> Formal
- Premium <-------> Affordable
- Modern <-------> Traditional
- Playful <-------> Serious
- Minimal <-------> Ornate

This reveals available visual territory and guides archetype selection.

### Mind Mapping Process [Will Patterson]

1. Write company name in center of page
2. Branch to primary keywords from brief (e.g., "athletics," "outdoors," "speed")
3. Branch each keyword to visual associations (e.g., Speed -> swoosh -> oblique -> italic)
4. Draw connection lines between branches that link
5. These connections become your creative rationale for presentations

**Example chain:** Rally > Athletics > Speed > Nike swoosh > Oblique/italic shows speed > Motion blur > Flag > Wind > Distorted type that looks like a flag waving

---

## IDEATION PHASE

### Max 2 Ideas Per Logo [LogoCore]

A logo should express at most 2 core ideas. More = illustration, not a logo.

**Process:**
1. List all possible ideas for the brand
2. Evaluate which are most relevant to the company
3. Select only the top 2
4. Merge them into a single visual concept

**Test:** If a viewer has half a second to see the logo, can they understand it? If not, too many ideas.

### Fast Sketching Technique [Will Patterson]

- Use dot-grid sketchbook (dots act as ruler substitute)
- Write company name at top so you don't forget it
- Give yourself 5 minutes total, ~1 minute per idea
- NO ruler, NO eraser, NO undos -- just get ideas out fast
- Fill in letter shapes by scribbling rather than leaving outlines
- After fast sketching, walk away; come back fresh for refinement

### Kit Bashing [LogoCore]

- Download free icons from Flat Icon/Noun Project to quickly test compositions
- Do NOT use downloaded icons in final logo -- only for experimentation
- Test 100 compositions quickly, then recreate the best from scratch
- Check negative stereotypes during this phase

---

## SKETCHING AND REFINEMENT

### Tracing Best Concepts [Will Patterson]

- After fast sketches, trace best ideas at larger scale with more care
- Annotate sketches with notes about what works and what doesn't
- "Make Big, Make Good": larger sketches reveal problems that small sketches hide
- Even in sketches, aim for consistent stroke widths, angles, and proportions

### Consistency Checks on Paper [Will Patterson]

- Use dot grid to maintain geometric consistency
- Look for letter-to-letter relationships: does the R share DNA with the A?
- Check that angles and proportions are deliberate, not accidental

---

## VECTORIZATION WORKFLOW

### Pen Tool Fundamentals [LogoCore]

- Use as FEW anchor points as possible
- Click-and-drag to create handles that define curves
- Click-Alt to remove outgoing handle for sharp transitions
- Prefer shape tools (rectangles, ellipses) over pen tool for geometric forms

### Breaking Logos into Pieces [LogoCore]

1. Divide logo into separate shape sections (e.g., body, head, antlers)
2. Vector each section independently
3. Use Pathfinder to merge after all pieces are complete
4. Keeps design editable and future-proof

### Offset Path Technique [LogoCore]

- Instead of vectoring both outer and inner outlines separately, vector only the innermost layer
- Apply Object > Path > Offset Path to generate outer outline
- Guarantees perfectly consistent stroke width throughout
- **Saves 50% of vectoring time**

### Logotype Tracing [Will Patterson]

1. Place sketch in Illustrator, embed it, dim image layer to 50%
2. Create separate layer for vectors above the sketch
3. Trace letter skeletons first, then build out thickness
4. Use appearance panel strokes (not expanded) to keep design editable

### Why NOT to Use Image Trace [Will Patterson] [CONTRARIAN]

- Image Trace creates messy, over-complicated paths
- Professional logotypes require clean, minimal anchor point paths
- Removes designer's control over curves and proportions
- Always hand-trace with pen tool

### Non-Linear Workflow [LogoCore] [CONTRARIAN]

- Avoid Object > Expand until absolutely necessary
- Keep strokes as strokes, effects as effects
- Only flatten/expand at the very end when exporting production files
- Keeps the file fully editable throughout the design process

---

## PRODUCTION-READY REFINEMENT

### Tangent Technique [LogoCore]

Where a circle meets a straight line:
1. Draw a radius from center to edge of circle
2. Rotate 90 degrees to find the tangent point
3. The 90-degree rotation ensures the tangent line intersects the circle at exactly one point
4. Creates flawless curve-to-flat transitions

### Repeating Geometric Ratios [LogoCore]

- Use the same circle/square proportions throughout the entire design
- If pin head is a perfect circle, derive pin body from the same circle's inscribed square rotated 45 degrees
- Creates visual consistency and demonstrates mathematical intention

### Mirror/Reflect Test [Will Patterson]

1. Duplicate logo
2. Object > Transform > Reflect vertically
3. Flip logotype backwards so brain stops reading and starts seeing shapes
4. Circle problem areas in red on separate layer
5. Catches balance issues, inconsistent connectors, weight distribution problems

### Blur Test [Will Patterson]

1. Apply Effect > Blur > Gaussian Blur at high radius
2. Reveals where weight is unevenly distributed (dark blobs = too heavy)
3. Fix by adjusting weights until blur shows even distribution
4. Can also print and annotate physically

### Boning Effect Correction [Will Patterson]

- Where straight line meets curved line, shape appears to contract inward
- Fix: add anchor points, make curve transition more gradual
- Pull curve slightly outward where it meets the straight line
- Critical for monoline logotypes and icon design

---

## ILLUSTRATOR TECHNIQUES QUICK REFERENCE

| Technique | Shortcut/Method |
|-----------|----------------|
| Paste in front | Ctrl+C, Ctrl+F |
| Recolor artwork | Edit > Edit Colors > Recolor Artwork |
| Offset path | Object > Path > Offset Path |
| Make guides | Right-click > Make Guides |
| Lock guides | View > Guides > Lock Guides |
| Dim sketch layer | Double-click layer > Dim Images to 50% |
| Embed image | Click Embed in control bar after pasting |
| Reset bounding box | Object > Transform > Reset Bounding Box |
| Corner widgets | Direct Selection > drag corner dots inward |
| Shape Builder | Shift+M (add) or Shift+M+Alt (subtract) |
| Reflect/copy | O tool > Alt+click > Vertical > Copy |
| Export for screens | File > Export > Export for Screens |
