# Variables, Tokens & Handoff — Complete Reference

## VARIABLE TYPES

| Type | Stores | Example Name | Example Value |
|------|--------|-------------|---------------|
| Color | Hex color | blue-600 | #2563EB |
| Number | Integer/float | spacing-16 | 16 |
| String | Text | font-family-primary | "Inter" |
| Boolean | True/false | is-dark-mode | false |

---

## PRIMITIVE VARIABLE SETUP

### Color Primitives
Create collection "Primitives". Group colors by hue family.

```
color/
├── blue/
│   ├── blue-50     → #EFF6FF
│   ├── blue-100    → #DBEAFE
│   ├── blue-200    → #BFDBFE
│   ├── blue-300    → #93C5FD
│   ├── blue-400    → #60A5FA
│   ├── blue-500    → #3B82F6
│   ├── blue-600    → #2563EB
│   ├── blue-700    → #1D4ED8
│   ├── blue-800    → #1E40AF
│   └── blue-900    → #1E3A8A
├── gray/
│   ├── gray-50     → #F9FAFB
│   ├── gray-100    → #F3F4F6
│   ├── gray-200    → #E5E7EB
│   ├── gray-300    → #D1D5DB
│   ├── gray-400    → #9CA3AF
│   ├── gray-500    → #6B7280
│   ├── gray-600    → #4B5563
│   ├── gray-700    → #374151
│   ├── gray-800    → #1F2937
│   └── gray-900    → #111827
├── red/
│   └── (same 50-900 pattern)
├── green/
│   └── (same 50-900 pattern)
├── yellow/
│   └── (same 50-900 pattern)
└── base/
    ├── white       → #FFFFFF
    └── black       → #000000
```

### Spacing Primitives
```
spacing/
├── 0      → 0
├── 1      → 4
├── 2      → 8
├── 3      → 12
├── 4      → 16
├── 5      → 20
├── 6      → 24
├── 8      → 32
├── 10     → 40
├── 12     → 48
├── 16     → 64
├── 20     → 80
├── 24     → 96
└── 32     → 128
```

### Radius Primitives
```
radius/
├── none   → 0
├── sm     → 4
├── md     → 6
├── lg     → 8
├── xl     → 12
├── 2xl    → 16
└── full   → 9999 (pill shape)
```

---

## TOKEN VARIABLE SETUP

Create separate collection "Tokens". Every token is an ALIAS referencing a primitive.

### Surface Tokens (Backgrounds)
```
surface/
├── surface-primary         → alias: color/base/white
├── surface-secondary       → alias: color/gray/gray-50
├── surface-tertiary        → alias: color/gray/gray-100
├── surface-inverse         → alias: color/gray/gray-900
├── surface-brand           → alias: color/blue/blue-50
├── surface-error           → alias: color/red/red-50
├── surface-success         → alias: color/green/green-50
└── surface-warning         → alias: color/yellow/yellow-50
```

### Text Tokens
```
text/
├── text-primary            → alias: color/gray/gray-900
├── text-secondary          → alias: color/gray/gray-600
├── text-tertiary           → alias: color/gray/gray-400
├── text-inverse            → alias: color/base/white
├── text-brand              → alias: color/blue/blue-600
├── text-error              → alias: color/red/red-600
├── text-success            → alias: color/green/green-600
└── text-link               → alias: color/blue/blue-600
```

### Border Tokens
```
border/
├── border-primary          → alias: color/gray/gray-200
├── border-secondary        → alias: color/gray/gray-300
├── border-focus            → alias: color/blue/blue-500
├── border-error            → alias: color/red/red-500
└── border-success          → alias: color/green/green-500
```

### Button Tokens
```
button/
├── button-primary-bg       → alias: color/blue/blue-600
├── button-primary-text     → alias: color/base/white
├── button-primary-hover    → alias: color/blue/blue-700
├── button-secondary-bg     → alias: color/base/white
├── button-secondary-text   → alias: color/gray/gray-700
├── button-secondary-border → alias: color/gray/gray-300
├── button-danger-bg        → alias: color/red/red-600
└── button-danger-text      → alias: color/base/white
```

