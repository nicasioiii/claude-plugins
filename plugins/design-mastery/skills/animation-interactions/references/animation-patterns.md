# Common Animation Patterns & Examples

Copy-paste ready animation patterns for common use cases.

## Pattern 1: Fade In on Scroll

```
Trigger: Scroll into view
Animation:
  0%: opacity 0, translateY(20px)
  100%: opacity 1, translateY(0)
Duration: 600ms
Easing: ease-out
Use: Content sections appearing as user scrolls
```

## Pattern 2: Scale Card on Hover

```
Default: scale(1)
Hover: scale(1.05)
Duration: 200ms
Easing: ease-in-out
+ Add shadow for depth
Use: Product cards, portfolio items
```

## Pattern 3: Color Change on Interaction

```
Default: background #0066FF
Click/Hover: background #0052CC (darker)
Duration: 150ms
Easing: ease-in-out
Use: Buttons, links, interactive elements
```

## Pattern 4: Slide Menu In

```
Default: translateX(-100%) (off-screen left)
Open: translateX(0) (on-screen)
Duration: 300ms
Easing: ease-out
Use: Mobile hamburger menu
```

## Pattern 5: Skeleton Screen Loading

```
Skeleton element opacity:
  0% → 50% → 0% (pulse)
Duration: 1500ms
Easing: ease-in-out
Repeat: infinite
Use: Placeholder while content loads
```
