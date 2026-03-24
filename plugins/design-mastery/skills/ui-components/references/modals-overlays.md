# Modals, Dialogs, and Overlays

## Modal Dialog (Most Common)

### Anatomy

```
Backdrop (dark overlay)
  ↓
┌─────────────────────────────┐
│ Title (20-24px)       [✕]   │  Header
├─────────────────────────────┤
│                             │
│  Modal Content              │  Content Area
│  (Padding: 24px)            │  (Scrollable if tall)
│                             │
├─────────────────────────────┤
│             [Cancel] [Save] │  Action Buttons
└─────────────────────────────┘
```

### Sizing

| Element | Size | Notes |
|---------|------|-------|
| **Width (Desktop)** | 400-600px | Standard: 500px |
| **Width (Tablet)** | 80% of viewport | Min 300px, max 80% |
| **Width (Mobile)** | 90% of viewport | Min 280px |
| **Min height** | Content-dependent | Usually 200px minimum |
| **Max height** | 80% of viewport | Scrollable if exceeds |
| **Padding** | 24-32px | Consistent all sides |
| **Border radius** | 8-12px | Modern appearance |

### Backdrop (Dark Overlay)

**Styling:**
- **Color:** rgba(0, 0, 0, 0.5) (50% black)
- **Fullscreen:** Covers entire viewport
- **Position:** fixed, z-index: 100 (below modal, above content)
- **Interaction:** Click closes modal (optional, configurable)

**Animation:**
```
Closed → Opening:
  From: opacity 0
  To: opacity 1
  Duration: 200ms
  Easing: ease-out
```

### Title

**Styling:**
- **Size:** 20-24px, semi-bold
- **Color:** Dark gray or black
- **Margin:** Bottom 12px
- **Alignment:** Left-aligned (or centered for critical actions)
- **Content:** Short, clear action-oriented: "Confirm Delete", "Edit Profile", "Share Post"

### Content Area

**Structure:**
- **Padding:** 24px (or 32px for breathing room)
- **Text:** 14-16px, regular weight
- **Line height:** 150% (readable paragraphs)
- **Max text width:** Keep under 600px even if modal is wider
- **Scrolling:** If content exceeds max-height (80vh), add vertical scroll
- **Scroll styling:** Use custom scrollbar or native (depends on browser)

### Close Button (X)

**Placement:**
- **Position:** Top-right corner of modal
- **Icon:** Simple X (24px × 24px)
- **Container:** 40×40px (touch target)
- **Padding:** 8px around icon
- **Color:** Dark gray or primary color

**Behavior:**
- **Click:** Closes modal
- **Keyboard (Escape):** Also closes modal
- **Always present:** Except on critical actions (data loss warning)

**States:**
- **Default:** Gray X
- **Hover:** Darker color or slight background
- **Focus:** 3px outline (accessibility)

### Action Buttons

**Positioning:**
```
┌────────────────┐
│ Modal content  │
│                │
└────────────────┘
    [Cancel] [Save]
```

**Button Arrangement:**
- **Primary action (right):** "Save", "Confirm", "Delete"
- **Secondary action (left):** "Cancel", "Back", "Close"
- **Gap:** 12px between buttons
- **Height:** 44-48px (same as form buttons)

**Button Styling:**
- **Primary:** Full solid color button
- **Secondary:** Outlined or gray button
- **Width:** Auto (not full-width in desktop modals), full-width on mobile

**Mobile Adjustment:**
```
On mobile, stack buttons vertically:
├─ [Full-width Save button]
├─ 12px gap
└─ [Full-width Cancel button]
```

### Animations

**Modal Entrance:**
```
Backdrop:
  From: opacity 0
  To: opacity 1
  Duration: 200ms

Modal:
  From: scale(0.9) + opacity 0
  To: scale(1) + opacity 1
  Duration: 300ms
  Easing: cubic-bezier(0.25, 0.46, 0.45, 0.94)
```

**Modal Exit:**
```
Backdrop:
  From: opacity 1
  To: opacity 0
  Duration: 150ms

Modal:
  From: scale(1)
  To: scale(0.95)
  Duration: 200ms
  Easing: ease-in
```

