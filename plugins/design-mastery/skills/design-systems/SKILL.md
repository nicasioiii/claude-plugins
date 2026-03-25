---
name: Design Systems
description: "Atomic design methodology, Figma components, variants, variables, design tokens, auto layout, style guides, component libraries, file organization, Dev Mode handoff. FOR: setting up reusable design systems in Figma, creating component libraries, establishing design tokens and variables, organizing design files, building scalable systems. MANDATORY TRIGGERS: design system, design tokens, Figma components, Figma variants, Figma variables, auto layout, component library, style guide, atomic design, text styles, color styles, file organization, responsive components, interactive components, Dev Mode, handoff, constraints, frames, nested components, component properties, boolean property, instance swap, prototype. Do NOT use for — use ui-components for individual component design patterns and sizing, use typography-systems for type scale decisions, use color-systems for palette construction."
---

# Design Systems

A design system is a collection of reusable components, guidelines, and principles that ensures consistency, saves time, and enables scalability. This skill covers the Figma mechanics of building and maintaining systems -- from atomic elements through variables and tokens to component handoff.

## ATOMIC DESIGN METHODOLOGY

Five levels from simple to complex [Arash]:

1. **Atoms**: Simplest elements that cannot be broken down further -- buttons, labels, icons, input fields
2. **Molecules**: Groups of atoms -- search bar (input + button), navigation item (icon + label)
3. **Organisms**: Groups of molecules -- header (logo + nav + CTA), product card (image + text + button)
4. **Templates**: Page-level structures defining layout and content zones
5. **Pages**: Specific template instances with real content

**Build bottom-up**: define atoms first, compose into molecules, assemble into organisms. This ensures every element inherits system properties.

---

## FIGMA FILE ORGANIZATION

### Page Structure [MDS]
```
Cover                  → Project thumbnail with title/status
──── (divider) ────
References             → Screenshots, competitors, inspiration (messier = better)
Explorations           → Design playground, duplicates, direction finding
──── (divider) ────
M0 - Wireframes        → Low-fidelity layouts
M1 - First Pass        → Initial visual design
M2 - Refined           → Iterated designs
──── (divider) ────
Design System          → Components, styles, tokens
```

### Design System Page Structure [Arash]
Use separate pages (or frames within a page) for each category:
- **Foundation**: Color palette, typography scale, spacing system, grid definitions
- **Colors**: All color swatches with 11 tints/shades per color
- **Typography**: Type scale with weight variants
- **Icons**: Standard icon set as components
- **Components**: Buttons, inputs, cards, navigation (organized by atom/molecule/organism)

Use emoji arrows for sub-page indentation. Use forward-slash naming for style/component categories.

---

## AUTO LAYOUT (The Critical Feature)

### Core Concept
Auto layout makes frames responsive and adaptive. Add to any selection with **Shift+A**.

### Three Directions
1. **Horizontal**: Elements side by side (row)
2. **Vertical**: Elements stacked (column)
3. **Wrap**: Elements flow to next line when space runs out (2023 update)

### Resizing Options (Most Important Concept)
Every auto layout frame and child has horizontal AND vertical resizing:

| Option | Behavior | When to Use |
|--------|----------|-------------|
| **Hug Contents** | Frame wraps tightly around children | Buttons, badges, inline elements |
| **Fixed** | Manually specified dimension | Containers at specific widths |
| **Fill Container** | Expands to fill available parent space | Responsive children, text blocks |

**Key rule**: Making things responsive requires setting CHILDREN to Fill Container, not just the parent [Arash].

### Spacing Modes
- **Packed**: Fixed gap value between children (default)
- **Space Between**: Children push to edges, gap auto-adjusts (set spacing to "Auto")

### Building Responsive Components (Inside-Out Method)
1. Start from innermost elements
2. Add auto layout, set spacing
3. Move outward, wrapping groups in auto layout
4. Set children to Fill Container where responsiveness needed
5. Set parent spacing to Space Between where edge-to-edge needed

