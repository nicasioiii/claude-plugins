# Form Inputs — Fields, States, and Validation

## Text Input Field (Single Line)

### Structure & Measurements

```
Label Text (12px gray, always visible)
┌──────────────────────────────────┐
│ Placeholder or entered text 14px │  Height: 44-48px
└──────────────────────────────────┘
Helper text or error message (12px)
```

**Sizing Specification:**
- **Height:** 44px (mobile accessible), 48px (preferred)
- **Padding:** 12px horizontal, 10px vertical (centered text)
- **Border:** 1px solid #CCCCCC
- **Border radius:** 4-8px
- **Font:** 14-16px, regular weight
- **Line height:** 1.4 (matches container height)
- **Max width:** 400px (prevent super-wide inputs)

### Field States

| State | Border | Background | Text Color | Notes |
|-------|--------|-----------|-----------|-------|
| **Default** | #CCCCCC (1px) | White | #333 | Empty or placeholder |
| **Focus** | #0066CC (2px) | #F9FBFF (faint blue) | #333 | Active input |
| **Filled** | #CCCCCC (1px) | White | #333 | User entered text |
| **Hover** | #999999 (1px) | White | #333 | Mouse over (desktop) |
| **Error** | #CC0000 (2px) | #FFF5F5 (faint red) | #333 | Validation failed |
| **Disabled** | #E6E6E6 (1px) | #F5F5F5 | #999 | cursor: not-allowed |
| **Success** | #00AA00 (2px) | #F5FFF5 (faint green) | #333 | Validation passed |

### Label Accessibility

**REQUIRED - Never use placeholder as label:**

```html
<!-- ✓ CORRECT -->
<label for="email">Email Address</label>
<input id="email" type="email" placeholder="you@example.com">

<!-- ✗ WRONG -->
<input placeholder="Email Address">
```

**Label Styling:**
- Size: 12-14px
- Weight: Regular (400)
- Color: #666 or primary dark gray
- Margin below: 4-8px
- Position: Above input (never inside)
- Bold: Use `<strong>` for required field indicator

**Required Field Indicator:**
```
Email Address *          (asterisk)
or
Email Address (required) (text indicator)
```

### Placeholder Text

**Purpose:** Provide format hints, not the label

```
✓ CORRECT placeholders:
- "name@example.com"
- "Enter your full name"
- "mm/dd/yyyy"

✗ WRONG placeholders:
- "Email" (that's the label)
- Empty placeholder (no guidance)
```

**Styling:**
- Color: #999 (lighter gray, lower contrast)
- Disappears when user types
- Never rely on it as the only instruction

### Helper Text

**Purpose:** Additional guidance or validation status

**Placement:** Below input, left-aligned

**Types:**

