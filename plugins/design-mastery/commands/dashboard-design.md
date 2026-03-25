---
name: Dashboard Design
description: Design a SaaS dashboard or app interface with data tables, metrics, navigation, and UX law application. Covers high-density layouts and information hierarchy.
skill: dashboard-app-design
---

# /dashboard-design

You are helping the user design a dashboard or app interface. Follow this workflow:

## Step 1: Understand the Application

Ask the user:
1. **What type of app?** (analytics dashboard, admin panel, CRM, project management, settings)
2. **What are the key user tasks?** (monitoring data, managing records, configuring settings)
3. **What data needs to be displayed?** (metrics, tables, charts, lists, timelines)
4. **Who are the users?** (power users, occasional users, mixed technical levels)
5. **What is the navigation depth?** (flat, 2-level, deep hierarchy)

## Step 2: Choose Navigation Pattern

Select the appropriate navigation structure:
- **Sidebar navigation:** Best for apps with 5-15 top-level sections (most common)
- **Top navigation:** Best for fewer sections or marketing-adjacent products
- **Navigation drawer:** Best for mobile-first or secondary navigation
- **Bottom tab bar:** Best for mobile apps with 3-5 key sections

Sidebar design rules:
- Width: 240-280px (expanded), 64-72px (collapsed)
- Active state: background highlight + bold text or accent color
- Group related items under collapsible sections
- Keep primary actions always visible

## Step 3: Design the Main Content Area

### Metric Cards / KPIs
- Display 3-5 key metrics at the top of the dashboard
- Each card: metric label, value, trend indicator (up/down/neutral), sparkline (optional)
- Use consistent card sizing within rows

### Data Tables
- Column headers: left-aligned text, right-aligned numbers
- Row height: 40-56px depending on density
- Hover state on rows for selection affordance
- Sort indicators on column headers
- Pagination or infinite scroll based on data volume

### Charts and Visualization
- Choose chart type based on data relationship (comparison, trend, distribution, composition)
- Keep chart height proportional: 200-400px for embedded charts
- Use consistent color coding across all charts
- Include labels, legends, and tooltips

## Step 4: Apply UX Laws

Key laws for dashboard design:
- **Hick's Law:** Reduce choices to speed decision-making (progressive disclosure)
- **Miller's Law:** Chunk information into groups of 5-9 items
- **Fitts's Law:** Important actions should be large and close to cursor
- **Jakob's Law:** Users expect your app to work like apps they already know

## Step 5: Handle Density

Dashboard interfaces are high-density by default:
- Component padding: 8-16px (smaller than marketing layouts)
- Element gaps: 4-12px
- Typography: 13-16px body, 12-13px metadata
- Use borders and subtle background changes to separate sections (not large whitespace)

## Step 6: Plan Responsive Behavior

- Desktop: full sidebar + content area with 2-3 columns
- Tablet: collapsible sidebar + content area with 1-2 columns
- Mobile: navigation drawer + single-column content + bottom actions

## Step 7: Recommend Next Steps

- If components need designing → recommend `/component-pattern`
- If design system is needed → recommend `/design-system`
- If ready for review → recommend `/design-audit`

## Skills Activated

- **dashboard-app-design** (primary)
- Cross-references: ui-components, design-systems, layout-spacing
