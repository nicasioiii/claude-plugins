---
name: UI Components
description: "Buttons, cards, navigation, forms, modals, tables, lists, snackbars, tabs, states, accessibility patterns, and auto layout component construction in Figma. FOR: designing individual UI elements, component pattern lookup, state design, sizing guidelines, interaction affordance. MANDATORY TRIGGERS: button design, card design, form input, modal, dialog, navigation element, tab bar, table design, component pattern, UI element, snackbar, toast, list design, badge, pagination, tooltip, dropdown, accordion, toggle, checkbox, radio, select, breadcrumb, search bar. Do NOT use for — use design-systems for Figma component/variant setup and token architecture, use web-layout for assembling components into full pages, use dashboard-app-design for data-heavy app interfaces."
---

# UI Components

Individual UI elements are the building blocks of every interface. This skill covers the design patterns, sizing, states, and affordance rules for each component type. Components designed here feed into design-systems for systematization and into web-layout or dashboard-app-design for page assembly.

## CORE PRINCIPLE: Build Components Inside-Out

Start with the text layer. Add auto layout. Add fill/stroke. Adjust padding. This creates responsive components by default.

**Never** create a rectangle and place text inside it. Always start from content and wrap outward. [Arash, MDS]

---

## BUTTON PATTERNS

### Construction Method (Figma)
1. Create text layer with button label
2. Add Auto Layout (Shift+A) -- creates auto layout frame
3. Add background fill, adjust corner radius
4. Set padding: vertical and horizontal independently
5. Result: button that hugs content and resizes with text changes

### Three Sizes
| Size | Vertical Padding | Horizontal Padding | Font Size | Min Height |
|------|-----------------|-------------------|-----------|------------|
| Small | 8px | 16px | 14px | 32px |
| Medium | 12px | 24px | 16px | 40px |
| Large | 16px | 32px | 16px | 48px |

Minimum touch target: 44px height for mobile.

### Button Types
- **Contained/Filled**: Primary actions. Solid background, high contrast. Highest visual weight
- **Outlined**: Secondary actions. Stroke border, no fill. Medium visual weight
- **Text/Ghost**: Tertiary actions. No border, no fill. Lowest visual weight
- **Danger**: Destructive actions. Red fill or red text. Reserved for delete/remove
- **Icon Button**: Icon-only, typically 40x40px with centered icon

### State Design
| State | Visual Treatment | Purpose |
|-------|-----------------|---------|
| Default | Base appearance | Resting state |
| Hover | White overlay 20% opacity (brighter) | Indicates interactivity |
| Pressed | Black overlay 40% opacity (darker) | Confirms click |
| Disabled | 50% opacity, no hover | Prevents interaction |
| Loading | Replace text with spinner | Shows processing |
| Focused | 2px blue outline (keyboard) | Accessibility |

**Weight signals action priority**: Primary action = heavier weight; secondary = lighter weight. Bold "Send" vs. regular "Cancel" [MDS].

---

## CARD PATTERNS

### Three Card Types
1. **Elevated**: Drop shadow creates depth. Floats above surface. Best for interactive cards
2. **Outlined**: 1px border defines boundary. Flat appearance. Best for grids with many cards
3. **Filled/Contained**: Solid background color. Subtle differentiation. Best for feature sections

### Card Anatomy (4 Sections)
1. **Rich media**: Image or illustration at top (16:9, 4:3, or 1:1 aspect ratio)
2. **Mandatory info**: Title + description. Always present
3. **Optional supporting**: Metadata, tags, dates, avatars
4. **Action section**: CTA buttons, links, icons

### Card Spacing
- Internal padding: 16-24px (consistent all sides)
- Image-to-content gap: 16px
- Element-to-element within card: 8-12px
- Border radius: 8-12px
- Card-to-card gap in grid: 16-24px

### Responsive Card Grid (Auto Layout Wrap)
Set parent auto layout direction to **Wrap**. Set child cards with min-width (e.g., 300px) and Fill Container. Cards automatically reflow from 3 columns to 2 to 1 as parent shrinks. No breakpoint changes needed [Arash].

### Hover States for Cards
- Lift with shadow: translateY -4px + deeper shadow
- Border highlight: add 2px accent border
- Subtle scale: scale(1.02)
- Background shift: 5% darker background

---

## FORM INPUTS & TEXT FIELDS

### Field States
| State | Border | Background | Label | Helper Text |
|-------|--------|-----------|-------|-------------|
| Enabled | 1px gray | White | Dark gray above | Optional |
| Focused | 2px primary | White | Primary color above | Optional |
| Filled | 1px gray | White | Dark gray above (smaller) | Optional |
| Error | 2px red | Light red tint | Red above | Red error message below |
| Disabled | 1px light gray | Light gray | Medium gray above | Grayed out |

### Critical Rules
- **Always place labels above input fields** -- never use placeholder text as the only label [Arash, consensus]
- Placeholder text color must be lighter than body text and must NOT match interactive text color
- Explain "why" when requesting personal info (phone number, birthday) -- show the benefit
- **Never use justified alignment** in any text field [Arash]
- Optimal input line length: 40-60 characters for text areas

### Validation
- Show errors on blur (leaving field), not only on submit
- Clear error messages: "Email must include @" not "Invalid input"
- Required fields: red asterisk or "(Required)" text
- Real-time validation preferred over submit-time validation

### Input Sizing
- Standard height: 40px
- Horizontal padding: 12px
- Border: 1px solid
- Border radius: 4-8px
- Font: 14-16px
- Label: 12-14px, medium weight, 4-8px above input

