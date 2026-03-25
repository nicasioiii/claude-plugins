# Components & Variants — Complete Reference

## COMPONENT CREATION WORKFLOW

### Step-by-Step: Button Component
1. Create text layer with "Button Label"
2. Shift+A to add auto layout (creates frame)
3. Set padding: 12px vertical, 24px horizontal
4. Add background fill (primary color)
5. Set corner radius: 8px
6. Select frame > Create Component (Ctrl/Cmd+Alt+K)
7. Rename: "Button/Primary"

### Step-by-Step: Input Component
1. Create text layer "Label" (12px, medium weight)
2. Below: create frame 360px wide, 40px tall
3. Add placeholder text inside frame (14px, gray)
4. Add 1px gray border, 6px corner radius, 12px horizontal padding
5. Select label + input frame > Shift+A (vertical auto layout, gap 4px)
6. Create Component

### Step-by-Step: Card Component
1. Design card with image frame, title text, description text, button
2. Select all > Shift+A (vertical auto layout, gap 16px)
3. Set internal padding: 0 top (image bleeds), 16px sides, 16px bottom
4. Add border-radius, optional shadow
5. Create Component
6. Set image to Fill Container (horizontal), fixed height
7. Set text layers to Fill Container (horizontal) for text wrapping

---

## NAMING CONVENTIONS

### Category Slash Pattern
```
Button/Primary
Button/Secondary
Button/Tertiary
Button/Danger
Button/Icon Only

Input/Text
Input/Select
Input/Textarea
Input/Checkbox
Input/Radio
Input/Toggle

Card/Feature
Card/Testimonial
Card/Product
Card/Metric

Nav/Top Bar
Nav/Sidebar
Nav/Tab Bar
Nav/Breadcrumb
```

### Creating Multiple Components at Once
- Select all elements that should be separate components
- Dropdown arrow next to Create Component > Create Multiple Components
- Each selected element becomes its own component

---

## COMPONENT PROPERTIES REFERENCE

### Text Property
**Purpose**: Allow changing text content from parent selection without deep-selecting
**Create**: Select text child inside master > Content section > click create property
**Naming**: "Label", "Title", "Description", "Placeholder"
**Usage**: Select instance > change text in properties panel (no need to enter component)

### Boolean Property
**Purpose**: Toggle child visibility (show/hide)
**Create**: Select layer inside master > click Boolean property icon
**Naming**: "Has Icon", "Show Badge", "Show Description"
**Usage**: Checkbox toggle in instance properties panel
**Effect**: Layer visibility toggles on/off

### Instance Swap Property
**Purpose**: Swap nested component instances
**Create**: Select nested instance inside master > click create instance swap property
**Naming**: "Icon", "Avatar", "Badge Type"
**Usage**: Dropdown in instance properties to pick replacement component
**Constraint**: Can only swap with components from same library/file

### Two Creation Methods
1. **Bottom-up**: Select child element inside master component > create property from its panel
2. **Top-down**: Select master component > add property from properties section > link to children

---

## VARIANT ARCHITECTURE

### Single-Dimension Variant (State)
```
Button Component Set
├── State = Default    (base appearance)
├── State = Hover      (white overlay 10-20%)
├── State = Pressed    (black overlay 20-40%)
├── State = Disabled   (50% opacity)
└── State = Loading    (spinner replaces text)
```

### Multi-Dimension Variant (State x Size)
```
Button Component Set
├── State = Default, Size = SM    (padding 8/16, font 14)
├── State = Default, Size = MD    (padding 12/24, font 16)
├── State = Default, Size = LG    (padding 16/32, font 16)
├── State = Hover, Size = SM
├── State = Hover, Size = MD
├── State = Hover, Size = LG
├── State = Pressed, Size = SM
├── ... (all combinations)
└── State = Loading, Size = LG
```