### Auto Layout Wrap for Responsive Grids
- Set parent direction to Wrap
- Set min-width on children (e.g., 300px)
- Combined with Fill Container, creates automatic column breakpoints
- Example: cards with min-width 300px go from 3 cols to 2 to 1 as parent shrinks

### Absolute Position (Within Auto Layout)
- Places element inside auto layout frame but removes it from flow
- Element floats over content, doesn't push other elements
- Combine with Constraints to pin to specific corner (e.g., notification badge in top-right)

### Advanced Properties
- **Negative spacing**: Overlap elements with negative gap values
- **Strokes Included/Excluded**: Whether stroke takes up layout space
- **Canvas Stacking**: Controls overlap order with negative spacing (First on Top vs Last on Top)
- **Align Text Baseline**: Aligns mixed-size text layers to baselines

---

## CONSTRAINTS (Non-Auto-Layout Frames)

Constraints tell Figma how children respond to parent size changes. Only work inside regular frames (not auto layout frames). But auto layout frames CAN have constraints within a non-auto-layout parent.

### Horizontal Options
| Constraint | Behavior |
|-----------|----------|
| Left | Maintains left padding (default) |
| Right | Maintains right padding |
| Left and Right | Stretches element, maintaining both paddings |
| Center | Maintains center position |
| Scale | Maintains percentage ratio |

### Practical Combinations
- Centered card: Center + Top
- Responsive full-width element: Left and Right + Top
- Fixed corner element (e.g., badge): Right + Top

---

## COMPONENTS & VARIANTS

### Component Creation
1. Design the element (auto layout recommended)
2. Select element, click Create Component (or Ctrl/Cmd+Alt+K)
3. Purple border = master component. Diamond icon in layers
4. All copies are instances (open diamond icon)

### Naming Convention
Use forward-slash for categories: "Button/Primary", "Button/Secondary", "Input/Text", "Input/Select"

### Instance Rules
- Changes to master propagate to all instances
- Individual instance overrides are possible but defeat the purpose of systems
- **Never nest master components** -- always use instances inside other components [Arash]
- Detach instance only when you need a one-off variation (breaks system link)

### Component Properties (Instance Controls)
Three property types that allow modifying instances without deep-selecting children:

| Property | Type | Example |
|----------|------|---------|
| **Text** | Content override | Button label text |
| **Boolean** | Show/hide toggle | "Has Icon" on/off |
| **Instance Swap** | Swap nested component | Change icon inside button |

### Creating Variants
1. Select component, click Add Variant
2. Creates component set (purple dashed border)
3. Add variant properties (e.g., State: default/hover/pressed)
4. Multi-dimension: combine properties (State x Size)

### Variant Architecture for Buttons
| Property | Values | Visual Difference |
|----------|--------|-------------------|
| **Type** | Primary, Secondary, Tertiary | Fill vs outline vs text |
| **State** | Default, Hover, Pressed, Disabled | Overlay opacity changes |
| **Size** | Small, Medium, Large | Padding and font size |
| **Has Icon** | True, False | Icon visibility toggle |

### State Construction
- **Hover**: Add white fill overlay at 10-20% opacity (brighter)
- **Pressed**: Add black fill overlay at 20-40% opacity (darker)
- **Disabled**: Component opacity 40-50%

### Interactive Components (Prototyping)
Connect variants in Prototype tab for hover/click animations:
1. Select default variant
2. Prototype tab > drag connection to hover variant
3. Trigger: "While Hovering", Animation: "Instant" or "Smart Animate"
4. Must create connections for each size variant separately

---

## STYLES (Text & Color)

### Text Styles
- Save text properties (typeface, weight, size, line height, letter spacing) for reuse
- Create: select text, click style icon in text section, name it
- **Color is NOT stored in text styles** -- only text properties
- Naming: use forward-slash categories ("Heading/H1", "Body/Regular", "Caption/Small")
- Modify globally: edit the style and ALL instances update

### Color Styles
- Save fill colors for reuse
- Naming: "Primary/50", "Primary/100" through "Primary/900"
- Also create stroke styles and effect styles (shadows)
- Access all local styles by clicking empty canvas

---

## VARIABLES & DESIGN TOKENS

