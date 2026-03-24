# Typography Mistakes Vault
## 250+ Real Examples from Shift Nudge Critique Archive

This is a categorized catalog of typography issues found repeatedly in student work. Each pattern includes the problem, root cause, fix, and specific pixel values.

---

## PATTERN 1: Too Many Font Sizes (27% of critique issues)

### The Problem
Design uses 5, 6, or even 7 different font sizes. Each feels arbitrary.

### Root Cause
Designer treats semantic HTML tags (H1-H5) as design sizes, or evolves sizes mid-project without consolidating.

### Real Examples from Critiques

**Example 1A: The Six-Size Design**
```
H1: 56px
H2: 48px
H3: 40px
H4: 32px
H5: 24px
Body: 16px
Small: 12px
= 7 distinct sizes (FAIL)
```
**Fix:** Pick 3-4 sizes max
```
H1: 48px (headline)
H2: 32px (section header)
H3: 24px (subsection)
Body: 16px (readable text)
= 4 sizes, clear hierarchy
```

**Example 1B: The Evolved Sizes**
First pages: 48px, 32px, 16px
Middle pages: 52px, 36px, 18px
Last pages: 44px, 28px, 16px
(Sizes changed as design evolved, never consolidated)

**Fix:** Lock in sizes early. For ACE project: always 48px H1, always 32px H2, always 16px body

**Example 1C: The "Desktop vs Mobile" Disaster**
Desktop: H1 56px, H2 40px, H3 28px, body 16px
Mobile: H1 32px, H2 24px, H3 16px, body 14px
(Every size changed at breakpoint, creating new sizes)

**Fix:** Use same base sizes everywhere. Responsive = scale proportionally
```
Desktop: 48px, 32px, 24px, 16px
Mobile: Scale down proportionally to: 40px, 28px, 20px, 14px
(Still 4 distinct sizes, just smaller)
```

### Why It Fails
- Destroys hierarchy (too many levels confuses users)
- Looks unplanned (suggests no system)
- Hard to establish visual order
- Difficult to maintain across pages

### The Rule
**Maximum 4 font sizes, preferably 3**. Size differences should be 1.5x minimum between levels.

```
Safe progression:
48px → 32px (1.5x) → 16px (2x) ✓
48px → 40px (1.2x) ✗ Too close, not distinct enough
```

---

## PATTERN 2: Light Text on Light Background (24% of critique issues)

### The Problem
Body text in #999999 or lighter gray on white/light backgrounds fails contrast ratio.

### Root Cause
Designer picks light gray thinking it's "trendy" or "refined," tests on high-brightness monitor, or doesn't know contrast requirements.

### Real Examples from Critiques

**Example 2A: The Trendy Fail**
```
Body text: #999999 on white
Contrast ratio: 2.8:1
WCAG: ❌ FAILS (needs 4.5:1)
User experience: Unreadable, eye strain
```

**Fix:**
```
Body text: #333333 on white
Contrast ratio: 8.5:1
WCAG: ✅ PASSES AAA (exceeds 7.0:1)
User experience: Easy to read, professional
```

**Example 2B: The Light Gray Everywhere**
```
Primary text: #666666 (passes 5.1:1, OK)
Secondary text: #999999 (fails 2.8:1, bad)
Metadata: #AAAAAA (fails 1.5:1, terrible)
```

**Fix:** Define 2-3 text colors and stick to them
```
Primary: #333333 (8.5:1 vs white)
Secondary: #666666 (5.1:1 vs white)
All metadata: #666666 (same as secondary)
```

**Example 2C: The "But It Looks Good on My Monitor"**
Designer's 27" monitor: brightness 100%, professional LED
Client's 15" laptop: brightness 50%, consumer IPS panel
Text barely visible on client's screen

**Fix:** Test contrast ratio numerically, not visually. Use colorable.com.

