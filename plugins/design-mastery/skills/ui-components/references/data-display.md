# Data Display — Tables, Lists, and Grids

## Data Table (Structured Information)

### Basic Table Structure

```
┌─────────────────────────────────────────────┐
│ Name        Email              Status       │  Header row
├─────────────────────────────────────────────┤
│ Sarah Chen  sarah@email.com   Active       │  Data row
│ John Smith  john@email.com    Inactive     │
│ Jane Doe    jane@email.com    Active       │
│ Mike Lee    mike@email.com    Active       │
│ Lisa Wang   lisa@email.com    Pending      │
└─────────────────────────────────────────────┘
```

### Sizing & Spacing

**Header Row:**
- **Height:** 48px (larger than data rows for distinction)
- **Font:** 12-14px, semi-bold, dark gray
- **Background:** Light gray (#F5F5F5) or subtle brand color
- **Padding:** 12px vertical, 16px horizontal
- **Text alignment:** Left-aligned (default), right for numbers

**Data Rows:**
- **Height:** 48-56px (comfortable for scanning)
- **Font:** 14px, regular weight
- **Background:** White (alternating row background optional)
- **Padding:** 12px vertical, 16px horizontal
- **Text color:** #333 (dark gray)

**Row Alternation (Optional):**
- **Even rows:** White (#FFFFFF)
- **Odd rows:** Very light gray (#FAFAFA)
- **Purpose:** Improves scanability for wide tables
- **Skip if:** Table has only 3-4 rows (too little data to benefit)

### Column Types & Alignment

| Column Type | Alignment | Content Example |
|-------------|-----------|-----------------|
| **Text/Name** | Left | "Sarah Chen" |
| **Email/URL** | Left | "sarah@email.com" |
| **Number/Currency** | Right | "12,345" or "$49.99" |
| **Percentage** | Right | "92.5%" |
| **Date** | Left or center | "Mar 12, 2026" |
| **Status/Badge** | Center | "Active" or "Pending" |

**Column Width:**
- Text columns: 200-300px minimum
- Number columns: 100-150px
- Icon columns: 60px
- Proportion: Adjust based on content importance

### Column Sorting (Interactive Tables)

**Indicator:**
```
Name       ▲  (ascending sort)
Email      ▼  (descending sort)
Status     -  (not sorted)
```

**Click Behavior:**
1. First click: Sort ascending (↑)
2. Second click: Sort descending (↓)
3. Third click: Remove sort (neutral)

**Icon Styling:**
- **Size:** 12-16px
- **Color:** Gray (#666), darker when active
- **Position:** Right-aligned in header, 8px from text
- **Cursor:** pointer on hover

**Hover State (Sortable Column):**
- **Text:** Underline or color change
- **Background:** 5% darker
- **Indicates:** Column is interactive

### Row Hover & Selection

**Row Hover State:**
```
┌─────────────────────────────────────────────┐
│ Name        Email              Status       │  (Header, no change)
├─────────────────────────────────────────────┤
│ Sarah Chen  sarah@email.com   Active       │  (Hover: light background)
│ John Smith  john@email.com    Inactive     │
│ Jane Doe    jane@email.com    Active       │
└─────────────────────────────────────────────┘
```

**Hover Background:** 2-5% darker shade of row color
**Hover effect:** Subtle, not distracting
**Cursor:** pointer (if row is clickable)

**Selectable Rows (Checkbox):**
```
┌─┬─────────────────────────────────────────┐
│☑│ Name        Email              Status   │  Checkbox column (60px)
├─┼─────────────────────────────────────────┤
│☑│ Sarah Chen  sarah@email.com   Active   │
│ │ John Smith  john@email.com    Inactive │  Unchecked row
│☑│ Jane Doe    jane@email.com    Active   │
└─┴─────────────────────────────────────────┘

Header checkbox: Select/deselect all rows
```

**Selected Row Styling:**
- **Background:** Light blue or brand color (10-20% opacity)
- **Border:** Optional left border (3px solid primary)
- **Checkbox:** Always checked visually

---

## Table Pagination

### Pagination Bar (Bottom of Table)

```
Showing 1–10 of 247 items
[← Prev]  [1]  [2]  [3]  [4]  [...]  [24]  [25]  [Next →]
```

**Components:**

1. **Info Text:** "Showing X–Y of Z items"
   - Font: 12px, gray
   - Left-aligned or right-aligned

2. **Page Buttons:**
   - Size: 36×36px (square buttons)
   - Font: 14px
   - Gap: 4px between buttons
   - Styling:
     - Default: White background, gray border
     - Active: Brand color background, white text
     - Hover: Light background shade
     - Disabled (first/last page): Grayed out

3. **Items Per Page Dropdown (Optional):**
   ```
   Show: [10 ▼] items per page
   ```
   - Dropdown: 10, 25, 50, 100
   - Updates table and pagination

4. **Navigation Buttons:**
   - **Prev/Next:** Show as text or icon
   - Disabled on first/last page
   - Icon (←, →): 16px

**Pagination Styles:**

```css
/* Prev button */
[← Prev] - Disabled when on page 1

/* Page buttons */
[1] [2] [3] [4] - Active (blue background)
               [5] [6] - Disabled: Grayed

/* Ellipsis */
[...] - Shows when many pages (3+ hidden pages)

/* Next button */
[Next →] - Disabled when on last page
```

---

## Sticky Table Header

**Behavior:** Header row stays visible when scrolling down

```
Scroll down
  ↓
┌─────────────────────────────────────┐
│ Name        Email        Status   │ ← STICKY (stays at top)
├─────────────────────────────────────┤
│ Item 50                             │
│ Item 51  (scrollable)               │
│ Item 52                             │
│ Item 53                             │
└─────────────────────────────────────┘
```

**CSS Implementation:**
```css
thead {
  position: sticky;
  top: 0;
  z-index: 10; /* Above rows */
  background-color: #F5F5F5; /* Don't fade */
}
```

**Shadow:** Add subtle bottom shadow to indicate stickiness
```css
box-shadow: 0 2px 4px rgba(0, 0, 0, 0.08);
```

---

## Responsive Table Design

### Desktop (1440px)

```
Full table with all columns visible
Horizontal scroll for very wide tables
```

### Tablet (800px)

**Option 1: Horizontal Scroll**
```
Table scrolls horizontally
User can scroll left/right to see columns
```

**Option 2: Hide Less Important Columns**
```
Keep: Name, Status, Actions
Hide: Email, Description, Metadata
Add: "..." menu to show hidden columns
```

### Mobile (390px)

**Option 1: Card View (Recommended)**
```
┌──────────────────┐
│ Name: Sarah      │
│ Email: s@...     │
│ Status: Active   │
│ [Actions menu]   │
└──────────────────┘

┌──────────────────┐
│ Name: John       │
│ Email: j@...     │
│ Status: Inactive │
│ [Actions menu]   │
└──────────────────┘
```

**Option 2: Stacked Rows**
```
[Name label]  Sarah Chen
[Email label] sarah@email.com
[Status label] Active
```

---

## Special Table Cases

### Table with Actions Column

```
Name        Email                Status    Actions
────────────────────────────────────────────────────
Sarah Chen  sarah@email.com      Active    ⋮ [Edit | Delete]
John Smith  john@email.com       Inactive  ⋮ [Edit | Delete]
```

**Actions Column:**
- Width: 60-80px
- Content: Icon menu (⋮) or action buttons
- Alignment: Center or right
- Icon menu: 3-dot vertical menu (hamburger for actions)

**Icon Menu Styling:**
- Icon: 20×20px, three dots vertical
- Color: Gray (#666), darker on hover
- Triggers dropdown with: "Edit", "Delete", "Archive", etc.

### Empty Table State

```
┌──────────────────────────────────────┐
│                                      │
│      📭 No data found                │
│                                      │
│  "There are no items to display."   │
│                                      │
│      [Create Item] or [Import]      │
│                                      │
└──────────────────────────────────────┘
```

**Styling:**
- Icon: Large (64px), light gray (#DDD)
- Message: 16px, gray (#666)
- Button: Optional CTA button
- Padding: 60px vertical, 40px horizontal

### Loading Table State (Skeleton)

```
┌──────────────────────────────────────┐
│ [████████] [████] [████]             │
├──────────────────────────────────────┤
│ [███████████] [███████] [█████]      │
│ [████████] [█████] [███]             │
│ [███████████] [██████] [██]          │
│ [████████] [████████] [███]          │
└──────────────────────────────────────┘
```

**Skeleton Styling:**
- Gray background: #E6E6E6
- Animated shimmer: Left-to-right movement
- 8-10 rows shown
- Width: Match actual content width

**Animation:**
```
Gradient shimmer: left-to-right
Duration: 1.5-2 seconds
Repeat: Continuous until loaded
```

---

## List Displays (Non-Table Data)

### Simple List

```
• Item 1
• Item 2
• Item 3
• Item 4
```

**Usage:** Bulleted lists for non-tabular data
**Styling:**
- Bullet: • or – or custom shape
- Font: 14px, regular
- Line height: 150%
- Gap: 12px between items

### Numbered List

```
1. First item
2. Second item
3. Third item
4. Fourth item
```

**Usage:** Ordered instructions or rankings
**Styling:** Same as bulleted, but with numbers

### Key-Value List

```
Name:        Sarah Chen
Email:       sarah@email.com
Company:     ACME Corp
Location:    San Francisco, CA
Phone:       (555) 123-4567
```

**Styling:**
- Label: 12-14px, bold or semi-bold, 25-30% width
- Value: 14px, regular, 70% width
- Row gap: 12px
- Border bottom: Optional 1px separator

---

## Data Grid (Card-based List)

### Grid Layout

```
┌──────────┬──────────┬──────────┐
│  Card 1  │  Card 2  │  Card 3  │
├──────────┼──────────┼──────────┤
│  Card 4  │  Card 5  │  Card 6  │
├──────────┼──────────┼──────────┤
│  Card 7  │  Card 8  │  Card 9  │
└──────────┴──────────┴──────────┘
```

**Columns by Breakpoint:**

| Breakpoint | Columns | Card Width | Gutter |
|-----------|---------|-----------|--------|
| **Desktop** (1440px) | 3-4 | 300-350px | 24px |
| **Tablet** (800px) | 2 | 280px | 20px |
| **Mobile** (390px) | 1-2 | Full width | 16px |

### Card as Data Container

```
┌─────────────────────┐
│ [Image/Thumbnail]   │
├─────────────────────┤
│ Name: Sarah         │  Key-value pairs
│ Status: Active      │  in card format
│ Email: s@...        │
├─────────────────────┤
│ [Edit] [Delete]     │  Action buttons
└─────────────────────┘
```

---

## Table Accessibility

- [ ] Table has `<table>` semantic element
- [ ] Header cells use `<th>` with scope="col"
- [ ] Row headers (if applicable) use scope="row"
- [ ] Column headers describe content
- [ ] Data cells use `<td>`
- [ ] Complex tables have `<caption>`
- [ ] Sortable columns have aria-sort attribute
- [ ] Pagination buttons are labeled
- [ ] Focus visible on all interactive elements
- [ ] Keyboard navigation works (Tab through, arrow keys in focusable areas)
- [ ] Color contrast: 4.5:1 for text
- [ ] Row selection: Checkbox with clear labels

**Caption Example:**
```html
<table>
  <caption>Q1 2026 Sales Report</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Revenue</th>
    </tr>
  </thead>
</table>
```

---

## Table Design Anti-Patterns

### ❌ Too Many Columns

```
❌ WRONG: 10+ columns visible
           (Impossible to read, overwhelming)
```

**Fix:** Hide less important columns, use horizontal scroll, or card view.

### ❌ Tiny Font Size

```
❌ WRONG: 11px or smaller font
           (Hard to read on screen)
```

**Fix:** Use 14px minimum for data rows.

### ❌ No Row Separation

```
❌ WRONG: Rows blend together
           (Can't tell where one row ends)
```

**Fix:** Add alternating row background or borders.

### ❌ Non-obvious Sortable Columns

```
❌ WRONG: No ▲▼ indicator
           (User doesn't know columns are sortable)
```

**Fix:** Show sort arrow/indicator + hover state.

### ❌ Poor Mobile Adaptation

```
❌ WRONG: Full desktop table on mobile
           (Tiny text, horizontal scroll nightmare)
```

**Fix:** Convert to card view or stacked layout on mobile.