---

## NAVIGATION ELEMENTS

### Desktop Navigation Types
- **Top horizontal bar**: Logo left, menu center, CTA right. Auto layout with Space Between [Arash]
- **Sidebar/drawer**: Vertical nav for apps. Slides out or persists
- **Mega menu**: Expanded dropdown with links + featured content side by side [Segall]
- **Tab navigation**: Horizontal tabs for switching views within a page

### Mobile Navigation Types
- **Tab bar (bottom)**: 3-5 tabs maximum. Most important actions. Located at bottom of screen [Arash]
- **Hamburger menu**: Full-screen overlay with animated open/close. Custom-built, not default navbar [Segall]
- **Breadcrumbs**: Horizontal path at top of content showing navigation history

### Navigation States
- **Default**: Base appearance
- **Hover**: Subtle background or underline. Position-based items (nav bar) don't need color to look clickable -- position signals interactivity [MDS]
- **Active/Current**: Bold weight or highlighted background to indicate current page
- **Disabled**: Grayed out (rare for nav)

### Navigation Sizing
| Element | Height | Font Size | Padding |
|---------|--------|-----------|---------|
| Desktop nav bar | 56-72px | 14-16px | 16-24px horizontal |
| Mobile top bar | 56px | 16px | 16px horizontal |
| Mobile tab bar | 56px | 10-12px | -- |
| Nav link | -- | 14-16px | 8-12px vertical, 12-16px horizontal |

### Chevron/Arrow Pattern
- Dropdown: chevron rotates to indicate open/closed state
- Breadcrumb: forward arrow between items
- Back navigation: left arrow

---

## DIALOGS & MODALS

### Two Types
1. **Basic dialog**: Smaller modal requiring user interaction. Title, content, 2 buttons (confirm + cancel)
2. **Full-screen dialog**: Entire screen for complex tasks. Close button in header

### Design Rules
- **Always add dark overlay** (rgba 0,0,0, 50%) behind modal for focus [Arash]
- Clear header describing purpose
- Close button visible (X in top-right)
- Primary action emphasized over secondary (color contrast)
- Keyboard dismissible (Escape key)
- Focus trapped inside modal (keyboard nav stays within)

### Modal Sizing
- Width: 400-700px (content-dependent)
- Max height: 80vh with internal scroll
- Padding: 20-24px header, 20-24px content, 16-20px footer
- Button alignment: right-aligned in footer

---

## TABLES

### Alignment Rules
- Headers: left-aligned
- Text columns: left-aligned
- Numbers/values: **right-aligned** (easier to compare) [Arash, MDS]
- Action buttons: consistent position per row
- Consistent spacing between all cells

### Table Features
- **Sticky headers** for long tables
- Sortable columns with chevron direction indicator
- Pagination: show "1-10 of 250" format
- Row hover: subtle background highlight for tracking
- Expandable rows for detail views
- Selectable rows with checkboxes for bulk actions

### Table States
- Default, hover row, sorted column, selected row, empty ("No data" message), loading (skeleton rows)

---

## LISTS

### List Anatomy
- Container, list items, item content, dividers, interactive elements
- Six states per item: enabled, disabled, hover, focused, pressed, dragged
- Use horizontal dividers to separate items

---

## SNACKBARS / TOASTS

- Brief notification at bottom of screen. Auto-disappears after 3-5 seconds
- **Maximum one action button** -- user doesn't have time to process more [Arash]
- Keep message brief and clear
- Use contrasting colors and subtle animation for noticeability
- Don't stack multiple snackbars simultaneously

---

## ICONOGRAPHY RULES

- Two types: **outline** (stroke, not filled) and **solid** (completely filled)
- Outline = inactive/unselected state; Solid = active/selected state
- **Pick one style per project** (all outline or all solid). Exception: outline inactive / solid active toggle
- **Never redesign well-known icons** (home, search, heart, share) -- use established icon libraries [Arash]
- Standard icon size: 24x24px. Use consistent sizes throughout (16x16, 20x20, 24x24, or 32x32)
- Consistent icon box sizes ensure alignment with text

---

## AFFORDANCE CHECKLIST

Every component must communicate how it should be used:
- Buttons look pressable (fill, shadow, distinct shape)
- Links look clickable (color, underline, or positional convention)
- Inputs look typable (border, background, placeholder)
- Sliders look draggable (handle + track)
- Toggles look switchable (on/off visual states)

**WCAG rule**: Color alone must NOT be the only way to convey information -- combine with underline, weight, position, or icons [MDS].

---

## ANTI-PATTERNS

- Primary and secondary buttons too visually similar
- Disabled state that still looks clickable
- Placeholder text as the only label
- Cards at different heights in a grid
- Images at different aspect ratios in a card grid
- No loading state on buttons (users think action failed)
- Center-aligned long text in inputs
- Multiple modals stacked on each other
- Too many navigation items (10+) without grouping

---

## RELATED SKILLS

- **design-systems**: For creating Figma components, variants, and tokens from these patterns
- **layout-spacing**: For the spacing system (4pt/8pt grid) that governs component internal spacing
- **typography-systems**: For text sizing, weight, and hierarchy within components
- **color-systems**: For interactive vs structural color decisions in component states
- **web-layout**: For assembling components into full page layouts
- **dashboard-app-design**: For data-heavy component patterns (metric cards, data tables)
- **design-critique**: For auditing component consistency and quality