### Spacing Tokens
```
spacing/
├── spacing-xs              → alias: spacing/1 (4px)
├── spacing-sm              → alias: spacing/2 (8px)
├── spacing-md              → alias: spacing/4 (16px)
├── spacing-lg              → alias: spacing/6 (24px)
├── spacing-xl              → alias: spacing/8 (32px)
├── spacing-2xl             → alias: spacing/12 (48px)
├── spacing-section         → alias: spacing/16 (64px) or larger
├── component-padding-sm    → alias: spacing/2 (8px)
├── component-padding-md    → alias: spacing/3 (12px)
└── component-padding-lg    → alias: spacing/4 (16px)
```

---

## CREATING ALIASES (STEP BY STEP)

1. Open Variables panel
2. Navigate to Tokens collection
3. Click on a token variable value cell
4. Click the "Libraries" icon (link icon)
5. Navigate to Primitives collection
6. Select the primitive variable to reference
7. Token now shows alias arrow icon with linked primitive name

---

## APPLYING VARIABLES TO DESIGNS

### Fill Color
1. Select element
2. In Fill section, click the small variable icon (hexagon)
3. Browse token variables
4. Select appropriate token (e.g., "surface-primary")
5. Fill now displays variable name instead of hex

### Stroke Color
1. Select element with stroke
2. In Stroke section, click variable icon
3. Select border token

### Auto Layout Spacing
1. Select auto layout frame
2. Click variable icon next to gap value
3. Select spacing token (e.g., "spacing-md")
4. Repeat for padding values

### Corner Radius
1. Select element
2. Click variable icon next to corner radius value
3. Select radius token

---

## THEME SWITCHING WITH TOKENS

### How It Works
1. Create a variable Mode for "Light" and "Dark" in the Tokens collection
2. Each token gets two values -- one per mode
3. Example: "surface-primary" = white (Light) / gray-900 (Dark)
4. Example: "text-primary" = gray-900 (Light) / white (Dark)
5. Apply a mode to a frame, and ALL children using tokens switch automatically

### Light/Dark Mode Token Mapping
| Token | Light Mode | Dark Mode |
|-------|-----------|-----------|
| surface-primary | white | gray-900 |
| surface-secondary | gray-50 | gray-800 |
| text-primary | gray-900 | white |
| text-secondary | gray-600 | gray-400 |
| border-primary | gray-200 | gray-700 |
| button-primary-bg | blue-600 | blue-500 |

---

## DEV MODE HANDOFF CHECKLIST

### Before Handoff
- [ ] All layers named (no "Frame 427" or "Rectangle 12")
- [ ] Batch rename (Cmd/Ctrl+R) groups of similar elements
- [ ] All colors use variables/styles (no raw hex in properties)
- [ ] All text uses text styles
- [ ] All spacing uses variables or consistent values
- [ ] Components are properly structured (no detached instances)
- [ ] Interactive component prototype flows are connected
- [ ] Export settings configured on assets (SVG for icons, 2x PNG for images)

### What Developers See in Dev Mode
- **Code tab**: CSS, iOS (Swift), Android (Kotlin) for selected element
- **Properties**: All style properties with variable names
- **Spacing**: Pixel-perfect measurements between elements
- **Assets**: Export options configured by designer
- **Components**: Property values and variant state

### Export Protocol for Assets
| Asset Type | Format | Resolution | Naming |
|-----------|--------|-----------|--------|
| Icons | SVG | 1x | icon-name.svg |
| Photos | PNG or WebP | 2x | image-description@2x.png |
| Logos | SVG | 1x | logo-variant.svg |
| Illustrations | SVG or PNG | 2x | illustration-name@2x.png |
| Favicon | PNG | 1x | favicon-32x32.png |
| OG Image | PNG | 1x | og-image-1200x630.png |
