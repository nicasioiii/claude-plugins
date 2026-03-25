# Critique Methodology: Systematic Audit Process

Complete systematic audit process, design workflow checklist, and QA methodology synthesized from Shift Nudge, Flux Academy, and Webflow Masterclass.

---

## SYSTEMATIC AUDIT FRAMEWORK

### Phase 1: Holistic Assessment (5 minutes)

Look at the entire design without analyzing specifics. Record gut reactions:

| Question | What You're Testing |
|----------|-------------------|
| Does it feel professional? | Overall polish and attention to detail |
| Does it feel trustworthy? | Credibility signals, color choices, quality |
| Is navigation obvious? | Information architecture, findability |
| Is there a clear entry point? | Visual hierarchy, focal point |
| Does it feel cramped or spacious? | Spacing, breathing room, density |

**Take notes on gut reaction before diving into details.** First impressions mirror what real users experience.

### Phase 2: Systematic Category Review (15-20 minutes)

Work through each category, rating 1-5:

**1 = Major issues** (multiple failures, fundamental problems)
**2 = Significant issues** (several clear problems)
**3 = Adequate** (functional but clear improvements possible)
**4 = Good** (minor refinements needed)
**5 = Excellent** (professional quality, no obvious issues)

| Category | Weight | What to Check |
|----------|--------|---------------|
| Typography | 25% | Sizes, weights, line heights, contrast, character width |
| Color & Contrast | 20% | Palette, contrast ratios, consistency, semantics |
| Layout & Spacing | 25% | Alignment, grid, section spacing, breathing room |
| Component Consistency | 15% | Buttons, cards, forms, icons, states |
| Visual Hierarchy | 15% | Focal point, CTA prominence, scanning path |

### Phase 3: Synthesis & Recommendations (10 minutes)

1. Identify top 3-5 highest-impact fixes
2. Map each to specific problems found in systematic review
3. Prioritize: high-impact quick fixes first, then high-impact bigger changes
4. Recommend which skill to reference for the fix

---

## TYPOGRAPHY AUDIT CHECKLIST

### Size System

- [ ] Count unique font sizes on screen (target: 3-4 max) [MDS Rule of Four]
- [ ] H1 is clearly dominant (at least 2x body size)
- [ ] Clear distinction between each heading level (not just 4-6px difference)
- [ ] Body text 16-18px on web; never below 14px
- [ ] Metadata/captions clearly subordinate (12-14px range)

### Weight System

- [ ] Headlines use heavier weight than body
- [ ] Weight contrast is dramatic (go up at least 2 weights) [Flux]
- [ ] Not everything is bold (over-emphasis = no emphasis) [MDS Critique Vault]
- [ ] Light weights only used at large sizes (60px+)
- [ ] Interactive elements signaled through weight changes

### Readability

- [ ] Body line height 150%+ (sweet spot: 150-160%)
- [ ] Title line height 100-120%
- [ ] Body text 45-75 characters per line (sweet spot: 55-65)
- [ ] Left-aligned body text (never justify on web) [Flux]
- [ ] Paragraph spacing = point size value (not double line breaks)
- [ ] Single emphasis method per instance (bold OR italic, not both) [Flux]

### Contrast (Text)

- [ ] Body text passes 4.5:1 minimum (AA)
- [ ] Preferred: body text at 7.0:1 (AAA)
- [ ] Large text (18.5px+ bold): 3.0:1 minimum
- [ ] Test tool: colorable.com or Figma contrast plugin

---

## COLOR AUDIT CHECKLIST

### Palette System

- [ ] Primary, secondary, accent colors defined
- [ ] 60-30-10 rule applied (60% dominant, 30% secondary, 10% accent)
- [ ] Maximum 2-3 neutral grays: light (backgrounds), medium (borders), dark (text)
- [ ] Brand color used appropriately (not as small body text if bright)

### Contrast

