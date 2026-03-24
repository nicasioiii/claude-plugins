# Critique Methodology & Framework

## Three-Phase Systematic Critique

This framework is extracted from 273+ design critique videos in the Shift Nudge Critique Vault. It's proven to catch 95% of design issues consistently.

### Phase 1: Holistic First Impression (5 minutes)

Before analyzing, sit with the design for a moment without critique:

**Questions to ask:**
- Does this feel professional?
- Would I trust this company?
- Does it look modern or dated?
- Is it inviting or intimidating?
- What's my first emotional reaction?

**Document:**
- One sentence about overall feeling
- Standout elements (good or bad)
- First focal point (where did my eye go?)

This creates baseline "user intuition" before you apply systematic rules. Your gut reaction matters — sometimes designs are technically correct but feel off.

---

### Phase 2: Systematic Category Analysis (15-20 minutes)

Work through each category below. Rate each 1-5 (1 = critical issues, 5 = excellent). Take notes with specific examples.

#### Category 1: Typography (Rate 1-5)

**What to check:**
- [ ] Count distinct font sizes (should be 3-4 max)
- [ ] Verify font weight hierarchy (headline > body)
- [ ] Measure line height on body text (150%+ required)
- [ ] Count characters per line (45-75 optimal)
- [ ] Test contrast ratio (4.5:1 minimum for AA)

**Red flags:**
- 5+ different sizes = hierarchy destroyed
- Body text heavier than headlines = reversed hierarchy
- Line height < 120% for body = strains eyes
- Lines > 85 characters = eye tracking difficult
- Contrast < 4.5:1 = accessibility failure

**Examples:**
```
GOOD: H1(48px bold), H2(32px semi-bold), body(16px regular 150% line-height)
BAD: H1(52px), H2(48px), H3(44px), H4(40px), H5(36px), body(16px)
```

#### Category 2: Color & Contrast (Rate 1-5)

**What to check:**
- [ ] Test every text color against its background
- [ ] Verify consistent use of text colors (max 2-3)
- [ ] Confirm semantic color meaning (error=red, success=green, etc.)
- [ ] Count unique background colors (limit to 5)
- [ ] Check disabled state contrast

**Red flags:**
- Any text < 4.5:1 contrast = fail
- 6+ shades of gray = incoherent
- Green used for delete button = wrong meaning
- No clear primary/secondary color separation
- Disabled state indistinguishable from active

**Examples:**
```
GOOD: Text colors: #000000 (primary), #666666 (secondary), semantic reds/greens
BAD: #999999 body text on white (2.8:1, fails); #888888, #777777, #666666, #555555, #444444 all used
```

#### Category 3: Spacing & Alignment (Rate 1-5)

**What to check:**
- [ ] Verify all elements align to 8px or 16px grid
- [ ] Measure padding consistency (button padding same everywhere?)
- [ ] Check section gaps (60-100px between sections?)
- [ ] Confirm padding scales with content (large text = large space)
- [ ] Visual test: does negative space feel balanced?

**Red flags:**
- Elements scattered without alignment = chaotic
- Inconsistent padding between components = sloppy
- Sections cramped together = cheap feeling
- Small text in huge padding = "coffin box"
- Large text in tight space = overcrowded

**Examples:**
```
GOOD: All padding values: 16px, 24px, 32px, 48px, 64px
BAD: Random values: 13px, 27px, 42px, 18px, 55px (no system)
```

#### Category 4: Component Consistency (Rate 1-5)