---

## Confirmation Dialog (Destructive Action)

### Purpose

Prevent accidental deletion or critical actions.

### Structure

```
⚠ Delete Account?
┌──────────────────────────────┐
│ This action cannot be undone │
│                              │
│ Your account and all data    │
│ will be permanently deleted. │
└──────────────────────────────┘
       [Keep Account] [Delete]
```

### Styling Differences

**Icon:** Warning icon (⚠) in orange or red
**Title:** Red color (destructive action)
**Text:** Clear, explicit consequences
**Primary button:** Red background (destructive), white text
**Secondary button:** Gray or outlined (safe option on left)

**Primary Destructive Button:**
- **Background:** Red (#CC0000 or brand danger color)
- **Text:** White
- **Hover:** Darker red
- **Confirmation required:** May require double-click or holding

---

## Alert Dialog

### Purpose

Inform user of important information (error, success, warning).

### Structure

```
┌──────────────────────────┐
│ ✓ Success                │  Title with icon
├──────────────────────────┤
│ Your profile has been    │
│ updated successfully.    │  Message
├──────────────────────────┤
│            [Dismiss]     │  Single button
└──────────────────────────┘
```

### Types

| Type | Icon | Color | Use Case |
|------|------|-------|----------|
| **Success** | ✓ | Green | Action completed |
| **Error** | ✗ | Red | Something failed |
| **Warning** | ⚠ | Orange | Important notice |
| **Info** | ℹ | Blue | General information |

**Icon Sizing:**
- Size: 40-48px
- Positioning: Left or top of message
- Color: Matches type (green, red, orange, blue)

---

## Tooltip / Popover

### Tooltip (Text Only)

**Trigger:** Hover over element (desktop), tap (mobile)

**Structure:**
```
[Element] → On hover →  ┌──────────────────┐
                        │ Tooltip text     │
                        │ (12-14px, white) │
                        └──────────────────┘
```

**Styling:**
- **Background:** Dark gray or black (#333 or #1a1a1a)
- **Text:** White or light color
- **Font:** 12-14px, regular
- **Padding:** 8px 12px
- **Border radius:** 4px
- **Shadow:** 0 2px 8px rgba(0,0,0,0.2)
- **Arrow/pointer:** Small triangle pointing to trigger (optional)

**Positioning:**
- **Default:** Above element (top)
- **Fallback:** Below if not enough space
- **Offset:** 8px from trigger element
- **Alignment:** Center-aligned to trigger

**Animation:**
```
Entrance: Fade-in 200ms
Exit: Fade-out 100ms (faster)
Delay: 500ms before showing (prevent accidental display)
```

**Do NOT use for:**
- Critical information (can be missed)
- Long-form explanations (use help text instead)
- Essential UI instructions (should be visible)

### Popover (Rich Content)

**Trigger:** Click on element

**Structure:**
```
┌─────────────────────────┐
│ Title (14px)            │
├─────────────────────────┤
│ Richer content here,    │
│ could include links,    │  More content than tooltip
│ lists, or images        │
│                         │
│ [Action Button]         │  Optional button
└─────────────────────────┘
  ↓ (pointer to trigger)
```

**Sizing:**
- **Width:** 200-300px
- **Max height:** 400px (scrollable if needed)
- **Padding:** 16px

**Styling:**
- **Background:** White
- **Border:** 1px #CCCCCC
- **Shadow:** 0 4px 12px rgba(0,0,0,0.15)
- **Border radius:** 8px
- **Arrow:** Solid triangle (12px × 12px) pointing to trigger

**Positioning:**
- **Preferred:** Right or below trigger
- **Avoid overlap:** Check viewport and reposition if needed
- **Arrow offset:** Points directly at trigger element

**Close Behavior:**
- Click outside: Closes popover
- Escape key: Closes popover
- Click button: Closes (or triggers action)
- Click trigger again: Toggles open/closed

---

## Notification Toast (Non-modal)

**Purpose:** Brief, non-blocking notifications.

### Structure

```
Success message notification  [✕]
(dismissible, auto-hides after 3-5 seconds)
```

**Positioning:**
- **Desktop:** Bottom-right corner, 16-20px from edges
- **Mobile:** Full-width, bottom of screen (above nav)
- **Z-index:** Highest (above all modals)

**Styling:**
```
Background: Green for success, red for error, blue for info
Text: 14px white or light color
Padding: 16px 20px
Border radius: 4-8px
Shadow: 0 2px 8px rgba(0,0,0,0.2)
Dismiss icon: [✕] right side (optional)
```

**Animation:**
```
Slide-up entrance: translateY(100%) → translateY(0)
Duration: 300ms

Auto-hide (5 seconds):
Then fade-out and slide-down
Duration: 200ms
```

**Multiple Notifications:**
```
┌─────────────────────┐
│ First notification  │  Stack vertically
├─────────────────────┤  Newest at bottom
│ Second notification │  12px gap between
└─────────────────────┘
```

---

## Sheet / Slide-up Panel (Mobile)

**Common on Mobile, Replaces Modal**

### Structure

```
Mobile screen
├─────────────────────┐
│ Existing content    │  Dims when sheet open
│ (dims)              │
├─────────────────────┤
┌──────────────────────┐
│ ─────────────────── │  Drag handle
│ Sheet Title (20px)  │  Half-screen by default
│ [✕] Close           │  Expands to ~90% on scroll
│                      │  Swipe-down to close
│ Sheet content...    │
│                      │
│                      │
│ [Action buttons]    │
└──────────────────────┘
```

### Sizing

**Initial state:** 50% of screen height
**Max expanded:** 80-90% of screen height
**Min height:** 200px

### Gestures

- **Swipe down:** Close sheet
- **Drag handle:** Same as swipe down
- **Tap outside:** Close (optional)
- **Scroll content:** Scroll sheet up (not the page behind)

### Animations

```
Slide-up: translateY(100%) → translateY(0)
Duration: 300ms
Easing: cubic-bezier(0.25, 0.46, 0.45, 0.94)

Close (slide-down):
translateY(0) → translateY(100%)
Duration: 250ms
```

---

## Modal Best Practices

### When to Use Modal

✓ Use when:
- Action requires immediate attention
- Confirmation needed (deletion, large purchases)
- Form input required
- Breaking focus is justified

❌ Don't use for:
- Navigation (use pages instead)
- Optional information (use popover)
- Blocking important content unnecessarily
- Non-critical messages (use toast notification)

### Accessibility Requirements

- [ ] Modal has role="dialog"
- [ ] Modal title has id and modal has aria-labelledby
- [ ] Focus trapped in modal (Tab loops within)
- [ ] Focus returned to trigger on close
- [ ] Escape key closes modal
- [ ] Close button always present
- [ ] Backdrop: Click outside closes (standard expectation)
- [ ] All form fields focusable and labeled
- [ ] Keyboard navigation works (Tab, Shift+Tab)
- [ ] Focus ring visible (3px outline)
- [ ] No color-only states (icon + color for error)

### Responsive Behavior

**Desktop:**
- Centered modal
- Max 600px width
- 20px margins minimum

**Tablet:**
- 80% of viewport width
- Centered or slight offset
- 16px margins

**Mobile:**
- Full-screen or 90% width
- Bottom-aligned (like sheet)
- Swipe-down to close support
- Consider converting to sheet for content-heavy modals

---

## Modal Anti-Patterns

### ❌ Modal on Modal

```
❌ WRONG: Modal opens another modal
           (Confusing stacking, hard to close)
```

**Fix:** Redesign flow to avoid nested modals.

### ❌ Non-dismissible Modal (Trap User)

```
❌ WRONG: No close button, only action buttons
           (User can't cancel without action)
```

**Fix:** Always include cancel button or close icon.

### ❌ Auto-closing Modal

```
❌ WRONG: Modal disappears after 3 seconds
           (User might miss it or not finish reading)
```

**Fix:** Keep modal visible until user acts or clicks close.

### ❌ Too Much Content

```
❌ WRONG: Modal is 50% of screen height
           with no scrolling solution
```

**Fix:** Limit modal content, use scroll if needed, or use sheet for mobile.

