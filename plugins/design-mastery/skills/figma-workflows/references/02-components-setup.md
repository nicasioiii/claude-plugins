# Figma Components: Master Setup & Variants

Components are the backbone of design systems. Set them up right and your entire design stays in sync automatically.

---

## Component Fundamentals

### What is a Component?

**Master component:** The main version (source of truth)

**Instance:** A copy that inherits changes from master
- Change master = all instances update automatically
- Modify instance = override just that copy
- Swap instance = replace with different component

**Benefits:**
- Consistency across entire design
- Change once, update everywhere
- Scalable to teams
- Time-saving

---

## When to Create Components

### Create Components When:

1. **Element is reused 2+ times** (or will be)
2. **Element needs to stay in sync** across entire file
3. **Element has multiple states** (hover, active, disabled)
4. **Element is part of design system** (should be documented)

### Don't Create Components For:

1. **One-off elements** (used once, never repeated)
2. **Experimental work** (still exploring, too unstable)
3. **Content that changes constantly** (copy, images that vary)
4. **Temporary frames** (reference screenshots, exploration sketches)

### Decision Tree

```
Is this element used 2+ times (or will it be)?
├─ NO → Don't create component
└─ YES → Will it stay the same across uses?
    ├─ NO → Don't create component
    └─ YES → Does it have states (hover, active, disabled)?
        ├─ NO → Create simple component
        └─ YES → Create component with variants
```

---

## Component Naming Convention

Use **BEM-inspired naming** (Block-Element-Modifier).

### Pattern

```
BlockName/Variant/State
```

### Real Examples

**Button components:**
```
Button/Primary/Default
Button/Primary/Hover
Button/Primary/Active
Button/Primary/Disabled
Button/Secondary/Default
Button/Secondary/Hover
Button/Tertiary/Default
Button/Icon/Default
```

**Card components:**
```
Card/Feature/Default
Card/Feature/Hover
Card/Testimonial/Default
Card/ProductImage/Default
Card/ProductImage/Hover
```

**Form components:**
```
Input/Text/Default
Input/Text/Focus
Input/Text/Error
Input/Text/Disabled
Input/Select/Default
Input/Select/Open
Input/Checkbox/Checked
Input/Checkbox/Unchecked
```

**Navigation:**
```
Navigation/Desktop/Default
Navigation/Mobile/Closed
Navigation/Mobile/Open
MenuDropdown/Default
MenuDropdown/Open
```

### Naming Rules

1. **Block:** Component type (Button, Card, Input, Modal)
   - Capitalized
   - Singular noun

2. **Variant:** Visual difference (Primary, Secondary, Large, Small, Desktop, Mobile)
   - Describes how it looks different
   - Use consistent variant names across components
   - Example: If using "Primary/Secondary" for buttons, use same for cards

3. **State:** Interactive state (Default, Hover, Active, Focus, Disabled, Loading, Error)
   - Describes interaction
   - Consistent across all components

### Figma Naming Path Result

When you name components as `Button/Primary/Default`:

```
Components panel shows:
├── Button
│   ├── Primary
│   │   ├── Default
│   │   ├── Hover
│   │   └── Disabled
│   └── Secondary
│       ├── Default
│       └── Hover
```

Creates clean hierarchy in Figma.

---

## Master Component Structure

### Simple Master Component (No Variants)

For simple components (used once with minor tweaks):

1. Create frame with your component
2. Right-click → "Create component"
3. Name it following convention
4. Done

**Use this for:** Simple icons, simple cards, simple sections

### Complex Master Component (With Variants)

For components with multiple states/variants:

1. Create frame with your component
2. Add all variants in the same frame (arrange vertically/horizontally)
3. Select all variant frames
4. Right-click → "Create component set"
5. Figma auto-organizes

**Better approach:** Use Figma's native "Component variants" feature (not separate masters).

---

## Using Component Variants (Modern Figma)

Newer Figma allows variants within a single master. Much better than old separate-master approach.

### Setting Up Variants

1. Create master component
2. In right panel, "Component" section
3. Add variant group: "State"
   - Add options: Default, Hover, Active, Disabled
4. For each state, design the variation

**Result:** One master component with 4 variants, all linked.

**Benefit:** Swap between variants by changing a single property. Much cleaner than multiple masters.