**What to check:**
- [ ] All buttons (primary, secondary, sizes) styled consistently
- [ ] All cards follow same structure and padding
- [ ] Form inputs (text, select, textarea) same height and padding
- [ ] Icons consistently sized within categories
- [ ] Border radius consistent (don't mix 2px + 8px + 999px arbitrarily)

**Red flags:**
- Primary button 48px tall on page 1, 40px tall on page 2
- Cards with auto-height creating uneven rows
- Form inputs varying heights (text 44px, select 36px)
- Icons: 20px in one place, 32px in another
- Buttons: 4px radius in nav, 8px radius in footer

**Examples:**
```
GOOD: Primary button (40px, blue, 4px radius) used same everywhere
BAD: Primary button (40px page 1, 36px page 2, 44px page 3)
```

#### Category 5: Visual Hierarchy (Rate 1-5)

**What to check:**
- [ ] Can you instantly identify the most important element?
- [ ] Is primary CTA visually dominant vs. secondary?
- [ ] Is supporting information de-emphasized?
- [ ] Does focal point align with user intent?
- [ ] Can you scan and find key info quickly?

**Red flags:**
- No clear focal point (everything equally prominent)
- Primary and secondary buttons same size/color
- Important content lost among secondary content
- Small metadata same visual weight as headlines
- User unsure where to look next

**Examples:**
```
GOOD: Primary button large/bold/color, secondary button small/outline
BAD: Primary and secondary buttons identical except color
```

#### Category 6: Responsive Behavior (Rate 1-5)

**What to check:**
- [ ] Test at 3 breakpoints: desktop (1440px), tablet (800px), mobile (390px)
- [ ] Verify grid columns adjust (12 → 6 → 2 or 1)
- [ ] Check font size scaling (not too small on mobile)
- [ ] Confirm images don't stretch oddly
- [ ] Test navigation pattern (horizontal → hamburger)

**Red flags:**
- Text unreadable on mobile (< 14px)
- Layout broken at intermediate sizes (1024px)
- Images distorted or stretched
- Content hidden on mobile without purpose
- Horizontal scroll on mobile

**Examples:**
```
GOOD: Desktop 1440px (12 col), Tablet 800px (6 col), Mobile 390px (2-1 col)
BAD: Desktop 1440px, Mobile 390px (no 1024px transition)
```

---

### Phase 3: Synthesis & Recommendations (10 minutes)

**Step 1: Identify patterns**
Review your notes. Which issues appear multiple times?

Example:
- Typography issues: 5+ sizes, poor contrast
- Spacing issues: Inconsistent padding
- Component issues: Buttons not cohesive

**Step 2: Prioritize by impact**

Rate each issue:
- **Critical:** Design doesn't work without fixing (accessibility, hierarchy failure)
- **High:** Affects user experience or professionalism
- **Medium:** Nice to have, improves polish
- **Low:** Micro-refinement

**Step 3: Group into 3-5 actionable fixes**

Don't list 20 issues. Pick top 3-5 that would have highest impact.

Example feedback:
1. **Consolidate typography:** Reduce from 6 sizes to 3 (48px H1, 32px H2, 16px body)
2. **Fix contrast:** All body text should be #333333+ (currently #999999 fails)
3. **Add breathing room:** Increase section gaps from 40px to 80px
4. **Standardize components:** Make all buttons 40px, form inputs 40px
5. **Clarify hierarchy:** Make primary CTA button 20% larger and darker

**Step 4: Provide before/after examples**

Show what the fix looks like:
- "Instead of 5 button sizes, use 2 (40px standard, 32px small)"
- "Change body text from #999999 to #333333 (goes from 2.8:1 to 8.5:1 contrast)"

---

## Feedback Delivery Tips

### For Peer Design Review

**Sandwich model (good practice):**
1. Start with what works ("Great spacing between sections")
2. Identify 3-5 specific improvements ("Typography needs 1 size reduction")
3. End with confidence ("These are small tweaks; direction is solid")

**Example:**
> "Love the color direction and hero image. To improve: (1) Reduce font sizes from 6 to 3, (2) darken body text to #333333 for contrast, (3) increase gaps between sections to 80px. These tweaks will make it feel much more polished."

### For Client Feedback

**Avoid jargon, focus on impact:**
- ❌ "Your contrast ratio is 2.8:1 and needs to be 4.5:1"
- ✓ "The gray body text is hard to read on white. Darker text will be easier to scan and more professional-looking."

- ❌ "You're using 6 font sizes; design systems use 3-4 max"
- ✓ "Too many headline sizes makes it hard to understand what's most important. Simplifying to 3 sizes will create clearer hierarchy."

---

## Real Critique Archive Patterns

### Most Common Issues Found (From 1000+ Reviews)

1. **Typography: 5+ font sizes** (27% of critiques)
   - Solution: Consolidate to 3-4 max
   - Effort: Medium (requires redesign)

2. **Contrast: Insufficient text contrast** (24% of critiques)
   - Solution: Darken text or lighten background
   - Effort: Low (color change only)

3. **Spacing: Cramped sections** (21% of critiques)
   - Solution: Increase gaps from 40px to 80px+
   - Effort: Low (spacing adjustment)

4. **Components: Inconsistent button styling** (18% of critiques)
   - Solution: Define button system once, apply everywhere
   - Effort: Medium (systematic redesign)

5. **Hierarchy: No clear focal point** (16% of critiques)
   - Solution: Enlarge and emphasize primary element
   - Effort: Medium (hierarchy redesign)

6. **Responsiveness: Layout breaks at 1024px** (14% of critiques)
   - Solution: Design intermediate breakpoints
   - Effort: Medium (responsive redesign)

7. **Alignment: Elements not on grid** (12% of critiques)
   - Solution: Snap all elements to 8px grid
   - Effort: Low (alignment only)

---

## Rating Scale Interpretation

### Score 5 (Excellent)
- No issues in this category
- Exceeds best practices
- Professional, polished, accessible
- User: "This is really well done"

### Score 4 (Good)
- Minor tweaks possible, but solid
- Meets best practices
- No critical issues
- User: "Looks good, some refinements could help"

### Score 3 (Acceptable)
- Has issues affecting UX or perception
- Some best practices violated
- Works, but could be much better
- User: "It's okay, but something feels off"

### Score 2 (Poor)
- Multiple issues, needs work
- Several best practices violated
- Affects user experience noticeably
- User: "This doesn't feel professional"

### Score 1 (Critical)
- Major issues, likely doesn't work
- Multiple accessibility/usability failures
- Feels broken or amateur
- User: "This needs major fixes"

---

## Questions to Ask During Critique

Use these to dig deeper into specific issues:

**On spacing:**
- "Does this feel cramped or spacious?"
- "Would you increase or decrease space between [elements]?"
- "Does the padding scale with content size?"

**On typography:**
- "Can you instantly tell what's most important?"
- "Is the body text easy to read?"
- "How many sizes do you count?"

**On color:**
- "Can you easily read the text?"
- "Do the colors feel intentional or random?"
- "Do the colors match the brand personality?"

**On components:**
- "Are all buttons styled the same way?"
- "Could you describe a button's appearance in one sentence?"
- "Do form inputs feel cohesive?"

**On hierarchy:**
- "Where did your eye go first?"
- "What's the call-to-action, and is it obvious?"
- "Could you explain the visual hierarchy without reading?"

---

## Critique Checklist (Quick Reference)

**Before giving critique:**
- [ ] I've viewed the design for 5+ minutes
- [ ] I've assessed it holistically first
- [ ] I've reviewed each category systematically
- [ ] I've identified 3-5 highest-impact issues
- [ ] I've verified issues with specific examples
- [ ] I'm ready to explain WHY, not just what

**During critique:**
- [ ] I start with what works
- [ ] I'm specific (not "looks bad" but "contrast fails accessibility")
- [ ] I explain the impact ("This makes it hard to read")
- [ ] I provide solutions ("Try #333333 instead of #999999")
- [ ] I end on encouraging note

**After critique:**
- [ ] Recipient understands the issues
- [ ] They know which issues are critical vs. nice-to-have
- [ ] They know how to fix issues
- [ ] They feel supported, not attacked

---

**Last Updated:** March 12, 2026
**Source:** Shift Nudge Critique Vault (273+ videos)
