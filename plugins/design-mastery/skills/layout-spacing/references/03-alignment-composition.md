---
name: Alignment & Composition Principles
description: |
  When to Read: Making alignment decisions, working with asymmetrical layouts, understanding visual weight, creating pacing in scrolling designs, or fixing balance issues.
  Cross-references: 01-grid-systems.md (grid as alignment framework), typography-systems (text alignment rules), design-critique (layout review against these principles).
---

# Alignment & Composition Principles

## ALIGNMENT RULES [MDS + Gareis]

### Strong Left Edge

- Strong vertical left edges = professional, trustworthy design [MDS]
- Alignment is more important than the grid [MDS]
- Nothing should be placed arbitrarily -- every element needs visual connection to something else [Flux]
- Random alignment = amateurish [Flux]

### Alignment Options

| Type | Best For | Notes |
|------|---------|-------|
| Left | Default for most content | Creates strong vertical reading edge |
| Center | Short formal sections, mobile titles | No strong edges; avoid for long text |
| Right | Balance in asymmetric layouts | Occasional use for counterweight |
| Justified | Long editorial content | Fills entire block width; creates formal structure [Gareis] |
| Columns/grids | Multi-column content | Alignment through grid system |
| Compositional | Creative/editorial | Free placement with intentional relationships |

### Baseline Alignment [MDS]

When text of different sizes sits on the same line, align to the text baseline (bottom of letters), NOT the top of the text box.

---

## OPTICAL VS. MATHEMATICAL CENTERING [MDS]

### The Problem

Mathematical alignment is not always visually correct. The human eye perceives things differently than measurements suggest.

### Common Cases

| Situation | Fix |
|-----------|-----|
| Play triangle in circle | Nudge right 1-2px |
| Text next to icon | May need vertical offset |
| Text in button | Sometimes 1px adjustment needed |
| Logo in navbar | Optical centering may differ from math |

### Rule

Trust your eyes over the measurements. Place mathematically, then adjust optically. Verify the design FEELS balanced.

---

## VISUAL BALANCE IN ASYMMETRICAL LAYOUTS [Gareis]

### Weight Distribution

Distribute elements based on visual weight, not physical position:
- Signal colors (red, neon green) add disproportionate visual weight
- Bold typography carries more weight than light
- High-contrast elements feel heavier than low-contrast
- Dark elements feel heavier than light [MDS]
- Detailed textures have more weight than flat colors [Gareis]
- Saturated colors feel heavier than desaturated [MDS]

### Counterbalancing Techniques

- Use white space as counterweight to heavy elements
- Align scattered elements to invisible structural lines for cohesion
- A small bright element can balance a large muted one [Gareis]
- 30/70 split: 30% white space buffer, 70% content = dynamic asymmetry [Gareis]

### Scale and Visual Weight [MDS]

Combining scale techniques for maximum impact:
- Large size + bold weight + saturated color + dark value = maximum visual weight
- Small size + regular weight + desaturated + light = minimum visual weight
- Use the full spectrum between these extremes for nuanced hierarchy

---

## PACING IN LAYOUT [Gareis]

### Definition

How information density changes throughout the layout -- the rhythm of dense and open sections.

### Principles

1. **Mix dense and open areas** -- heavy content next to minimal breathing space
2. **Create "wow moments"** (high-impact visuals/statements) between quieter sections -- like a beat drop in music
3. **Good pacing keeps people engaged** -- creates sense of journey instead of flat experience
4. **After data-heavy sections, provide clean/minimal** to let the brain reset
5. **Alternate alignment direction** -- left > right > left through the page maintains interest

### Content Layout Pattern [Gareis]

- Asymmetrical reading flow: left side > right side > left side through the page
- Bold headlines break out of grid for emphasis while body text stays within
- Split paragraphs into two columns when single column is too wide

---

## SEVEN PRINCIPLES OF LAYOUT [Flux]

### 1. Guide the Viewer
Encourage information access in meaningful order. Make next step obvious.

### 2. Clear Focal Point
Center of interest (not necessarily center of layout).
- Dead center = formality, calmness
- Top-left = default reading start
- Rule of thirds = compositional interest

### 3. Grouping
Proximity suggests relationship. Gather related elements. Separate unrelated ones.

### 4. Alignment
Nothing placed arbitrarily. Every element should have visual connection to something else.

### 5. Balance
Even distribution of visual weight. Symmetrical (formal) or asymmetrical (interesting).

### 6. Scale
Relative size of elements. **Big-medium-small rule:** With 3+ elements, make one big, one medium, one small.

### 7. White Space
Empty areas of visual rest. White space is a luxury good -- more = higher-end feel.

### Sequence Principle [Flux]

Think of websites like movies -- each scroll panel is part of a cinematic story. Interrupt expected flow periodically to maintain interest.

---

## GESTALT PRINCIPLES IN LAYOUT

### Applied to Spacing

| Principle | Spacing Application |
|-----------|-------------------|
| Proximity | Closer elements = related; further = separate |
| Similarity | Same spacing pattern = same content type |
| Continuity | Smooth alignment lines guide the eye |
| Closure | Users complete partial visual frames |
| Figure-Ground | Foreground (white cards) on background (gray) |
| Common Region | Elements within same container = grouped |

---

## SCALE AND VISUAL WEIGHT [MDS]

### Building Blocks

| Element | More Weight | Less Weight |
|---------|-----------|------------|
| Size | Larger | Smaller |
| Color | Saturated | Desaturated |
| Value | Dark | Light |
| Weight (font) | Bold/Black | Light/Regular |
| Space | More surrounding space | Crowded among others |
| Contrast | High contrast with BG | Low contrast with BG |

### Combining for Hierarchy

- **Maximum emphasis:** Large + bold + saturated + dark + surrounded by space + high contrast
- **Maximum de-emphasis:** Small + regular + desaturated + light + crowded + low contrast
- Use 3-4 levels between extremes for typical content hierarchy

---

## AFFORDANCE IN LAYOUT [MDS]

Elements should suggest how they should be used:
- Buttons look pressable (shadows, gradients, distinct shape)
- Links look clickable (color, underline)
- Input fields look typable (border, background, placeholder)
- Sliders look draggable (handle + track)
- Position-based affordance: navigation at top inherits clickability regardless of visual treatment