### Variant Example: Button

**Master component:**
```
Button (master)
├── Variant: Type
│   ├── Primary
│   └── Secondary
├── Variant: State
│   ├── Default
│   ├── Hover
│   ├── Active
│   └── Disabled
└── Variant: Size
    ├── Small
    ├── Medium
    └── Large
```

When you use this component:
- Change "Type" → Primary to Secondary instantly
- Change "State" → Default to Hover instantly
- Change "Size" → Small to Large instantly

One component, infinite combinations.

---

## Component Properties & Resizing

### Auto Layout (Recommended)

1. **Select component frame**
2. **Enable Auto Layout** (⌘A on Mac, Shift+A on Windows)
3. **Set direction:** Vertical or horizontal
4. **Set gap:** Spacing between elements (8, 12, 16px)
5. **Set padding:** Inside the frame (match component padding)
6. **Set resizing:** "Hug content," "Fill container," or fixed

**Benefits:**
- Content changes = component resizes automatically
- Spacing stays consistent
- Adding/removing elements maintains alignment
- Responsive behavior built-in

### Constraints (Legacy, less preferred)

Use if auto layout doesn't fit your use case:

1. **Select element inside component**
2. **Set horizontal constraint:** Left, center, right, scale
3. **Set vertical constraint:** Top, middle, bottom, scale

**Example:** Logo inside navigation
- Horizontal: Left (stick to left side)
- Vertical: Middle (stay centered vertically)

---

## Component Structure Best Practices

### Break Into Logical Pieces

Don't create one massive component. Break it down:

**❌ Bad: One button component with everything**
```
Button (icon + text + badge + tooltip)
```

**✓ Good: Modular components**
```
Button/Icon (just icon)
Button/Text (just text)
Button/Primary (icon + text, no badge)
Badge (standalone)
Tooltip (standalone)
```

Use composition: Button can contain Badge when needed.

### Nested Components

Use nested components for complex structures:

**Example: Card component**
```
Card (master)
├── uses CardImage (nested)
├── uses CardContent (nested)
│   ├── uses CardTitle (nested)
│   └── uses CardDescription (nested)
└── uses Button (nested, for CTA)
```

**Benefit:** Change Button everywhere = updates in Cards too. Single source of truth.

### Main Component Organization

Place main components in dedicated section of your file:

```
File structure:
├── Pages
│   ├── Home
│   ├── Products
│   └── etc.
└── Design System (hidden page, visible only to designers)
    ├── Components
    │   ├── Button
    │   ├── Card
    │   ├── Input
    │   └── Modal
    ├── Colors
    └── Typography
```

**Why separate page:** Developers don't see this page. They see final designs using components.

---

## Overriding Component Instances

When using a component, you can override specific properties:

### Swappable Properties

- **Text:** Change text in instances while master controls style
- **Images:** Replace image in instance
- **Nested components:** Swap Button inside Card for different button
- **Visibility:** Hide/show layers in instance
- **Overrides:** Customization without breaking component link

### When to Override

**Allow overrides for:**
- Text (headline, description)
- Images (different photos per instance)
- Nested components (different button type)

