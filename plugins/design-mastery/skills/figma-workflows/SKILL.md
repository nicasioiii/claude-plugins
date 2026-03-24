---
name: Figma Workflows
description: "Figma file organization, components, design systems, prototyping, tokens, best practices. MANDATORY TRIGGERS: Figma organization, file structure, components, design system, Figma setup, file naming, auto layout, design tokens, color styles, typography styles, prototyping, handoff. Do NOT use for — use visual-foundations for design principles, ui-components for specific component patterns."
---

# Figma Workflows

Figma file organization seems simple until you have 100+ pages and 500+ components. Structure your file correctly from day one—it saves hours later.

---

## File Organization Philosophy

**Goal:** Create structure that supports your thinking, not rigid constraints.

**Principle:** Start messy, then organize. Organization should serve your creative process, not throttle it.

---

## Template File Structure

Use this as your starting structure. Adapt based on project size.

### Page Hierarchy (Sequential Order)

1. **Cover Page** (First impression)
   - Create a project cover
   - Fill in later if needed (not blocking)
   - Signals the start of organized work
   - Helps during stakeholder reviews (one screenshot)

2. **Divider** (Visual separator)
   - Empty page with dashes or visual break
   - Separates cover from working content
   - Helps navigate large files

3. **References** (Inspiration & Input)
   - Dump everything here: competitor screenshots, previous projects, inspirations, UI audits
   - Messy is better—reflects thinking
   - Use vector files from past projects OR screenshots
   - Goal: All inspiration in one searchable place (no hunting through browser tabs)

4. **Explorations** (Play Area)
   - Take references and duplicate/modify
   - Experiment freely, no organization pressure
   - This is where ideas come to life
   - Safe space for bad iterations

5. **Research** (Time-stamped documentation)
   - Date-stamped: "Research - March 2nd"
   - Screenshots of design decisions
   - Shows what you wanted to present to users
   - Can remove non-essential information here

6. **Presentations** (Client-ready)
   - Date-stamped: "Presentation - March 3rd"
   - Screenshots locked in time
   - Shows specific focus areas, interactions
   - Place at bottom so people see actual work first (before messy explorations)

7. **Milestones** (Production deliverables)
   - Use divider to separate from working pages
   - M0, M1, M2, M3 (milestone numbering)
   - Use checkmarks (✓) to indicate final versions
   - Label clearly: "M0 - Rating Complete ✓" or "M1 - Search - In Progress"
   - Engineers/PMs know exactly where to look
   - Final work is distinct from iterations

---

## Page Organization Rules

**Drafts first:** Create new files in Drafts folder. Prevents cluttering project folder with unnamed work.

**Name early:** If you know project name, rename immediately.

**Emojis sparingly:** Use sparingly for labeling (✓ = done). Excessive emojis = distraction.

**Blocks for grouping:** Use visual divider blocks to organize milestone work together.

**Clear hierarchy:** Final work (milestones) must be instantly recognizable vs. explorations.

---

## Component Naming Convention

Establish naming convention before creating components. Use **BEM-inspired naming** (Block-Element-Modifier).

### Naming Pattern

```
ComponentName/Variant/State
```

**Examples:**

```
Button/Primary/Default
Button/Primary/Hover
Button/Primary/Active
Button/Primary/Disabled
Button/Secondary/Default
Button/Secondary/Hover

Card/Feature/Default
Card/Feature/Hover
Card/Testimonial/Default

Input/Text/Default
Input/Text/Focus
Input/Text/Error

Navigation/Desktop/Default
Navigation/Mobile/Open
Navigation/Mobile/Closed
```

### Naming Rules

1. **Block name:** Component type (Button, Card, Input, Modal)
2. **Variant:** Visual difference (Primary, Secondary, Large, Small, Dark)
3. **State:** Interactive state (Default, Hover, Active, Disabled, Loading, Error)

**Path visualization in Figma:**
```
Components/
├── Button/
│   ├── Primary/Default
│   ├── Primary/Hover
│   ├── Primary/Active
│   ├── Primary/Disabled
│   ├── Secondary/Default
│   └── Secondary/Hover
├── Card/
│   ├── Feature/Default
│   ├── Feature/Hover
│   └── Testimonial/Default
└── Input/
    ├── Text/Default
    ├── Text/Focus
    └── Text/Error
```

---

## When to Create Components

**Create components when:**
- Element is used 2+ times (or will be)
- Element needs to stay in sync across file
- Element has multiple states (hover, active, disabled)
- Element is part of design system

**Don't create components for:**
- One-off elements (used once, never repeated)
- Experimental work (still exploring)
- Content that changes frequently (copy, images)

---

## Component Best Practices

### Master Component Setup

1. Create one main "master" component with all variations
2. Child instances inherit all changes automatically
3. Update master = update all instances instantly
4. Use component variants (newer Figma feature) instead of separate master components

### Resizing Rules

**Auto Layout:** Enable for responsive component behavior
- Direction: Vertical or horizontal
- Spacing: Standard (8, 12, 16px)
- Padding: Consistent padding inside component
- Resizing: Set to "hug" or "fill" container

**Constraints:** For non-auto-layout
- Horizontal: Left, center, right, scale
- Vertical: Top, middle, bottom, scale

### Component Documentation

**Add notes:**
- When to use this component
- What states it has
- What doesn't go in this component
- Related components

Use Figma component description field for this.

---

## Design Tokens Setup

Tokens = reusable values (colors, typography, spacing) that sync across entire design.

### Color Tokens

Create "styles" for all brand colors:

