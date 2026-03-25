---
name: Animation Tools Reference
description: "Lottie (+ AI generation), Spline 3D, GSAP integration, Rive, Unicorn Studio, Three.js overview, and Figma prototyping animation concepts."
---

# Animation Tools Reference

Setup guides and capabilities for each animation tool available in Webflow projects.

---

## LOTTIE

### What It Is
Lightweight vector animations in .json format. Originally from After Effects, now generatable with AI. Natively supported in Webflow.

### File Format
- `.json` (not video, not GIF)
- Extremely lightweight (kilobytes, not megabytes)
- Scalable without quality loss (vector-based)
- Controllable via Webflow's interaction system

### Adding to Webflow
1. Elements panel > Advanced > Lottie
2. Upload .json file or paste URL
3. Configure: autoplay, loop, direction, speed
4. Optional: connect to Webflow scroll/trigger interactions

### AI-Generated Lottie Workflow
1. Upload a reference image to ChatGPT (or similar AI)
2. Describe the desired animation: "Make these circles pulsate in a staggered way"
3. Request output as Lottie .json file
4. Download the .json
5. Preview at lottiefiles.com before importing
6. Iterate on prompt if needed (e.g., "not simultaneously, stagger them")
7. Import directly into Webflow

### Lottie Interaction Control
- **Scroll-controlled:** Map animation progress to scroll position
- **Click-triggered:** Play on user click
- **Hover-triggered:** Play on mouse enter, reverse on mouse leave
- **Page load:** Play once on page load

### Best Use Cases
- Logo animations (contour reveal, color fill)
- Pre-loaders
- Icon animations (menu toggle, like button)
- Decorative section transitions
- Loading states

### Limitations
- No interactivity beyond Webflow triggers
- Complex animations increase file size
- Not suitable for photographic/raster content
- Browser rendering varies slightly

---

## SPLINE (3D FOR WEB)

### What It Is
3D modeling tool for web with built-in interactivity. Creates embeddable 3D scenes that respond to mouse movement, scroll, and clicks. Natively supported in Webflow.

### AI Model Generation
1. Use Spline's AI prompt system
2. Describe desired 3D model (e.g., "white sneaker on platform")
3. AI generates base model
4. Customize: materials, lighting, textures, animations
5. Export texture maps, modify in Photoshop if needed (e.g., change shoe color)
6. Re-import modified textures

### Embedding in Webflow
1. Export scene from Spline (embed URL)
2. Elements panel > Embed
3. Paste Spline embed code
4. Set container dimensions and z-index

### Z-Index Strategy with Spline
```
Background layer (decorative):     z-index: 0
Spline 3D model (interactive):     z-index: 1
Content layer (text, buttons):     z-index: 2
```

### Interaction Types
- **Mouse tracking:** Model follows cursor position
- **Scroll-controlled:** Animation tied to page scroll
- **Click interaction:** State change on click
- **Hover effects:** Material/lighting changes on hover

### Performance Considerations
- 3D rendering is GPU-intensive
- Test on mobile devices (may need reduced quality)
- Consider fallback static image for low-powered devices
- Limit to one major Spline embed per page

---

## GSAP IN WEBFLOW

### What It Is
GreenSock Animation Platform -- the most powerful JavaScript animation library, now being natively integrated into Webflow. Powers most award-winning websites.

### Access in Webflow
- Interactions panel > GSAP icon
- Available for both scroll triggers and element animations
- Custom attributes for targeting (not just classes)

### Scroll Trigger Configuration
| Setting | Options | Recommended |
|---------|---------|-------------|
| Target | Attribute, class, or element | Attribute (most reusable) |
| Start position | Top/center/bottom of element meets top/center/bottom of viewport | "top bottom" (when top of element hits bottom of viewport) |
| End position | Same options | "bottom top" (when bottom of element hits top of viewport) |
| Mode | Scrub / Trigger | Trigger for content reveals |
| Duration | Seconds | 0.5s |
| Easing | GSAP easing functions | power-out-3 |

