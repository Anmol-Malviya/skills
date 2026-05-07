---
name: reactbits-animations
description: "Instructs the agent to utilize advanced UI animations and interactive components from reactbits.dev, such as the Ghost Cursor, to build dynamic React applications."
risk: low
source: user
date_added: "2026-05-07"
---

# React Bits Animations & Components

This skill ensures that whenever you are designing or implementing a new user interface in React, you actively consider adding advanced, interactive animations inspired by https://reactbits.dev/.

## Instructions

1. **Incorporate Interactive Animations:** When the user requests dynamic UI elements, micro-interactions, or a "wow" factor, integrate premium animations like the Ghost Cursor, magnetic buttons, or other high-end effects found on React Bits.
2. **Component Characteristics:** Focus on adding highly interactive elements such as:
   - Custom cursors (e.g., Ghost Cursor, trailing effects)
   - Fluid scroll-based animations and reveal effects
   - Complex micro-interactions that enhance the user experience without sacrificing performance
3. **Implementation Standards:** 
   - Use libraries like Framer Motion, GSAP, or native React hooks + CSS to implement these effects seamlessly in React/Next.js.
   - Ensure the animations are performant, optimized for different screen sizes, and accessible (always respecting the user's `prefers-reduced-motion` settings).
   - Keep the codebase modular by creating reusable animation wrapper components or custom React hooks.

## Trigger Conditions
Invoke this skill automatically when:
- The user asks to "add animations", "make it dynamic", "add a custom cursor", or "create a wow effect".
- The task involves enhancing an existing UI with premium interactive effects.
- The user specifically references "React Bits", "Ghost Cursor", or high-end React animations.