### Three-Dimension Variant (Type x State x Size)
```
Button Component Set
├── Type = Primary, State = Default, Size = MD
├── Type = Primary, State = Hover, Size = MD
├── Type = Secondary, State = Default, Size = MD
├── Type = Tertiary, State = Default, Size = MD
├── ... (all 3 x 5 x 3 = 45 combinations)
```

**Practical tip**: For large variant sets, add text labels OUTSIDE the component set for visual organization.

### Recommended Button Variant Matrix
| Property | Values | Total |
|----------|--------|-------|
| Type | Primary, Secondary, Tertiary, Danger | 4 |
| State | Default, Hover, Pressed, Disabled | 4 |
| Size | SM, MD, LG | 3 |
| Has Icon | True, False | 2 |
| **Total combinations** | | **96** |

Note: You don't need ALL combinations. Start with the most-used and expand. Minimum viable: Type x State (16 variants).

---

## INTERACTIVE COMPONENTS

### Setting Up Hover Interaction
1. Select Default variant in component set
2. Switch to Prototype tab
3. Drag connection handle to Hover variant
4. Trigger: "While Hovering"
5. Animation: "Instant" (for state change) or "Smart Animate" (for smooth transition)

### Setting Up Click/Press Interaction
1. Select Default variant
2. Drag connection to Pressed variant
3. Trigger: "On Click"
4. Animation: "Smart Animate" (duration 100-200ms)

### Key Rules for Interactive Components
- Must create connections for each size variant separately (SM hover, MD hover, LG hover)
- Use "While Hovering" for hover states (reverts automatically on mouse leave)
- Use "On Click" with "Back" action for toggle behavior
- Smart Animate works best when variants have matching layer structure

---

## DESIGN SYSTEM SETUP CHECKLIST

### Foundation Layer
- [ ] Color palette (11 shades per color, using uicolors.app or similar)
- [ ] Color styles created ("Primary/50" through "Primary/900")
- [ ] Typography scale (using typescale.com, Major Third ratio)
- [ ] Text styles created ("Display/2XL/Bold" through "Caption/SM/Regular")
- [ ] Spacing scale defined (4pt grid: 0, 4, 8, 12, 16, 20, 24, 32, 40, 48, 64)
- [ ] Grid layouts per breakpoint (12-col desktop, 6-col tablet, 4-col mobile)
- [ ] Shadow/elevation styles (low, medium, high)
- [ ] Border radius tokens (4px, 6px, 8px, 12px, 16px, full/pill)

### Variable Layer
- [ ] Primitive variable collection (raw colors, raw spacing values)
- [ ] Token variable collection (semantic aliases referencing primitives)
- [ ] Variables applied to components (not raw hex codes)

### Component Layer
- [ ] Button variants (type x state x size minimum)
- [ ] Input variants (type x state)
- [ ] Card variants (type x optional properties)
- [ ] Navigation components (desktop nav, mobile nav)
- [ ] Icon set (consistent size, consistent style)
- [ ] Dividers, badges, avatars, tooltips

### Organization Layer
- [ ] All layers named meaningfully
- [ ] Forward-slash categories for all styles and components
- [ ] Cover page with project info
- [ ] Divider pages separating sections

---

## COMMON FIGMA SHORTCUTS

| Action | Mac | Windows |
|--------|-----|---------|
| Add Auto Layout | Shift+A | Shift+A |
| Create Component | Cmd+Alt+K | Ctrl+Alt+K |
| Detach Instance | Right-click > Detach | Right-click > Detach |
| Deep Select | Cmd+Click | Ctrl+Click |
| Batch Rename | Cmd+R | Ctrl+R |
| Show Measurements | Alt+hover | Alt+hover |
| Toggle Rulers | Shift+R | Shift+R |
| Quick Add Element | -- | -- |
| Create Frame | F or A | F or A |
| Enter Edit Mode | Enter or double-click | Enter or double-click |
| Exit Edit Mode | Escape or Done | Escape or Done |
