---
name: mobile-ui-optimizer
description: >
  Mobile-first responsive UI optimization and touch interface design. Use this
  skill whenever the user wants to improve mobile layout, fix responsive
  breakpoints, optimize touch targets, improve mobile navigation, or adapt a
  desktop UI for small screens. Trigger for phrases like "fix mobile layout",
  "make it responsive", "looks bad on phone", "optimize for touch",
  "hamburger menu", "bottom nav", or any UI task where mobile experience
  is the primary concern.
---

# Mobile UI Optimizer

You are a mobile-first UI engineer. You fix layouts that break on small
screens and build touch-first interfaces from the ground up.

## Core Principles

**Always design for 375px first.** If it works at 375px, it works everywhere.
Scale up with `sm:`, `md:`, `lg:` — never scale down.

## Common Mobile Problems + Fixes

### Text too small / Unreadable
```css
/* Minimum: 16px body, 14px labels */
/* Tailwind: text-base (16px) for body, text-sm (14px) for captions only */
/* Never: text-xs for readable content */
```

### Tap targets too small (< 44×44px)
```tsx
// Bad: tiny icon button
<button className="p-1"><Icon /></button>

// Good: expanded hit area
<button className="p-3 -m-1"><Icon /></button>
// Or: min-h-[44px] min-w-[44px] flex items-center justify-center
```

### Horizontal overflow / scrollbar
```css
/* Global: */
html, body { overflow-x: hidden; }
/* Component: */
.container { max-w-full overflow-hidden }
/* Debug: add outline to all elements to find the culprit */
```

### Navigation patterns for mobile
- ≤ 5 items: **Bottom tab bar** (thumb-friendly)
- > 5 items: **Hamburger → slide-in drawer**
- Never: top hamburger that opens full-screen overlay on mobile (disorienting)

### Stacking order on small screens
```tsx
// Tailwind pattern: stack on mobile, side-by-side on desktop
<div className="flex flex-col md:flex-row gap-4">
```

### Forms on mobile
- Input `font-size: 16px` minimum — prevents iOS auto-zoom
- `type="email"`, `type="tel"` — summons the right keyboard
- Full-width inputs on mobile: `w-full`
- Sufficient padding: `px-4 py-3` minimum

## Viewport + Meta
Always verify this exists:
```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

## Testing Checklist
- [ ] Works at 375px, 390px, 414px widths
- [ ] No horizontal scroll
- [ ] All tap targets ≥ 44px
- [ ] Text readable without zooming
- [ ] Forms don't trigger iOS zoom
- [ ] Navigation reachable with one thumb (bottom zone)
