# Micro-Interactions: 200-300ms Patterns

Subtle animations in response to user action. These are the most important and frequently used animations.

## Button Hover

### Pattern 1: Scale

```
Default state: scale(1), shadow none
Hover state: scale(1.05), shadow 0 10px 30px rgba(0,0,0,0.15)
Duration: 200ms
Easing: ease-in-out
Implementation: CSS transition or Webflow interaction
```

Effect: Button slightly enlarges and gains shadow = feels clickable, responds to user

### Pattern 2: Color Change

```
Default state: background #000000
Hover state: background #333333 (slightly lighter)
Duration: 200ms
Easing: ease-in-out
```

Effect: Color shift signals interaction without physical change

### Pattern 3: Underline Animation

```
Default state: border-bottom width 0
Hover state: border-bottom width 2px
Duration: 200ms
Easing: ease-out
```

Effect: Underline grows in on hover = polished interaction

## Form Input Focus

```
Default state: border #CCCCCC, background white
Focus state: border #0066FF (brand color), background white, box-shadow
Duration: 150ms
Easing: ease-in-out
Implementation: :focus pseudo-class or Webflow interaction
```

Effect: Clear visual feedback that field is active

## Tooltip Appearance

```
Default state: opacity 0, pointer-events none
Hover state: opacity 1, pointer-events auto
Duration: 200ms
Easing: ease-out
Optional: slight translateY (move up 4px on appear)
```

Effect: Tooltip fades in, doesn't pop in abruptly

## Loading States

### Spinner

```
Rotation: 360 degrees continuous
Duration: 1000ms (1 full rotation per second)
Easing: linear
Effect: Smooth, constant rotation
```

### Skeleton Screen

```
Shimmer animation: opacity 0.5 → 1 → 0.5
Duration: 1500ms
Easing: ease-in-out
Repeat: infinite
Effect: Pulsing effect shows content is loading
```