### Variables vs Styles
| Feature | Styles | Variables |
|---------|--------|-----------|
| Store multiple values (gradients, shadows) | Yes | No (single raw values) |
| Reference other values (aliases) | No | **Yes** |
| Types | Fill, text, effect, grid | Color, Number, String, Boolean |
| Best for | Complex visual properties | Token architecture, theming |

### Two-Layer Variable Architecture

**Layer 1: Primitives**
- Collection named "Primitives"
- Raw values with descriptive names
- Color: "blue-50", "blue-100"... "blue-900" with actual hex values
- Spacing: 0, 4, 8, 12, 16, 20, 24 (4pt grid values)
- Group with forward-slash: "color/blue", "spacing"

**Layer 2: Tokens**
- Separate collection named "Tokens"
- **Never use primitive variables directly** -- tokens reference primitives via aliases [Arash]
- Semantic naming: "surface-primary" references "color/base/white"
- Functional naming: "button-background-primary" references "blue-600"
- Create alias: click variable value > Libraries > select primitive

**Why tokens matter**: Change a token's alias once and all elements using that token update. Enables theme switching (light mode to dark mode by swapping token aliases).

### Applying Variables
- Fill: select element > fill section > click variables icon > select token
- Spacing: select auto layout > click variable icon next to padding/gap values
- Variables work for fill, stroke, padding, margin, gap, corner radius

---

## TYPOGRAPHY SCALE SETUP

### Using typescale.com [Arash]
1. Base size: **16px** (web and mobile standard)
2. Scale ratio: **Major Third (1.25x)** recommended for most projects
3. Generate: 16 * 1.25 = 20, 20 * 1.25 = 25, etc. Round decimals
4. Range: 12px (smallest) to ~76px (display text)

### Other Ratios
- Minor Third (1.2x): Tighter scale, subtle differences
- Perfect Fourth (1.333x): Wider jumps, more dramatic hierarchy
- Golden Ratio (1.618x): Very dramatic, only for fashion/editorial

### Weight Variants Per Size
Create 4 weight variants for each size: Regular, Medium, Semi-Bold, Bold.
Naming: "Display/2XL/Regular", "Display/2XL/Bold", "Body/MD/Regular"

---

## COLOR PALETTE SETUP

### Using uicolors.app [Arash]
1. Enter base brand color
2. Tool generates 11 shades/tints (50 through 900, optionally 25)
3. Preview in UI examples within the tool
4. Export as SVG, paste directly into Figma
5. Built-in contrast grid verifies accessibility

### Naming Convention
- Primary/50, Primary/100... Primary/900
- Accent/50, Accent/100... Accent/900
- Neutral/50, Neutral/100... Neutral/900
- Higher number = darker shade

[CONTRARIAN: Arash uses Tailwind CSS colors from uicolors.app for all projects rather than custom palettes per project. Colors are pre-validated for contrast and accessibility.]

---

## DEV MODE & HANDOFF

### What Dev Mode Shows
- CSS/Swift/Kotlin code for selected elements
- Spacing values, colors, typography specs
- Component property values
- Variable/token references

### Handoff Best Practices
- Name all layers meaningfully (batch rename: Ctrl/Cmd+R)
- Use variables/tokens so developers see semantic names, not hex codes
- Organize components into clear categories
- Add notes or annotations for complex interactions
- Export assets at 2x resolution

---

## ANTI-PATTERNS

- Using primitive variables directly instead of tokens
- Nesting master components instead of instances
- Skipping text styles and color styles (manual values everywhere)
- Inconsistent naming (no forward-slash categories)
- Creating components too early before design direction is established
- Not using auto layout for components (fixed-size = breaks on content change)
- Forgetting to create all states for interactive components

---

## RELATED SKILLS

- **typography-systems**: For type scale decisions that feed into text styles and tokens
- **color-systems**: For palette construction that feeds into color variables and tokens
- **layout-spacing**: For spacing scale (4pt/8pt) that becomes spacing tokens
- **ui-components**: For the design patterns that components implement
- **web-layout**: For how components assemble into pages
- **design-critique**: For auditing system consistency
