# Form Input & Dialog Patterns — Quick Reference

## INPUT FIELD ANATOMY

```
[Label Text]                    ← 12-14px, medium weight, dark gray
┌─────────────────────────────┐
│ Placeholder text             │ ← 14-16px, regular, lighter gray (#999)
└─────────────────────────────┘
[Helper text or error message]  ← 12px, regular, gray or red
```

## INPUT STATE REFERENCE TABLE

| State | Border | Border Color | Background | Label Color | Cursor |
|-------|--------|-------------|-----------|-------------|--------|
| Default | 1px | #D1D5DB (gray-300) | #FFFFFF | #374151 (gray-700) | text |
| Hover | 1px | #9CA3AF (gray-400) | #FFFFFF | #374151 | text |
| Focused | 2px | Primary color | #FFFFFF | Primary color | text |
| Filled | 1px | #D1D5DB | #FFFFFF | #6B7280 (gray-500) | text |
| Error | 2px | #EF4444 (red-500) | #FEF2F2 (red-50) | #EF4444 | text |
| Disabled | 1px | #E5E7EB (gray-200) | #F9FAFB (gray-50) | #9CA3AF | not-allowed |
| Read-only | 0px | -- | #F3F4F6 (gray-100) | #6B7280 | default |

## INPUT SIZING

| Size | Height | H-Padding | Font | Label Font | Border Radius |
|------|--------|-----------|------|-----------|---------------|
| Small | 32px | 10px | 14px | 12px | 4px |
| Medium | 40px | 12px | 14-16px | 12-14px | 6px |
| Large | 48px | 16px | 16px | 14px | 8px |

## FORM FIELD TYPES & RULES

### Text Input
- Single line for short content (name, email, phone)
- Placeholder text disappears on focus -- always pair with visible label above
- Maximum width: match expected content length (email wider than zip code)

### Textarea
- Multi-line for longer content (message, description)
- Show character count for limited fields: "0/500 characters"
- Resizable handle at bottom-right (vertical only preferred)
- Min-height: 80-120px (3-5 lines visible)

### Select / Dropdown
- Chevron icon right-aligned indicates expandability
- Selected value replaces placeholder text
- Dropdown list: max 7-8 visible items, then scroll
- Search within dropdown for lists 10+ items

### Checkbox
- 18-20px square with 2px border radius
- Checked: filled with primary color + white checkmark
- Indeterminate: dash icon (for "select all" with partial selection)
- Label right of checkbox, vertically centered
- Gap: 8-12px between checkbox and label

### Radio Button
- 18-20px circle
- Selected: outer circle + inner filled circle (primary color)
- Only one selectable within a group
- Vertical list preferred for 3+ options
- Gap: 8-12px between radio and label

### Toggle / Switch
- Track: 36-44px wide, 20-24px tall, pill shape
- Thumb: 16-20px circle
- On state: track fills primary color, thumb slides right
- Off state: track is gray, thumb is left
- Label to the left or right of toggle

### Date Picker
- Input field triggers calendar overlay
- Calendar: 7-column grid (days of week)
- Highlight today, selected date, date range
- Navigation: month/year arrows in header

## FORM LAYOUT PATTERNS

### Single Column (Default)
- Stack fields vertically, full width
- Gap between fields: 16-24px
- Best for most forms -- creates clear top-to-bottom flow

### Two Column
- Related short fields side by side (first name + last name, city + state)
- Gap between columns: 16-24px
- Collapse to single column on mobile

### Inline Label
- Label left, input right on same row
- Only for very short forms or settings pages
- Label width: fixed (e.g., 120px), input: fill remaining

### Sectioned Form
- Group related fields under section headings
- Divider line between sections
- Section heading: 16-18px, semi-bold, 24px margin-top
- Aligns with Gestalt proximity -- related fields close, unrelated separated

## VALIDATION PATTERNS

### When to Validate
| Trigger | Best For | Example |
|---------|----------|---------|
| On blur (leave field) | Required fields, format | Email format check |
| On input (real-time) | Character limits, strength | Password strength meter |
| On submit | Cross-field dependencies | "Passwords must match" |

### Error Message Rules
- Position: immediately below the field, 4px gap
- Color: red (#EF4444 or similar), 12px font
- Content: specific and actionable
- Good: "Email must include @ and a domain (e.g., name@example.com)"
- Bad: "Invalid input"
- Bad: "Error"

### Success Indicators
- Green checkmark icon inside field (right-aligned)
- Brief green text: "Looks good!" (optional, can be noisy)
- Remove error state immediately when corrected

---

## DIALOG / MODAL PATTERNS

### Modal Sizing
| Type | Width | Max Height | Use Case |
|------|-------|-----------|----------|
| Alert/Confirm | 400-480px | auto | Simple yes/no decisions |
| Standard Modal | 500-640px | 80vh | Forms, content, settings |
| Large Modal | 720-900px | 80vh | Complex workflows, tables |
| Full Screen | 100vw | 100vh | Multi-step wizards, mobile |

### Modal Anatomy
```
┌─────────────────────────────────────┐
│ [X]  Modal Title                    │ ← 20-24px padding, 18px semi-bold
├─────────────────────────────────────┤
│                                     │
│  Modal content area                 │ ← 20-24px padding, scrollable
│                                     │
├─────────────────────────────────────┤
│              [Cancel]  [Confirm]    │ ← 16-20px padding, buttons right
└─────────────────────────────────────┘
```

### Backdrop
- Color: rgba(0, 0, 0, 0.5) -- semi-transparent black
- Click-to-dismiss: yes for non-critical modals, no for destructive confirmations
- Animation: fade in 200-300ms on open, fade out 200ms on close

### Dialog Button Rules
- Primary action (confirm/submit): right-most position, filled button
- Secondary action (cancel/dismiss): left of primary, outlined or text button
- Destructive confirmation: "Delete" in red, "Cancel" in gray
- Never stack more than 2 buttons in a dialog footer

---

## TOAST / SNACKBAR PATTERNS

### Anatomy
```
┌──────────────────────────────────────────┐
│ [icon]  Message text here    [Action]    │
└──────────────────────────────────────────┘
```

### Rules
- Position: bottom-center (web) or bottom of screen (mobile)
- Auto-dismiss: 3-5 seconds
- Maximum one action button (user has no time for more) [Arash]
- Maximum one snackbar visible at a time
- Brief message: 1-2 short sentences maximum
- Padding: 12-16px vertical, 16-24px horizontal

### Snackbar Types
| Type | Icon | Color | Example |
|------|------|-------|---------|
| Success | Checkmark | Green accent | "Changes saved" |
| Error | X or ! | Red accent | "Failed to save. Try again." |
| Info | i | Blue accent | "New version available" |
| Warning | ! triangle | Yellow accent | "You're running low on storage" |

---

## TOOLTIP PATTERNS

- Trigger: hover (desktop) or long-press (mobile)
- Delay: 300-500ms before showing
- Position: above element by default, reposition if clipped by viewport
- Arrow: small triangle pointing to trigger element
- Background: dark (#1F2937) with white text, or inverted
- Padding: 8px vertical, 12px horizontal
- Font: 12-14px
- Max width: 200-280px
- Auto-dismiss: on mouse leave or after 3 seconds (mobile)