- [ ] All text/background combinations tested
- [ ] Interactive elements meet contrast requirements
- [ ] Disabled states: either 4.5:1 (if communicating) or obviously grayed
- [ ] No color-only information (add icons, text, or patterns for colorblind users)

### Semantic Meaning

- [ ] Error states: red
- [ ] Success states: green
- [ ] Warning states: orange/yellow
- [ ] Info states: blue
- [ ] Semantic colors consistent throughout the product

---

## LAYOUT & SPACING AUDIT CHECKLIST

### Grid & Alignment

- [ ] All elements aligned to consistent grid (8px or 4pt)
- [ ] Container width is clean multiple (1440px, 1200px, 960px)
- [ ] No elements offset by odd pixel values (3px, 7px)
- [ ] Content consistently centered within containers

### Spacing

- [ ] Consistent spacing scale used (8, 16, 24, 32, 48, 64, 80, 100)
- [ ] Major section gaps: 60-100px minimum
- [ ] Related elements: 4-8px apart
- [ ] Component internal padding: 12-20px, consistent per component type
- [ ] Padding scales with content size (large text = large surrounding space)

### Hierarchy Through Space

- [ ] Most important content has most surrounding space
- [ ] Primary CTA has generous breathing room
- [ ] Secondary content nested closer together
- [ ] White space used as luxury signal (more = higher-end feel) [Flux]

---

## COMPONENT CONSISTENCY AUDIT CHECKLIST

### Buttons

- [ ] All primary buttons: same height, padding, border-radius, color
- [ ] All secondary buttons: consistent differentiation from primary
- [ ] Defined sizes: small (32px), medium (40px), large (48px)
- [ ] Hover, active, disabled states defined

### Cards

- [ ] Same internal structure throughout (image > title > description > CTA)
- [ ] Consistent padding, border-radius, shadow
- [ ] Fixed or min/max heights to prevent layout jank
- [ ] Truncation strategy for variable content (max-lines)

### Form Inputs

- [ ] All inputs: same height (40-44px recommended)
- [ ] Same padding, border style, border-radius
- [ ] Labels present and consistently positioned
- [ ] Error, focus, disabled states defined

### Icons

- [ ] Consistent sizing throughout (one or two sizes)
- [ ] Same style (outline, filled, or duotone -- not mixed)
- [ ] Consistent stroke weight across icon set

---

## QA PROCESS (PRE-HANDOFF)

### Desktop QA [Webflow Masterclass + Flux]

1. Scroll entire page at normal speed -- does the sequence work?
2. Check every link and interactive element
3. Verify all text content (no lorem ipsum remaining)
4. Test at 1440px, 1280px, and 1024px widths
5. Check print preview if relevant

### Responsive QA

1. Test at major breakpoints: 1440, 1024, 768, 375
2. Check that no content is cut off or overflowing
3. Verify touch targets are 44x44px minimum on mobile
4. Test hamburger menu interaction
5. Verify images resize/crop appropriately

### Cross-Device Check [MDS]

- Always check on actual device (phone in hand), not just on monitor
- Zoom to 100% to check readability after designing zoomed out
- Screen brightness matters: test at low brightness for contrast issues

---

## AUDIT OUTPUT TEMPLATE

### Overall Score

| Grade | Range | Meaning |
|-------|-------|---------|
| A | 90-100 | Strong design, minor refinements only |
| B | 80-89 | Good design, clear improvement areas |
| C | 70-79 | Acceptable, needs attention in multiple areas |
| D | Below 70 | Significant issues to address |

### Issue Priority Format

**Critical (must fix):**
- Issue description
- Why it matters (impact on user/business)
- Specific fix recommendation

**Important (should fix):**
- Issue description
- Why it matters
- Fix recommendation

**Nice-to-have (could improve):**
- Suggestion
- Benefit
- Implementation approach

### Roadmap

1. High-impact, quick fixes (do first)
2. High-impact, bigger changes (schedule)
3. Medium-impact improvements (next sprint)
4. Polish and refinement (ongoing)