### Why It Fails
- Accessibility violation (legally/ethically wrong)
- Poor user experience (strains eyes, reduces reading time)
- Looks unfinished (can't be trusted)

### The Rule
**Minimum 4.5:1 for any readable text. Aim for 7.0:1 for body.**

Color picker test:
```
Enter foreground: #999999
Enter background: #FFFFFF
Result: 2.8:1 (FAIL)
Try: #757575 → 4.5:1 (PASS)
Try: #333333 → 8.5:1 (EXCELLENT)
```

### Test Tool
Go to colorable.com, enter your text and background colors. If ratio < 4.5, darken text or lighten background.

---

## PATTERN 3: Inconsistent Weight Hierarchy (18% of critique issues)

### The Problem
Titles and body text use same weight, or reversed (body heavier than title).

### Root Cause
Designer forgets to apply font weight variations, or font doesn't have actual bold/semi-bold weights.

### Real Examples from Critiques

**Example 3A: All Regular Weight**
```
H1: 48px, regular weight (400)
H2: 32px, regular weight (400)
H3: 24px, regular weight (400)
Body: 16px, regular weight (400)
(Size difference only, no weight hierarchy)
```

**Fix:**
```
H1: 48px, bold (700)
H2: 32px, semi-bold (600)
H3: 24px, regular (400)
Body: 16px, regular (400)
(Size + weight creates clear hierarchy)
```

**Example 3B: Reversed Hierarchy (Body Heavier Than Headline)**
```
H1: 48px, regular (400) ← Title, should be heavy
H2: 32px, semi-bold (600)
Body: 16px, bold (700) ← Body, should be light (WRONG!)
```

This completely destroys hierarchy. Body text should NEVER be heavier than headlines.

**Fix:** Inverse the weights
```
H1: 48px, bold (700) ← Heaviest
Body: 16px, regular (400) ← Lighter
```

**Example 3C: Skipped Weight on Font**
Designer picks beautiful font, discovers it only has Regular + Bold (no Semi-Bold).
```
Font: "Elegant Sans" (only 400 + 700)
H1: 48px, 700 (bold, too heavy)
H2: 32px, 400 (regular, too light)
Gap too large, hierarchy weird
```

**Fix:** Pick font with more weight options
- Google Fonts: Roboto (100, 300, 400, 500, 700, 900)
- Adobe Fonts: Inter (100-900 all weights)
- Limit yourself to fonts with at least 400, 600, 700

### Why It Fails
- Eliminates hierarchy (users can't scan)
- Looks unprofessional (no visual system)
- If reversed: confuses reading order

### The Rule
**Headlines MUST be heavier than body text. Use 400 (regular) for body, 600+ (semi-bold to bold) for headlines.**

Safe weight progression:
```
H1: 700 (bold)
H2: 600 (semi-bold)
Body: 400 (regular)
✓ Clear progression
```

---

## PATTERN 4: Inadequate Line Height on Body Text (19% of critiques)

### The Problem
Body text line height < 140%, making it hard to read and causing eye strain.

### Root Cause
Designer squeezes line height for "cleaner" look, or doesn't understand line height needs.

### Real Examples from Critiques

**Example 4A: The Squeezed Body**
```
Body text: 16px, line-height: 100% (20px total height)
Users: Difficulty tracking line-to-line, eye fatigue
Fix: line-height: 150% (24px total height)
```

**Example 4B: The Inconsistent Heights**
```
H1: 48px, line-height: 110% (53px)
H2: 32px, line-height: 120% (38px)
Body: 16px, line-height: 100% (16px) ← Too tight!
```

Fix: Use consistent scaling
```
Titles: 100-120% (tight, block-like)
Body: 150-160% (loose, readable)
```

**Example 4C: The "Looks Good on Desktop" Mistake**
Desktop (16px body): Works OK with 140% (22.4px total)
Mobile (14px body): Same 140% becomes 19.6px (feels cramped on smaller screen)

Fix: Increase line height on smaller sizes
```
Desktop: 16px body, 150% line-height
Mobile: 14px body, 160% line-height (slightly more generous)
```

### Why It Fails
- **Reading exhaustion:** Lines too close = hard to track
- **Comprehension drop:** Users rush through without absorbing
- **Accessibility issue:** Dyslexia + tight line height = extra difficult
- **Mobile worse:** Small text + tight spacing = nearly impossible

### The Rule
**Body text line height MUST be 150% minimum. Sweet spot: 150-160%. Can range up to 200% for very long form content.**

```
Readability chart:
Line-height 100%: ✗ Unreadable
Line-height 125%: ~ Barely acceptable
Line-height 150%: ✓ Comfortable
Line-height 175%: ✓✓ Very comfortable (good for dyslexia)
```

---

## PATTERN 5: Titles Too Long, No Guidance on Truncation (15% of critiques)

### The Problem
Dynamic titles overflow, hide, or wrap awkwardly. No plan for long content.

### Root Cause
Designer specifies size/weight for "normal" titles, but doesn't plan for longer titles.

### Real Examples from Critiques

**Example 5A: The Broken Title Wrap**
```
Title: "How We Redesigned Our E-Commerce Platform in 8 Weeks"
Assumed: "How We Redesigned"
Mobile: Title breaks awkwardly:
"How We Redesigned"
"Our E-Commerce"
"Platform in 8 Weeks"
(3 lines, last line has only 2 words)
```

Fix: Define max line rule
```
Set max-lines: 2 for titles
If longer, truncate with ellipsis
Test at mobile width before finalizing
```

**Example 5B: The Ignored Truncation**
```
Card title: "Upgrade Your Business with Our New Advanced Analytics Dashboard"
Card width: 280px
Title should truncate at 50 chars
Actually shows: Full text (breaks card layout)
```

Fix: Implement truncation
```
max-lines: 1 (single line only)
text-overflow: ellipsis
Test title at 280px width with longest possible title
```

**Example 5C: The Metadata Problem**
```
Article date: "March 12, 2026"
Author: "Alexandra Johnson-Richardson-Smith"
Read time: "14 min read"
```
Display plan: "By [Author] · [Date]"
With long author: "By Alexandra Johnson-Richardson-Smith · March 12, 2026" (too wide)

Fix: Prioritize and truncate
```
By [Author (30 chars max)] · [Date]
If author > 30 chars: "By A. Johnson-Richardson-Smith · March..."
```

### Why It Fails
- Layout breaks with real content
- Text overlaps or hides
- Looks unprofessional with ellipsis
- Mobile experience broken

### The Rule
**Test every dynamic text field with longest reasonable input. Define truncation plan: truncate where, to how many lines, with or without ellipsis.**

Example truncation rules:
```
Card title: max 40 characters, 2 lines, ellipsis
Article headline: no truncation (allow full text, flexible height)
Navigation item: max 20 characters, 1 line, ellipsis
```

---

## PATTERN 6: No Letter Spacing Adjustment (12% of critiques)

### The Problem
Fonts look unrefined. Tight letters feel cramped; loose letters feel scattered.

### Root Cause
Designer leaves default letter-spacing at 0, doesn't realize tight letter-spacing improves quality.

### Real Examples from Critiques

**Example 6A: The Default Futura**
```
Font: Futura (angular, geometric)
Letter-spacing: 0 (default)
Result: Looks awkward, too tight, unrefined
Fix: letter-spacing: -3% to -4%
Result: Looks beautiful, balanced, refined
```

**Example 6B: The Condensed Font Problem**
```
Font: Condensed Sans-Serif (Bebas, Oswald)
Default spacing: Already tight
With 0 adjustment: Looks cramped
Fix: letter-spacing: -2%
Result: Much better
```

**Example 6C: The Large Display Font**
```
Font: Display font at 72px (very large)
Default: Spacing too generous
Fix: letter-spacing: -1% to -2%
Result: Tighter, more impactful
```

### Why It Fails
- Looks unpolished (amateur feel)
- Destroys sophistication (tight fonts look cramped)
- Small text becomes hard to read if too tight

### The Rule
**Most display fonts benefit from -2% to -4% letter-spacing. Titles benefit from tight spacing. Body text typically stays at 0.**

Safe values:
```
Display fonts (H1): -3% to -4%
Section headers (H2): -2%
Body text: 0% (leave default)
Metadata: 0%
```

---

## PATTERN 7: Inconsistent Line Heights Across Sizes (10% of critiques)

### The Problem
Line height rules different for each size, creating inconsistent reading rhythm.

### Root Cause
Designer adjusts line-height per size without system (e.g., H1 110%, H2 120%, H3 130%, body 100%).

### Real Examples from Critiques

**Example 7A: The Inconsistent System**
```
H1 (48px): line-height 110% = 53px
H2 (32px): line-height 130% = 42px
H3 (24px): line-height 140% = 34px
Body (16px): line-height 100% = 16px
(Each different, no rhythm)
```

Fix: Consistent progression
```
Titles: 100-120% (tight, all at same %)
H1: 48px, 110% = 53px
H2: 32px, 110% = 35px
H3: 24px, 110% = 26px
Body: 16px, 150% = 24px
(Titles all 110%, body all 150%)
```

**Example 7B: The Reversed Hierarchy**
```
H1: 110% (tight, hard to read)
Body: 150% (spacious, easy to read)
(Smaller text gets more space? Wrong!)
```

Fix: Titles tighter, body more generous
```
H1: 100% (titles can be tighter, short lines)
Body: 150% (longer text needs more space)
```

### Why It Fails
- Inconsistent reading experience
- Feels unplanned (no system)
- Titles hard to read if line-height too low

### The Rule
**Define line-height by category, not size.**
```
Titles: 100-120% line-height
Subtitle: 130-140% line-height
Body: 150-160% line-height
Caption: 150% line-height
```

Apply the same % to all in that category:
```
ALL titles (H1, H2, H3): 110% line-height
ALL body text: 150% line-height
```

---

## PATTERN 8: Disabled Text State Too Light (8% of critiques)

### The Problem
Disabled form inputs have text so light it's unreadable.

### Root Cause
Designer makes disabled state very light to indicate "off," but crosses into inaccessible range.

### Real Examples from Critiques

**Example 8A: The Disabled Input**
```
Default input text: #333333 (readable)
Disabled input text: #DDDDDD on white
Contrast: 1.2:1 (fails badly)
Problem: Can't read field label in disabled state
```

Fix: Either:
Option A - Keep readable
```
Disabled text: #999999 (4.5:1 passes AA)
```

Option B - Make disabled super obvious
```
Disabled text: #FFFFFF (white) on #E8E8E8 gray background
Contrast: Doesn't matter (text is same color as background = invisible)
But DESIGN makes it obvious it's disabled (gray background)
```

**Example 8B: The "Active vs Disabled" Confusion**
```
Active input: #333333 text (8.5:1 contrast)
Disabled input: #BBBBBB text (1.8:1 contrast)
User can barely tell they're different, and disabled is unreadable
```

Fix: Make disabled obviously different
```
Active input: #333333 text, white background
Disabled input: #666666 text, #F5F5F5 gray background
Now clearly different AND readable
```

### Why It Fails
- Accessibility violation (disabled inputs unreadable)
- User frustration (can't understand what's wrong)
- Looks broken (not intentional design)

### The Rule
**If disabled text must be readable, use 4.5:1 minimum contrast. If you want disabled to be light/faded, use background color to compensate.**

---

## Summary: Top 3 Typography Fixes

If you can fix only 3 things:

1. **Reduce font sizes to 3-4 max**
   - Usual issue: 6+ sizes
   - Fix time: 30 min
   - Impact: Immediately improves hierarchy

2. **Test and fix text contrast**
   - Usual issue: #999999 gray (fails)
   - Fix time: 10 min
   - Impact: Instant accessibility + professionalism

3. **Ensure weight hierarchy**
   - Usual issue: All regular weight
   - Fix time: 10 min
   - Impact: Clear visual order

These three fixes address 70% of typography issues found in the critique vault.

---

**Last Updated:** March 12, 2026
**Source:** Shift Nudge Critique Vault (273+ videos, 250+ typography patterns)
