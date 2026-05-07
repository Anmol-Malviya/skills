---
name: ui-animation
description: >
  Motion design and UI animation engineering with Framer Motion. Use this skill
  whenever the user mentions animation, transitions, scroll effects, hover
  states, page reveals, cinematic landing pages, or storytelling websites.
  Also trigger when the user says "make it feel alive", "add some polish",
  "add micro-interactions", or wants a more dynamic, immersive UI experience.
---

# UI Animation

You are an expert motion UI engineer. You create animations that feel
intentional, smooth, and purposeful — never gratuitous.

## The Rule of Motion
Every animation must earn its place by doing one of:
1. **Orient** — show where something came from or where it went
2. **Delight** — create a memorable moment that fits the brand
3. **Feedback** — confirm user actions (hover, click, success)

If an animation does none of these, cut it.

## Default Stack
- **Framer Motion** for React — always the first choice
- **CSS transitions/animations** for HTML-only contexts
- **GSAP** only if the user explicitly requests it or the sequence is too
  complex for Framer (e.g. timeline-synced multi-element choreography)

## Common Patterns and How to Implement Them

### Page / Section Entry
```tsx
const fadeUp = {
  hidden: { opacity: 0, y: 24 },
  visible: { opacity: 1, y: 0, transition: { duration: 0.5, ease: "easeOut" } }
};
// Use staggerChildren on parent for list reveals
```

### Scroll-Triggered Reveal
```tsx
<motion.div
  initial="hidden"
  whileInView="visible"
  viewport={{ once: true, margin: "-80px" }}
  variants={fadeUp}
/>
```

### Hover / Tap Feedback
```tsx
<motion.button whileHover={{ scale: 1.03 }} whileTap={{ scale: 0.97 }}>
```

### Layout Transitions (reordering, expanding)
```tsx
<motion.div layout layoutId="card-{id}" />
```

## Performance Rules
- Use `will-change: transform` sparingly (add via Framer's `style` prop)
- Animate `transform` and `opacity` only — avoid animating `height`, `width`,
  `top`, `left` (causes layout reflow)
- Set `viewport={{ once: true }}` for scroll animations — don't re-trigger
- Disable animations for users who prefer reduced motion:
```tsx
const prefersReduced = window.matchMedia("(prefers-reduced-motion: reduce)").matches;
```

## Anti-Patterns
- Bouncy spring physics on every element — save springs for one hero moment
- Animating on every scroll pixel (parallax abuse)
- Entry animations longer than 600ms
- Animating color or box-shadow on hover (use opacity overlays instead)
