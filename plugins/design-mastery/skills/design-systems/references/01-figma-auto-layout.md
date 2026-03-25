# Figma Auto Layout — Complete Reference

## AUTO LAYOUT CHEATSHEET

### Adding Auto Layout
- Select elements > Shift+A
- Or: right-click > Add Auto Layout
- Or: click + icon in Auto Layout section of design panel
- Remove: click minus icon in Auto Layout section

### Direction Options
| Direction | Icon | Behavior | Keyboard |
|-----------|------|----------|----------|
| Horizontal | → | Children side by side (row) | Default after Shift+A on horizontal selection |
| Vertical | ↓ | Children stacked (column) | Default after Shift+A on vertical selection |
| Wrap | ↻ | Children flow to new line when space runs out | Set in direction dropdown |

### Resizing Behavior Matrix

| Parent H-Resize | Parent V-Resize | Child H-Resize | Child V-Resize | Result |
|-----------------|-----------------|----------------|----------------|--------|
| Hug | Hug | Hug | Hug | Tight wrapper (buttons) |
| Fixed | Hug | Fill | Hug | Children stretch horizontally (responsive cards in row) |
| Fill | Hug | Fill | Hug | Container fills parent, children fill container |
| Hug | Fixed | Hug | Fill | Children stretch vertically (sidebar items) |
| Fixed | Fixed | Fill | Fill | Fully responsive container (main content area) |

### Common Responsive Patterns

**Responsive Button:**
- Text layer: Hug/Hug
- Auto layout frame: Hug/Hug
- Padding: 12px vertical, 24px horizontal
- Result: button grows/shrinks with text content

**Responsive Card:**
1. Title + description: vertical auto layout, gap 4px, both Hug
2. Profile image + text group: horizontal auto layout, gap 12px
3. Card wrapper: vertical auto layout
4. Set inner text frames to Fill Container to prevent overflow
5. Set card to Fill Container within parent grid

**Responsive Navbar:**
1. Menu items group: horizontal auto layout, gap 24px
2. Logo + menu + CTA: horizontal auto layout
3. Set spacing mode to Space Between (logo left, menu center, CTA right)
4. Add background fill, padding 16px vertical, 48px horizontal
5. Set to Fill Container within parent

**Responsive Card Grid (Wrap):**
1. Card container: auto layout, direction Wrap, gap 16px
2. Each card: Fill Container width, min-width 300px
3. Cards auto-reflow: 3 cols > 2 cols > 1 col as parent shrinks

---

## SPACING MODE REFERENCE

### Packed (Default)
- Fixed gap value between children
- Children cluster together with consistent spacing
- Set gap value in pixels (e.g., 8, 12, 16, 24)

### Space Between
- Children push to edges of parent
- Gap auto-adjusts to distribute remaining space evenly
- Set spacing to "Auto" in the gap field
- Perfect for: navbar (logo left, CTA right), card with title and action

### Negative Spacing
- Set gap to negative value (e.g., -8)
- Children overlap
- Canvas Stacking controls which child appears on top
- Use: overlapping avatars, stacked cards with offset

---

## PADDING REFERENCE

### Uniform Padding
- All four sides same value
- Set one value; link icon locks all sides

### Independent Padding
- Click the 4-corner icon to unlock per-side padding
- Top, Right, Bottom, Left (clockwise)
- Common: more horizontal than vertical padding (e.g., 12px top/bottom, 24px left/right)

### Common Padding Values
| Component | Vertical | Horizontal |
|-----------|----------|------------|
| Button SM | 8px | 16px |
| Button MD | 12px | 24px |
| Button LG | 16px | 32px |
| Card | 16-24px | 16-24px |
| Input field | 8-12px | 12-16px |
| Section | 64-120px | 24-48px |
| Navbar | 12-24px | 24-48px |
| Modal header/footer | 16-20px | 20-24px |
| Modal content | 20-24px | 20-24px |

---

## ALIGNMENT WITHIN AUTO LAYOUT

