# Table Design — Columns, Sorting, Filtering, and Responsive Tables

## Standard Data Table Structure

### Table Anatomy

```
┌────────────────────────────────────────────────┐
│ Name       Email            Role    Actions    │  Header (48px)
├────────────────────────────────────────────────┤
│ Sarah Chen sarah@email.com  Admin   [⋮]      │  Row (48px)
│ John Smith john@email.com   Editor  [⋮]      │
│ Jane Doe   jane@email.com   Viewer  [⋮]      │
│ Mike Lee   mike@email.com   Admin   [⋮]      │
├────────────────────────────────────────────────┤
│ Showing 1–4 of 247 items                      │  Footer
└────────────────────────────────────────────────┘
```

**Sizing:**
- Header height: 48px (darker background, bold text)
- Row height: 48px (comfortable scanning)
- Padding: 12px vertical, 16px horizontal
- Border: 1px #E0E0E0 between rows (optional)
- Font: Headers 12px semi-bold gray, rows 14px regular

### Column Width Guidelines

| Column Type | Width | Example |
|------------|-------|---------|
| **Name/Text** | 150-200px | "Sarah Chen", "sarah@email" |
| **Email** | 200-250px | "sarah@example.com" |
| **Status/Badge** | 100px | "Active", "Pending" |
| **Number/Date** | 120px | "247", "Mar 12, 2026" |
| **Actions** | 60px | [⋮] menu or buttons |

**Total Table Width:** Sum of columns + gutters
For 1200px container: 200 + 250 + 100 + 120 + 60 = 730px (can fit)

## Column Features

### Sortable Columns

**Indicator:**
```
Name ▲    (ascending, currently sorted)
Email     (neutral, not sorted)
Role ▼    (descending)
```

**Icon:** 12-16px arrow, right of header text, gray until active (then brand color)

**Click behavior:**
1. First click: Sort ascending (↑)
2. Second click: Sort descending (↓)
3. Third click: Remove sort (neutral)

**Visual feedback:**
- Column header text darkens on hover
- Cursor: pointer
- Background: Optional light shade on hover

### Filterable Columns

**Filter Icon** (optional, right side of header):
```
Name [🔍]    Click to filter by name
Status [🔍]  Opens dropdown with options
```

**Filter Dropdown:**
```
☑ Active
☐ Inactive
☐ Pending

[Apply] [Clear]
```

Options: Checkboxes for multiple selection
Position: Below column header, left-aligned with column
Max-height: 200px scrollable

### Searchable Table

**Search bar above table:**
```
[🔍 Search users...]
Filters rows in real-time
```

**Styling:** Match form input styling (see ui-components form-inputs)
**Width:** 300px or full width depending on layout

## Row Features

### Selectable Rows (Checkbox Column)

**Structure:**
```
┌─┬──────────────────────┐
│☑│ Name    Email   Role │  Header checkbox: select all
├─┼──────────────────────┤
│☑│ Sarah   s@...   Admin│  Selected row: light background
│ │ John    j@...   Edit │  Unselected row: default
└─┴──────────────────────┘
```

