# Button & Card Design Patterns — Quick Reference

## BUTTON SIZING MATRIX

### Web Buttons
| Size | Height | H-Padding | V-Padding | Font | Border Radius | Use Case |
|------|--------|-----------|-----------|------|---------------|----------|
| XS | 28px | 12px | 4px | 12px | 4px | Inline actions, tags |
| SM | 32px | 16px | 8px | 14px | 6px | Secondary, compact UI |
| MD | 40px | 24px | 12px | 16px | 8px | Default, most common |
| LG | 48px | 32px | 16px | 16px | 8px | Hero CTAs, forms |
| XL | 56px | 40px | 20px | 18px | 8px | Landing page primary |

### Mobile Buttons
- Minimum touch target: 44x44px (Apple HIG) / 48x48px (Material Design)
- Full-width buttons on mobile: padding 16px vertical, fill container horizontal
- Bottom-fixed CTA: 16px from bottom edge, 16px side margins

## BUTTON TYPE DECISION TREE

```
What action does this trigger?
├── Primary action (submit, confirm, save, buy)
│   └── Contained/Filled button (strongest visual weight)
├── Secondary action (cancel, back, dismiss)
│   └── Outlined button (medium visual weight)
├── Tertiary action (learn more, skip, see all)
│   └── Text/Ghost button (lightest visual weight)
├── Destructive action (delete, remove, clear)
│   └── Danger button (red, outlined or filled)
└── Space-constrained (toolbar, inline)
    └── Icon button (40x40, centered icon)
```

## BUTTON STATE CONSTRUCTION (Figma)

### Hover State
- Add second fill layer on top: white (#FFFFFF) at 10-20% opacity
- Result: button appears slightly brighter
- Alternative: increase brightness 10% in HSB

### Pressed State
- Add second fill layer on top: black (#000000) at 20-40% opacity
- Result: button appears notably darker
- Alternative: decrease brightness 15% in HSB

### Disabled State
- Reduce entire component opacity to 40-50%
- Remove all hover/press interactions
- Cursor: not-allowed (in implementation)

### Loading State
- Replace text with spinner/dots animation
- Maintain exact button dimensions (no layout shift)
- Optional: reduce opacity to 80%

### Focus State (Accessibility)
- 2px outline in blue (#2563EB or brand color) offset 2px from button edge
- Must be visible on all backgrounds (light and dark)

## BUTTON ICON PLACEMENT

- Icon left of text: directional/action context (arrow left for "Back", plus for "Add")
- Icon right of text: forward action (arrow right for "Next", external link)
- Icon only: when meaning is universally understood (play, pause, close, search)
- Icon + text spacing: 8px gap between icon and label

## BUTTON GROUPS

- Primary + secondary side by side: primary right (for LTR), secondary left
- Gap between grouped buttons: 8-12px
- Stacked (mobile): primary on top, secondary below, full width, 8px gap

---

## CARD DESIGN PATTERNS

### Card Type Decision
| Card Type | Shadow | Border | Background | Best For |
|-----------|--------|--------|-----------|----------|
| Elevated | Yes (drop shadow) | None | White | Interactive, clickable cards |
| Outlined | None | 1px gray | White | Dense grids, content listings |
| Filled | None | None | Light gray/tint | Feature sections, static info |

### Card Shadow Values
| Elevation | X | Y | Blur | Spread | Color | Use |
|-----------|---|---|------|--------|-------|-----|
| Low | 0 | 1px | 3px | 0 | rgba(0,0,0,0.1) | Default/resting |
| Medium | 0 | 4px | 6px | -1px | rgba(0,0,0,0.1) | Hover state |
| High | 0 | 10px | 15px | -3px | rgba(0,0,0,0.1) | Lifted/dragging |

### Card Grid Responsive Behavior

**Figma Auto Layout Wrap Method:**
1. Parent: Auto Layout, direction Wrap, gap 16-24px
2. Children: Fill Container width, min-width 280-320px
3. Result: 3 cols at 1200px+ > 2 cols at 800px+ > 1 col at 400px+

**Web (CSS Flexbox):**
- Parent: display flex, flex-wrap wrap, gap 1rem
- Child: flex-grow 1, flex-basis 18rem (adjusts column count automatically)

### Common Card Compositions

**Product Card:**
- Image (16:9 or 4:3, object-fit cover)
- Category tag (12px, uppercase, tracking 80%)
- Title (18px, semi-bold)
- Price (16px, bold) + original price (strikethrough, lighter)
- Rating stars + review count
- Padding: 0 on image, 16px on content

**Feature Card:**
- Icon (32-48px, brand color)
- Title (18px, semi-bold)
- Description (14-16px, regular, lighter color)
- Optional CTA link
- Padding: 24px all sides

**Testimonial Card:**
- Large quotation mark (decorative, 48px+, low opacity)
- Quote text (16-18px, italic or regular)
- Divider line
- Avatar (48px circle) + Name (16px, semi-bold) + Title (14px, lighter)
- Padding: 24-32px all sides

**Metric Card (Dashboard):**
- Label (12-14px, uppercase, lighter)
- Value (24-36px, bold)
- Trend indicator (up/down arrow + percentage, green/red)
- Optional sparkline chart
- Padding: 16-20px all sides

### Card Image Aspect Ratios
| Ratio | Use Case | Figma Setup |
|-------|----------|-------------|
| 16:9 | Blog posts, video thumbnails | Frame 360x202 |
| 4:3 | Product photos, features | Frame 360x270 |
| 1:1 | Profile photos, app icons | Frame 360x360 |
| 3:2 | Photography, portfolio | Frame 360x240 |

Always use the same aspect ratio for all cards in a grid. Mixed ratios create uneven heights.

### Card Interaction Patterns
- Entire card clickable: wrap in Link Block (Webflow) or use card as button
- Specific CTA only: button inside card, rest is non-interactive
- Multiple actions: primary CTA + secondary link, both inside card footer

---

## BADGE / TAG PATTERNS

### Badge Types
| Type | Padding | Font | Radius | Use |
|------|---------|------|--------|-----|
| Status | 4px/8px | 12px semi-bold | 4px | Active, Pending, Error |
| Count | 4px/8px | 12px bold | Full (pill) | Notifications (3, 99+) |
| Label | 4px/12px | 12px regular | 4px | Categories, tags |

### Status Badge Colors
- Active/Success: green background (#ECFDF5) + green text (#065F46)
- Warning: yellow background (#FFFBEB) + amber text (#92400E)
- Error/Danger: red background (#FEF2F2) + red text (#991B1B)
- Info: blue background (#EFF6FF) + blue text (#1E40AF)
- Neutral: gray background (#F3F4F6) + gray text (#374151)
