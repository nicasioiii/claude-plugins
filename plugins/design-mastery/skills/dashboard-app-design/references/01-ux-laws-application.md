# UX Laws Applied to Dashboard & App Design — Quick Reference

## HICK'S LAW — Decision Time Increases with Options

### Principle
Time to make a decision = logarithmic function of number of choices.
More options = slower decisions = higher abandonment.

### Dashboard Applications

**Navigation Design:**
| Scenario | Bad | Good |
|----------|-----|------|
| Main nav items | 15 flat items | 5-7 groups with sub-items |
| Filter panel | 20 visible filters | 4-5 key filters + "Advanced" expandable |
| Action buttons | 8 equal-weight actions | 1 primary + "More Actions" dropdown |
| Settings page | One long scrolling list | Tabbed/sectioned categories |

**Progressive Disclosure Pattern:**
```
Level 1: Summary view (metric cards, key numbers)
Level 2: Click to expand detail (charts, trends)
Level 3: Click to drill down (individual records, raw data)
```
Show only what's needed at each level. Don't show Level 3 detail on the dashboard summary.

**Pricing Page Application:**
- 3 tiers is standard (not coincidence -- Hick's Law) [Arash]
- Highlight "Most Popular" tier (Von Restorff to guide choice)
- Limit feature comparison to 8-12 rows

---

## FITTS'S LAW — Distance and Size Affect Speed

### Principle
Time to acquire target = function of distance to target + size of target.
Larger, closer targets are faster to select.

### Dashboard Applications

**Primary Action Placement:**
| Action | Position | Size |
|--------|----------|------|
| Save/Submit | Near the form it affects | Large (48px) |
| Create New | Top-right of relevant section | Medium-Large |
| Delete | Bottom or secondary position | Text/small (prevent accident) |
| Cancel | Adjacent to primary, smaller | Medium |

**Touch Optimization (Tablet Dashboards):**
- All interactive elements: minimum 44x44px touch area
- Table row actions: revealed on hover (desktop), persistent icon (tablet)
- Sidebar items: 44px minimum height
- Spacing between adjacent targets: minimum 8px to prevent mis-taps

**Edge and Corner Advantage:**
- Screen edges are infinitely tall targets (cursor stops at edge)
- Sidebar nav items touching the left edge are easier to hit
- Bottom tab bars touching the bottom edge are easier to hit
- Use this for the most frequent actions

---

## JAKOB'S LAW — Familiarity Breeds Usability

### Principle
Users spend most time on OTHER apps. They expect yours to work the same way.

### Established SaaS Conventions (Don't Reinvent)

**Layout Conventions:**
| Element | Expected Position | Breaking This = Confusion |
|---------|------------------|---------------------------|
| Main navigation | Left sidebar | Right sidebar, bottom, or hidden |
| Search | Top bar, center or right | Bottom of page, sidebar |
| Notifications | Top-right, bell icon | Left side, text only |
| User profile | Top-right corner | Bottom-left, hidden |
| Logo/Home | Top-left | Centered, bottom |
| Page title | Top-left of content area | Center, bottom |
| Primary CTA | Top-right of content area | Hidden in menu |
| Breadcrumbs | Below top bar, above content | Bottom of page |

**Interaction Conventions:**
| Interaction | Expected Behavior |
|-------------|-------------------|
| Click column header | Sort by that column |
| Click row | Navigate to detail view |
| Three-dot icon | Opens action menu |
| Gear icon | Opens settings |
| Red button | Destructive action (delete, cancel) |
| Blue link text | Navigation to another view |
| Checkbox + action bar | Bulk operations |
| Drag handle (≡) | Reorder items |

**Form Conventions:**
- Labels above input fields (not inside as placeholder-only)
- Required fields marked with asterisk or "(Required)"
- Error messages in red below the field
- Save button bottom-right of form
- Cancel button to left of Save

---

## MILLER'S LAW — Working Memory Limits

### Principle
People can hold 7 +/- 2 items in working memory.

### Dashboard Applications

**Information Chunking:**
- Group metrics into 3-4 themed cards (Revenue, Users, Performance, Support)
- Within each card group, limit to 3-4 key metrics
- Use visual separators (cards, dividers, headings) to chunk information
- Tables: paginate at 10-25 rows, not 100+

**[CONTRARIAN] Visible Navigation Exception [Arash]:**
Menu items are visible on screen -- users don't need to remember them.
Don't artificially limit sidebar navigation to 7 items.
Instead, group with section dividers and use clear labels.

**Dashboard Card Grouping:**
```
Revenue Section          Users Section           Performance Section
├── Total Revenue       ├── Active Users        ├── Uptime
├── MRR                 ├── New Sign-ups        ├── Response Time
├── Growth Rate         ├── Churn Rate          ├── Error Rate
└── [See Details →]     └── [See Details →]     └── [See Details →]
```

---

## GESTALT PRINCIPLES — Perceptual Organization

### Proximity
**Rule**: Elements placed close together are perceived as a group.

**Dashboard Application:**
- Metric label directly above or beside its value (4-8px gap)
- Related metrics in the same card (shared boundary)
- Form fields for the same topic grouped together (16px gap)
- Unrelated sections separated by larger gaps (32-48px)
- Table cells: horizontal padding groups cell content to its column

### Similarity
**Rule**: Elements sharing visual characteristics are perceived as related.

**Dashboard Application:**
- All metric cards: same height, same padding, same label style
- All status badges: same size, different colors for different states
- All CTAs: same button style across dashboard
- Consistent icon set: all outline OR all solid

### Common Region
**Rule**: Elements within a shared boundary are perceived as a group.

**Dashboard Application:**
- Cards with borders or backgrounds to contain related metrics
- Table rows as visual containers for record data
- Section backgrounds (alternating white/gray) to separate dashboard zones
- Modal dialogs to focus attention on a single task

### Figure-Ground
**Rule**: Users separate visual field into figure (focus) and ground (background).

**Dashboard Application:**
- Key data (figures) should contrast clearly with the dashboard chrome (ground)
- White cards on gray-100 background: cards are figure, background is ground
- Modal overlay: modal is figure, dimmed dashboard is ground
- Active sidebar item: highlighted item is figure, other items are ground

---

## VON RESTORFF EFFECT — Isolation Makes Memorable

### Principle
Items that visually stand out from their surroundings are noticed and remembered.

### Dashboard Applications

| Use Case | Technique |
|----------|-----------|
| Critical alert | Red badge, pulsing animation |
| Recommended plan | "Most Popular" badge, different card color |
| Key metric | Larger size, bold value, accent color |
| New feature | Dot indicator, "New" badge |
| Error state | Red border, warning icon |
| Empty state | Illustration + helpful message |

**Warning**: If everything is highlighted, nothing stands out. Use sparingly.
- Maximum 1-2 highlighted items per dashboard view
- Critical alerts should be the ONLY red elements on screen

---

## FOGG BEHAVIOR MODEL — Triggering User Action

### Principle
Behavior = Motivation x Ability x Prompt
All three must converge for action to occur.

### Dashboard Applications

**Increasing Ability (Reduce Friction):**
- Pre-fill form fields where data is known
- Inline editing instead of navigate-to-form
- One-click actions for common tasks (archive, mark complete)
- Auto-save instead of manual save
- Smart defaults on new records

**Well-Timed Prompts:**
- Contextual action buttons near relevant data
- Empty state CTAs: "No reports yet. [Create Report]"
- Tooltip guidance on first use
- Progress indicators: "3 of 5 steps complete"
- Notification badges drawing attention to pending items

**Maintaining Motivation:**
- Show impact: "You've completed 85% of tasks this week"
- Social proof: "12 team members already use this feature"
- Quick wins: start with easiest onboarding step
- Visual progress: completion bars, checkmark lists

---

## COGNITIVE LOAD QUICK REFERENCE

### Three Types of Cognitive Load
| Type | Definition | Dashboard Strategy |
|------|-----------|-------------------|
| Intrinsic | Complexity of the task itself | Simplify workflows, break into steps |
| Extraneous | Unnecessary complexity from design | Clean layout, consistent patterns |
| Germane | Effort toward understanding | Clear labels, helpful empty states |

### Reducing Extraneous Load
- Consistent visual patterns (same action = same button style)
- Predictable layout (same position = same type of content)
- Clear typography hierarchy (scan without reading)
- Adequate white space between groups (even in dense UIs)
- Progressive disclosure (show detail on demand)