**Checkbox:**
- Size: 20×20px
- Column width: 60px total (20px checkbox + padding)
- Header checkbox: Select/deselect all rows
- Checked row: Optional background highlight (#F0F0FF or brand color, 10% opacity)

**Bulk actions:**
When rows selected, show action bar:
```
3 items selected [Delete] [Archive] [Change Role ▼]
```

### Row Hover State

**Default row:**
- Background: White
- Border: 1px #E0E0E0

**On hover:**
- Background: #FAFAFA (1-2% darker)
- Shadow: Optional, subtle (no change needed)
- Cursor: pointer if row is clickable

### Row Click Actions

**Option 1: Expand row**
```
Click → Row expands to show more details
```

**Option 2: Navigate to detail page**
```
Click → Open user detail page
```

**Option 3: Actions menu (⋮)**
```
[⋮] → Dropdown with Edit, Delete, Archive, etc.
```

## Pagination & Navigation

### Pagination Bar (Below Table)

```
Showing 1–25 of 500 items
[← Prev] [1] [2] [3] [4] ... [19] [20] [Next →]
```

**Components:**

1. **Info Text:** "Showing X–Y of Z items"
   - Font: 12px gray
   - Left-aligned or right-aligned
   - Updates dynamically

2. **Page buttons:** [1] [2] [3] ...
   - Size: 36×36px square
   - Font: 14px
   - Active: Brand primary background, white text
   - Inactive: White background, gray border
   - Hover: Light background
   - Disabled (first/last): Grayed out

3. **Prev/Next buttons:**
   - Text: "← Prev", "Next →" OR
   - Icon: Arrow (16px)
   - Disabled on first/last page
   - Cursor: pointer when enabled

4. **Items per page dropdown (Optional):**
   ```
   Show: [25 ▼] items per page
   Options: 10, 25, 50, 100
   ```

### Infinite Scroll (Alternative)

**Instead of pagination:**
- Auto-load more rows as user scrolls to bottom
- No pagination buttons needed
- "Load more" button between pages (optional)

**Pro:** Smooth mobile experience
**Con:** Hard to jump to specific page, page position lost on back

## Responsive Table Design

### Desktop (1440px)

**Full table view:**
```
All columns visible
Horizontal scroll only if necessary
Normal row height (48px)
```

### Tablet (800px)

**Option 1: Horizontal Scroll**
```
Table scrolls left-right
Frozen first column (name) optional
```

**Option 2: Hide Less Important Columns**
```
Keep: Name, Status, Actions
Hide: Email, Description, Created Date
Show: [v] checkbox to reveal hidden columns
```

### Mobile (390px)

**Recommended: Card View**
```
┌──────────────────┐
│ Name: Sarah      │
│ Email: s@...     │
│ Role: Admin      │
│ Status: Active   │
│ [Actions]        │
├──────────────────┤
│ Name: John       │
│ Email: j@...     │
│ Role: Editor     │
│ Status: Pending  │
└──────────────────┘
```

**Styling:**
- Card: Full-width minus 16px margins
- Each row becomes a card
- Labels + values stacked
- Actions at bottom

**Alternative: Stacked Rows**
```
Name | Sarah Chen
Email | sarah@email.com
Role | Admin
---
Name | John Smith
...
```

## Table States

### Empty Table

```
┌─────────────────────┐
│ 📭 No items found  │
│                    │
│ Try different      │
│ search terms       │
│                    │
│ [Create item]      │
└─────────────────────┘
```

- Icon: 64px, light gray
- Message: 16px gray
- CTA button: Optional
- Padding: 60px vertical, 40px horizontal
- Height: At least 200px

### Loading Table

```
[████] [████████] [██]        (Skeleton rows)
[██████████] [████] [████]
[████] [██████] [████]
```

- Placeholder bars: #E6E6E6
- Shimmer: Left-to-right animation
- Repeat: 5-8 rows shown
- Duration: 1.5-2 seconds until load complete

### Error State

```
⚠️ Failed to load users

Something went wrong. Try again.

[Retry]  [Go Back]
```

- Icon: 48px orange/red
- Message: 14px gray
- Buttons: Retry (primary), Go Back (secondary)

## Table Accessibility

**Requirements:**
- Table semantic: Use `<table>` element
- Headers: `<th scope="col">` for each column
- Rows: `<tr>` elements
- Data: `<td>` for each cell
- Caption: `<caption>` for table title
- Keyboard navigation: Tab/arrow keys work
- Focus ring visible: 3px outline on all interactive elements
- Contrast: 4.5:1 for all text

**Aria attributes:**
- `aria-sort="ascending"` on sorted headers
- `aria-label="Delete user"` on action buttons
- `role="status"` on pagination updates

## Table Anti-Patterns

### ❌ Too Many Columns

```
15+ columns visible
(Impossible to read on most screens)
```

**Fix:** Show essential columns, hide others in menu, or use card view.

### ❌ Tiny Font

```
11px or smaller font
```

**Fix:** Minimum 14px for readability.

### ❌ No Row Separation

```
All rows blend together
(Can't distinguish rows)
```

**Fix:** Use border or alternating background colors.

### ❌ Non-sortable Columns

```
No indicator that columns are sortable
Users don't know they can sort
```

**Fix:** Show ↑↓ icon on hover or always.

### ❌ No Mobile Design

```
Same table on mobile
(Tiny, horizontal scroll nightmare)
```

**Fix:** Card view or stacked layout on mobile.