```
Colors/
├── Primary/Base
├── Primary/Light
├── Primary/Dark
├── Secondary/Base
├── Error
├── Success
├── Warning
├── Neutral/Black
├── Neutral/Dark
├── Neutral/Medium
├── Neutral/Light
└── Neutral/White
```

**Benefit:** Change primary color = updates everywhere instantly.

### Typography Tokens

Create styles for all text treatments:

```
Typography/
├── H1
├── H2
├── H3
├── Body
├── Small
├── Button
├── Caption
└── Overline
```

**Each style includes:** Font family, size, weight, line height, letter spacing.

### Spacing Tokens

Document spacing scale in design:

```
Spacing (8px base)
├── 4px
├── 8px
├── 12px
├── 16px
├── 24px
├── 32px
├── 40px
├── 60px
└── 80px
```

**Document in:** Design system documentation or Figma text layer (screenshot for reference).

---

## Auto Layout Workflow

Use Auto Layout heavily for responsive design and consistency.

### Auto Layout Setup

1. **Select element or frame**
2. **Enable Auto Layout** (Cmd+A or Shift+A on Mac)
3. **Set direction:** Vertical or horizontal
4. **Set spacing:** Between elements (8, 12, 16px)
5. **Set padding:** Inside the frame (match component padding)
6. **Set resizing rules:** Hug content, fill container, or fixed

### Benefits

- Components resize responsively when content changes
- Spacing stays consistent
- Adding/removing elements maintains alignment
- Easy to duplicate and modify variations

### Common Auto Layout Patterns

**Button:**
- Horizontal auto layout
- Icon (optional) + Text
- Padding: 12px vertical, 16px horizontal
- Gap: 8px between icon and text

**Card:**
- Vertical auto layout
- Image (optional, fixed height)
- Content section (vertical auto layout)
- Gap: 16px between sections

**Navigation:**
- Horizontal auto layout
- Logo + Menu items + CTA
- Gap: 32px between groups
- Padding: 16px vertical, 24px horizontal

---

## Prototyping Basics

Use Figma's prototyping for key flows before handoff.

### Prototype Setup

1. **Create interactions:** Click element → action
2. **Common actions:**
   - Navigate to frame
   - Change component variant
   - Show/hide overlay
   - Open/close overlay

3. **Test prototype:** Click preview button (play icon)
4. **Share prototype:** Share link with stakeholders

### When to Prototype

- **High complexity projects:** Must prototype key flows
- **New interaction patterns:** Test before building
- **Stakeholder feedback:** Show flow, not static screens

### Don't Over-Prototype

- Prototype key flows only (3-5 max)
- Don't prototype every micro-interaction
- Real interactions will differ when built
- Goal: Validate the experience, not build the product

---

## File Organization Checklist

Before considering your file "done":

- [ ] **Cover page created** (signals organized work)
- [ ] **Pages organized sequentially** (Cover → Divider → References → Explorations → Research → Presentations → Milestones)
- [ ] **Components named consistently** (BEM-style naming)
- [ ] **Color styles created** (all brand colors documented)
- [ ] **Typography styles created** (all text treatments documented)
- [ ] **Spacing documented** (safe values visible somewhere)
- [ ] **Auto layout used** (responsive components)
- [ ] **Milestone pages marked** (M0, M1, M2, checkmarks for final)
- [ ] **Research page dated** (time-stamped insights)
- [ ] **Presentations dated** (time-stamped deliverables)
- [ ] **Explorations separate from finals** (clear distinction)
- [ ] **Naming conventions followed** (consistent across file)

---

## Handoff Preparation

When ready to hand off to developers:

1. **Export all assets:** SVGs, PNGs with correct dimensions
2. **Document spacing:** Create spec document or use Figma measurement tools
3. **Create dev handoff frame:** Screenshot with annotations (or use Figma specs panel)
4. **List colors:** All colors with hex codes
5. **List typography:** All font sizes, weights, line heights
6. **Annotate interactions:** Where animations/interactions occur
7. **Share access:** Give developers view-only Figma access
8. **Version control:** Commit design file to version control if possible

---

## When to Use References

Load these reference files when:

- **01-file-organization.md** — Setting up new Figma file, planning page structure
- **02-components-setup.md** — Creating master components, setting up variants, naming conventions
- **03-design-systems.md** — Creating design systems, typography styles, color styles, managing fonts and palettes

---

## Common Figma Mistakes

1. **No organization:** Everything on one page or random pages
   - **Fix:** Use template structure above

2. **Inconsistent component naming:** "Button 1," "CTA," "Primary Button"
   - **Fix:** Establish naming convention before creating components

3. **Master components too complex:** One master with 20 variants
   - **Fix:** Use component variants feature or split into simpler masters

4. **No resizing rules:** Components break on content change
   - **Fix:** Enable auto layout or set constraints

5. **Hidden explorations:** Final work mixed with messy iterations
   - **Fix:** Separate explorations into dedicated page

6. **No documentation:** Developers can't figure out states or variations
   - **Fix:** Add component descriptions, create spec doc

---

## After File Organization: Next Steps

1. **Visual Foundations** — Understand design principles to apply in Figma
2. **UI Components** — Design specific component patterns
3. **Web Layout** — Assemble components into pages
4. **Animation/Interactions** — Add motion to your designs

---

## Cross-References

- **visual-foundations** — Design principles for creating effective components
- **discovery-direction** — Determines what you're designing (informs file structure)
- **ui-components** — Specific component patterns to build in Figma
- **web-layout** — How to structure pages in Figma