1. **Helper Text (Neutral):**
   ```
   Email Address
   ┌──────────────┐
   │              │
   └──────────────┘
   Must include @ symbol
   ```
   - Font: 12px, gray (#666)
   - Display: Always visible

2. **Error Message (Red):**
   ```
   Password
   ┌──────────────┐
   │              │
   └──────────────┘
   ✗ Password too short (minimum 8 characters)
   ```
   - Font: 12px, bold, red (#CC0000)
   - Icon: Red X or exclamation mark
   - Display: Only on validation failure

3. **Success Message (Green):**
   ```
   Username
   ┌──────────────┐
   │              │
   └──────────────┘
   ✓ Username available
   ```
   - Font: 12px, green (#00AA00)
   - Icon: Green checkmark
   - Display: After validation succeeds

---

## Textarea (Multi-line)

### Structure

```
Message
┌─────────────────────┐
│ Enter your message. │  Resizable
│ Placeholder text    │  Min height: 120px
│                     │
│                     │
└─────────────────────┘
Character count (optional): 0 / 500
```

**Sizing:**
- **Min height:** 120px (allows ~3 lines)
- **Max height:** 300px (scrollable after)
- **Padding:** 12px
- **Border:** 1px solid #CCCCCC (same as text input)
- **Resize:** Vertical resize handle bottom-right (or disable: resize: none)

**Character Counter (Optional):**
```
Position: Below textarea, right-aligned
Format: "0 / 500" or "500 characters remaining"
Font: 12px, gray (#666)
Warning: Red text at 90% capacity
```

---

## Checkbox

### Structure

```
☑ Label text (14px)
```

**Sizing:**
- **Box:** 20×20px (fits 8px grid)
- **Border:** 2px solid
- **Padding/Gap to label:** 8-12px

### States

| State | Background | Border | Icon | Notes |
|-------|-----------|--------|------|-------|
| **Unchecked** | White | #999 (2px) | None | Default |
| **Checked** | #0066CC | #0066CC | ✓ white | Selected |
| **Hover** | #F0F0F0 | #666 | (varies) | Visual feedback |
| **Focus** | White | #0066CC | (varies) | Outline 2px offset |
| **Disabled** | #F5F5F5 | #CCCCCC | ✓ gray | cursor: not-allowed |

**Checkmark Styling:**
- Color: White (on checked state)
- Thickness: 2px stroke
- Style: Modern check mark (not X, not filled)

### Label Accessibility

```html
<label>
  <input type="checkbox">
  Label text
</label>

<!-- OR -->

<input id="terms" type="checkbox">
<label for="terms">I agree to terms</label>
```

---

## Radio Button

### Structure

```
◯ Option 1
◯ Option 2
◯ Option 3 (selected: ◉)
```

**Sizing:**
- **Circle:** 20×20px
- **Border:** 2px solid
- **Inner dot (selected):** 10×10px circle, centered
- **Gap to label:** 12px

### States

| State | Background | Border | Dot | Notes |
|-------|-----------|--------|-----|-------|
| **Unchecked** | White | #999 | None | Default |
| **Checked** | White | #0066CC (2px) | #0066CC (10px) | Selected |
| **Hover** | #F0F0F0 | #666 | (varies) | Visual feedback |
| **Focus** | White | #0066CC | (outline) | 2px offset outline |
| **Disabled** | #F5F5F5 | #CCCCCC | #999 | cursor: not-allowed |

**Grouping Radio Buttons:**

```
Which color do you prefer?
◉ Red
◯ Blue
◯ Green
```

- Legend: "Which color do you prefer?"
- Vertical stacking: 16px gap between each option
- Horizontal stacking (if 2-3 options): 24px gap, inline

---

## Select Dropdown

### Closed State

```
Select an option            ▼
┌──────────────────────────────┐
│                              │  Height: 44-48px
└──────────────────────────────┘
```

**Sizing:**
- **Height:** 44-48px (matches text input)
- **Padding:** 12px horizontal
- **Arrow icon:** 16-20px, right-aligned, 12px from right edge
- **Border:** 1px #CCCCCC (focus: 2px primary)
- **Border radius:** 4-8px (match text input)

### Open State

```
Select an option            ▲
┌──────────────────────────────┐
│ Option 1                     │  40px height per item
│ Option 2 (hover highlight)   │
│ Option 3                     │
│ Option 4                     │
│ Option 5                     │
└──────────────────────────────┘
```

**Dropdown Menu Styling:**
- **Background:** White
- **Border:** 1px #CCCCCC
- **Shadow:** 0 2px 8px rgba(0,0,0,0.12)
- **Item height:** 40px
- **Item padding:** 12px horizontal, 8px vertical
- **Hover background:** #F5F5F5 (5% darker)
- **Selected item:** Bold or primary color
- **Max-height:** 240px (5.5 items), then scrollable

### States

| State | Background | Border | Notes |
|-------|-----------|--------|-------|
| **Default** | White | #CCCCCC | Closed, placeholder shown |
| **Open** | White | #CCCCCC | Menu expanded |
| **Focus** | White | #0066CC (2px) | Keyboard navigation |
| **Hover (item)** | #F5F5F5 | None | Hover over option |
| **Selected** | White | #CCCCCC | Option selected, closes |
| **Disabled** | #F5F5F5 | #E6E6E6 | cursor: not-allowed |

**Arrow Icon Rotation:**
- **Closed:** 0° (pointing down)
- **Open:** 180° (pointing up)
- **Rotation time:** 200ms

---

## Date Input

### Options

**1. Native HTML Date Input (Recommended):**
```html
<label for="date">Start Date</label>
<input id="date" type="date">
```

**2. Text Input with Format Guide:**
```
Start Date
┌────────────────────┐
│ MM / DD / YYYY     │  Placeholder with format
│ 03 / 12 / 2026     │  Auto-formatting on input
└────────────────────┘
```

**3. Date Picker (Custom Component):**
```
Start Date
┌────────────────────────┐
│ 03/12/2026        [📅] │  Calendar icon triggers picker
└────────────────────────┘

  ← March 2026 →
  Su Mo Tu We Th Fr Sa
           1  2  3  4
   5  6  7  8  9 10 11
  12 13 14 15 16 17 18
  ...
```

**Preferred Pattern:** Native HTML date input (browser handles formatting and validation)

**Fallback:** Text input with auto-formatting + calendar icon

---

## Validation & Error States

### Real-time vs. On-Submit Validation

**Real-time (Recommended):**
```
User types in field
  ↓
Field validates as user types
  ↓
Shows green checkmark when valid
  ↓
Shows red error if invalid
```

**On-Submit:**
```
User fills out entire form
  ↓
User clicks Submit
  ↓
Form validates all fields
  ↓
Shows errors for invalid fields
  ↓
User corrects, resubmits
```

### Error Message Design

**Content:**
- Specific: "Email must include @ symbol" (not "Invalid email")
- Actionable: Tell user what to do
- Concise: 1-2 sentences max
- Friendly tone: Avoid blame ("You entered wrong..."), avoid technical jargon

**Styling:**
- Color: Red (#CC0000), 4.5:1 contrast
- Size: 12px
- Weight: Regular or semi-bold
- Icon: Red exclamation mark or X (optional)
- Position: Below input or in-field
- Visible: Always show when field is invalid

**Example:**

```
❌ Password
┌──────────────┐
│              │
└──────────────┘
✗ Password too short (minimum 8 characters)
```

### Required Field Indicators

**Preferred Method: Asterisk + Text**

```
Email Address *
(or mark as "required" in smaller text)
```

**Styling Asterisk:**
- Color: Red (#CC0000)
- Size: Same as label (12-14px)
- Position: After label text
- Include explanation: "* Required fields"

---

## Form Layout Patterns

### Single Column (Most Common)

```
Email
┌─────────┐
│         │
└─────────┘
Password
┌─────────┐
│         │
└─────────┘
Name
┌─────────┐
│         │
└─────────┘
```

- Spacing between fields: 20-24px
- Input width: 100% (or max 400px)
- Mobile: Always single column

### Two Column

```
First Name          Last Name
┌─────────┐        ┌─────────┐
│         │        │         │
└─────────┘        └─────────┘
Email
┌──────────────────┐
│                  │
└──────────────────┘
```

**Rules:**
- Desktop only (1440px+)
- Column gap: 24px
- Tablet/mobile: Switch to single column
- Always make responsive: Use CSS `grid-template-columns` that adapts

### Inline (Rarely Used)

```
[Email Field]  [Subscribe Button]
```

- Use only for simple cases (email + subscribe)
- Button height matches input (44-48px)
- Gap: 8px between input and button

---

## Form Accessibility Checklist

- [ ] All labels have associated `<label>` with `for` attribute
- [ ] Required fields marked with * and explained
- [ ] Error messages linked to inputs with `aria-describedby`
- [ ] Form has `<fieldset>` and `<legend>` for grouped fields
- [ ] Keyboard navigation works (Tab through fields in order)
- [ ] Focus ring visible (3px outline, high contrast)
- [ ] Color contrast: Text and labels 4.5:1
- [ ] Error text: Red color + icon (not color alone)
- [ ] Help text: `aria-describedby` points to helper element
- [ ] Touch targets: Buttons and inputs 44×44px minimum
- [ ] No automatic submission on field change
- [ ] Submit button label is specific: "Submit", "Send", "Save"

---

## Form Anti-Patterns

### ❌ Placeholder as Label

```
❌ WRONG: No label, only placeholder
┌──────────────────┐
│ Enter email...   │
└──────────────────┘
```

**Fix:** Always include visible label above input.

### ❌ Error on Blur (Too Aggressive)

```
❌ WRONG: Error shows as soon as user leaves field
         (Interrupts typing, frustrating)
```

**Fix:** Show error after 2-3 seconds of inactivity, or on submit.

### ❌ No Error Indication

```
❌ WRONG: Field turns red but no text explanation
         (Colorblind users miss the error)
```

**Fix:** Show error message + red color + icon.

### ❌ Multi-page Form with No Progress

```
❌ WRONG: User doesn't know what step they're on
         (How many more pages? Can I go back?)
```

**Fix:** Show progress indicator (step 1 of 3) + ability to navigate back.