### 9-Point Alignment Grid
```
[TL] [TC] [TR]
[ML] [MC] [MR]
[BL] [BC] [BR]
```
- TL = Top Left (default)
- MC = Middle Center (centered content)
- BC = Bottom Center (footer buttons)

### Alignment + Space Between Combinations
| Alignment | Spacing | Result |
|-----------|---------|--------|
| Top Left | Packed | Standard stacked list |
| Top Left | Space Between | Spread items (navbar) |
| Middle Center | Packed | Centered group (hero text) |
| Middle Left | Space Between | Sidebar with top and bottom groups |

---

## CONSTRAINTS REFERENCE (Non-Auto-Layout)

### When to Use Constraints vs Auto Layout
| Scenario | Use |
|----------|-----|
| Responsive content reflow | Auto Layout |
| Pinning element to corner | Constraints (or Absolute Position in AL) |
| Stretching element with parent | Both work: AL Fill or Constraint Left+Right |
| Overlapping decorative elements | Constraints with Absolute positioning |
| Fixed position elements (sticky nav concept) | Constraints |

### Constraint Combinations
| Goal | H-Constraint | V-Constraint |
|------|-------------|-------------|
| Pin to top-left | Left | Top |
| Pin to top-right | Right | Top |
| Pin to bottom-center | Center | Bottom |
| Stretch horizontally | Left and Right | Top |
| Stretch both ways | Left and Right | Top and Bottom |
| Scale proportionally | Scale | Scale |

### Left+Right vs Scale
- **Left and Right**: Maintains absolute pixel padding values on both sides. Element width changes.
- **Scale**: Maintains percentage ratios. Element at 50% of parent width stays at 50%.
- Use Left+Right for containers. Use Scale for proportional elements (images, decorative shapes).

---

## FRAME vs GROUP vs SECTION

| Feature | Frame | Group | Section |
|---------|-------|-------|---------|
| Clip content | Yes | No | No |
| Auto layout | Yes | No | No |
| Constraints | Yes (children) | No | No |
| Fill/stroke | Yes | No | No |
| Can nest content | Yes | Yes | Yes (frames) |
| Purpose | Design container | Temporary grouping | Organize canvas |

### Practical Rule
- **Always use Frames** for design containers (not groups)
- Use Groups only for temporary multi-select operations
- Use Sections to organize related frames on the canvas (e.g., "Login Flow" section containing 5 screens)

---

## BOOLEAN, MASK & PEN TOOLS

### Boolean Operations
| Operation | Result | Use Case |
|-----------|--------|----------|
| Union | Combines shapes | Creating icons (cloud = union circles + rect) |
| Subtract | Top removes from bottom | Moon icon (circle - circle), cutouts |
| Intersect | Keeps overlap only | Eye icon center, cropping |
| Exclude | Removes overlap, keeps rest | Ring shapes, XOR patterns |

**Layer order matters for Subtract**: top layer is cut from bottom layer.

### Masks
- Mask shape must be BELOW the image in layers
- Select shape + image > click Mask
- Three types: Alpha (most common), Vector, Luminance
- Profile picture trick: circle shape > Place Image > click circle

---

## PROTOTYPING CONNECTIONS

### Trigger Types
| Trigger | When | Best For |
|---------|------|----------|
| On Click | User clicks | Navigation, buttons, toggles |
| While Hovering | Mouse enters element | Hover states, tooltips |
| On Drag | User drags | Sliders, drawers |
| Mouse Enter / Leave | Cursor enters/exits | Dropdown menus |
| After Delay | Time passes | Auto-advance, notifications |

### Animation Types
| Animation | Duration | Best For |
|-----------|----------|----------|
| Instant | 0ms | Hover state changes |
| Dissolve | 200-300ms | Simple transitions |
| Smart Animate | 200-500ms | Complex state transitions |
| Move In/Out | 200-400ms | Drawers, sheets |
| Push | 200-300ms | Page navigation |
| Slide | 200-300ms | Carousel, tab content |