**Lock overrides for:**
- Spacing (maintain consistency)
- Colors (brand consistency)
- Size (component size shouldn't vary)

### Example: Card Component

Master card:
```
Card (master)
├── Image (override allowed)
├── Title (override allowed)
├── Description (override allowed)
├── Button (swap allowed)
└── Spacing/styling (locked)
```

Using the component, you can:
- ✓ Change image per card
- ✓ Change title text per card
- ✓ Change button type per card
- ✗ Can't change padding (locked)
- ✗ Can't change colors (locked)

---

## Component Library Organization

### Organizing Components in Figma

Recommended structure:

```
Components Page:
├── Foundation
│   ├── Icon (icon-base, small, medium, large)
│   ├── Badge (default, success, error)
│   └── Divider
├── Buttons
│   ├── Button/Primary
│   ├── Button/Secondary
│   ├── Button/Icon
│   └── Button/Ghost
├── Cards
│   ├── Card/Feature
│   ├── Card/Testimonial
│   ├── Card/Product
│   └── Card/Small
├── Forms
│   ├── Input/Text
│   ├── Input/Select
│   ├── Input/Checkbox
│   └── Input/Radio
├── Navigation
│   ├── Navigation/Desktop
│   ├── Navigation/Mobile
│   └── MenuDropdown
└── Modals
    ├── Modal/Confirmation
    ├── Modal/Alert
    └── Modal/Form
```

**Naming in Figma's components panel:**
```
Components/
├── Foundation/
│   ├── Icon/Small
│   ├── Icon/Medium
│   ├── Icon/Large
├── Buttons/
│   ├── Button/Primary
│   ├── Button/Secondary
├── Cards/
│   ├── Card/Feature
│   ├── Card/Testimonial
└── etc...
```

---

## Documentation & Component Notes

### Add Component Descriptions

1. Right-click component
2. "Edit component"
3. In right panel, add description

**Include:**
- When to use this component
- What states it has
- What shouldn't go in it
- Related components
- Usage rules

**Example for Button/Primary:**
```
Primary action button for forms and CTAs.

Use when: User should click here (primary action)
States: Default, Hover, Active, Disabled, Loading
Don't use for: Secondary actions (use Button/Secondary)
Padding: 12px vertical, 16px horizontal
Icon: Optional, 16px size
Text: Keep under 3 words
```

### Create Component Library Documentation

Beyond Figma, create a doc that lists:

```
# Component Library

## Button
- Button/Primary (for main CTAs)
- Button/Secondary (for alternative actions)
- Button/Ghost (for tertiary actions)
- Button/Icon (icon-only button)

### Button/Primary
- Size: Medium (standard)
- Padding: 12px vertical, 16px horizontal
- States: Default, Hover, Active, Disabled, Loading
- Usage: Primary call-to-action, form submission
- Don't use for: Links, secondary actions

[etc. for each component]
```

---

## Common Component Mistakes

1. **Master component too complex:** 20 variants + 50 overrides = confusing
   - **Fix:** Break into smaller components. Button vs. IconButton vs. ButtonGroup

2. **Inconsistent naming:** "Button," "CTA," "Primary Button," "Primary Btn"
   - **Fix:** Establish naming convention before creating any components

3. **Overrides not controlled:** Developers change anything, breaking consistency
   - **Fix:** Lock overrides for critical properties (spacing, colors)

4. **Components change during project:** V1 button ≠ V2 button
   - **Fix:** Create V2 components, don't modify existing ones mid-project

5. **No documentation:** Designers don't know which button to use where
   - **Fix:** Add descriptions to every component

6. **Too many variants:** One master with 30+ variants
   - **Fix:** Limit to 5-7 variants per component. Create separate components instead.

---

## Updating Components Across Design

### Change Master = Update All Instances

1. Select master component
2. Edit it (change color, size, spacing)
3. All instances update automatically

**Example:** Change primary button color from blue to purple
- Edit Button/Primary master
- All instances everywhere update instantly
- No manual color-swapping needed

### Detaching Instances

If you need to break the link:
- Right-click instance
- "Detach instance"
- Now it's independent (won't update with master)

**Use rarely.** Only when truly need independent copy.

---

## Component Best Practices Checklist

Before considering components "done":

- [ ] **Naming convention established** (BEM-style)
- [ ] **Variants organized** (size, state, type logically grouped)
- [ ] **Auto layout enabled** (responsive behavior)
- [ ] **Resizing rules defined** (constraints or hug/fill behavior)
- [ ] **Overrides controlled** (what can change, what's locked)
- [ ] **Nested components used** (avoiding duplication)
- [ ] **Documentation added** (descriptions in Figma)
- [ ] **Component library documented** (external doc if needed)
- [ ] **Main components organized** (separate page or section)
- [ ] **No unused components** (clean library)
- [ ] **Consistent styling** (colors, typography, spacing from design system)

---

## Tools & Plugins

- **Figma Tokens:** Manage design tokens in code, sync to Figma
- **Master:** Find and replace across components
- **Rename It:** Batch rename components
- **Component Map:** Visualize component dependencies
- **Figma Cleanup:** Remove unused components

---

## Next Steps

Once components are set up:

1. Use components in your page designs (instead of recreating)
2. Create color styles and typography styles
3. Test component library with team members
4. Document in design system (Figma or external wiki)
5. Hand off to developers with component specs