### GSAP Easing Functions
| Function | Feel | When to Use |
|----------|------|-------------|
| power-out-1 | Gentle deceleration | Subtle movements |
| power-out-2 | Medium deceleration | General purpose |
| power-out-3 | Strong deceleration | Content reveals (recommended default) |
| power-out-4 | Very strong deceleration | Dramatic reveals |
| power-in-out-2 | Smooth both ends | While-scrolling animations |
| elastic-out-1 | Bouncy | Playful interactions |
| bounce-out | Ball bounce | Fun, attention-grabbing |

### Markers for Debugging
- Enable markers to see exactly where scroll triggers fire
- Green marker: start position
- Red marker: end position
- Always disable markers before publishing

### Reusable GSAP Patterns
Create animation presets via custom attributes:
```
animation="slide-up"     → translateY 40px to 0, opacity 0 to 1
animation="fade-in"      → opacity 0 to 1
animation="slide-left"   → translateX -40px to 0, opacity 0 to 1
animation="slide-right"  → translateX 40px to 0, opacity 0 to 1
animation="scale-in"     → scale 0.8 to 1, opacity 0 to 1
```

---

## RIVE

### What It Is
Interactive animation tool combining Lottie capabilities with rich interactivity. State machines allow complex conditional animations.

### Web Design Use Cases
- Interactive illustrations
- Animated icons with multiple states
- Game-like micro-interactions
- Complex conditional animations

### Limitations for Web Design
- More useful for apps/games than marketing websites
- Steeper learning curve than Lottie
- Larger file sizes for complex animations
- Less established in web design workflows

### Embedding in Webflow
- Export from Rive as web runtime
- Embed via custom code element
- Rive runtime JavaScript required

---

## UNICORN STUDIO

### What It Is
WebGL effects with a no-code interface. Creates shader-based visual effects (gradients, particles, distortions) without coding.

### Capabilities
- Animated mesh gradients
- Particle systems
- Image distortion effects
- Mouse-reactive backgrounds
- Blur and glow effects

### Integration
- Paid tool
- Generates embed code
- Paste into Webflow embed element
- Usually used as background layer (z-index: 0)

### When to Use
- Creative agency sites
- Portfolio pieces
- Landing pages with high visual impact
- NOT for e-commerce or utility-focused sites

---

## THREE.JS

### What It Is
Full JavaScript 3D framework -- the foundation that Spline is built on. Provides complete control over 3D scenes, materials, lighting, and physics.

### Relevance to Webflow
- Spline uses Three.js under the hood
- Direct Three.js requires JavaScript coding
- AI can generate Three.js code from prompts
- Out of scope for most Webflow projects
- Consider when Spline's limitations are reached

---

## FIGMA PROTOTYPING (Animation Concepts)

### Types of UI Animation [Arash]
- **Micro-interactions:** Button hover, toggle, like animation
- **Page transitions:** Screen-to-screen navigation
- **Loading animations:** Spinners, skeleton screens
- **Scroll animations:** Parallax, reveal effects
- **Notification animations:** Toast slides, badge bounces

### Interactive Component Animations (Figma)
- Connect variant states within component set
- While Hovering trigger for hover effects
- On Click trigger for pressed states
- Smart Animate for smooth transitions between variants
- These prototypes serve as animation specs for Webflow implementation

### Prototyping to Implementation Flow
1. Design animation in Figma (prototype mode)
2. Document: trigger, duration, easing, properties animated
3. Implement in Webflow using equivalent interactions
4. Smart Animate in Figma ≈ transition with ease-out in Webflow

---

## TOOL SELECTION GUIDE

| Need | Tool | Complexity |
|------|------|-----------|
| Simple hover/scroll animations | Webflow Native | Low |
| Quick section reveals | Webflow Presets | Low |
| Scalable reusable animations | GSAP + Attributes | Medium |
| Logo/icon animations | Lottie | Medium |
| 3D interactive models | Spline | Medium-High |
| Complex state machines | Rive | High |
| Shader effects / WebGL | Unicorn Studio | Medium |
| Full 3D scenes | Three.js | High |

### Default Recommendation
For most Webflow projects, use this combination:
1. **Webflow Native** for hover states and simple triggers
2. **GSAP + Attributes** for scroll-triggered content reveals
3. **Lottie** for pre-loaders and icon animations
4. Add **Spline** only if 3D is part of the design concept
