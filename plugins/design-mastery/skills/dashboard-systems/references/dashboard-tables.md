# Data Tables in Dashboards

## Table Structure

```
┌─────────────────────────────────────────┐
│ User Name  Email         Status  Action │  Header (48px)
├─────────────────────────────────────────┤
│ Sarah Chen sarah@...     Active  [⋮]   │  Row (48px)
│ John Smith john@...      Inactive [⋮]  │
│ Jane Doe   jane@...      Active  [⋮]   │
│ Mike Lee   mike@...      Active  [⋮]   │
└─────────────────────────────────────────┘
```

**Sizing:**
- **Header height:** 48px
- **Row height:** 48px (can be 40-56px)
- **Header font:** 12-14px, semi-bold, gray background
- **Row font:** 14px, regular
- **Padding:** 12px vertical, 16px horizontal
- **Border:** 1px #E0E0E0 between rows (optional)

**Column Width:**
```
Name: 200px
Email: 250px
Status: 100px
Action: 60px
Total: 610px (on 1200px container)
```

## Table Features

**Sorting:** Column header with ↑↓ indicator
**Filtering:** Icon next to header or filter bar above
**Selection:** Checkbox column (60px wide)
**Pagination:** "Showing 1-10 of 247 items" + buttons
**Row actions:** Dropdown menu (⋮) or inline buttons

## Responsive Tables

**Desktop:** Full table, all columns visible

**Tablet:** Horizontal scroll or hide less important columns

**Mobile:** Card view or stacked rows
```
┌──────────────────┐
│ Name: Sarah      │
│ Email: sarah@... │
│ Status: Active   │
│ [Actions]        │
└──────────────────┘
```
