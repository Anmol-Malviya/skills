---
name: gobblecube-dark-neon-ui
description: Recreate the deep dark mode, neon-glowing, glassmorphism SaaS aesthetic seen on GobbleCube.ai.
---

# GobbleCube Dark Neon UI Skill

This skill teaches you how to build immersive, tech-heavy, dark mode SaaS landing pages utilizing neon glows, deep space backgrounds, and glassmorphism.

## 📸 Visual Reference
![GobbleCube UI Reference](https://image.thum.io/get/width/1200/crop/1000/https://gobblecube.ai/)

---

## 🎨 The Aesthetic DNA

### 1. Deep Space Canvas
*   **Backgrounds:** Deep navy (`#0A0A0B`) or pure black. Use Aceternity UI's `bg-grid-white/[0.02]` or `bg-dot-white/[0.2]` to add texture and depth to the background.
*   **Glassmorphism:** Navigation bars and overlaying elements must use translucent backgrounds (`bg-black/40`) and heavy blurs (`backdrop-blur-md`).

### 2. Neon Accents & Glows
*   **Colors:** Use electric cyan (`#00FFFF`), bright purple, or vibrant blue for primary actions.
*   **Shadows:** Replace standard drop shadows with neon glows using Tailwind: `shadow-[0_0_20px_rgba(0,255,255,0.4)]`.

### 3. Advanced Bento Cards
*   Cards should use dark backgrounds (`bg-[#111]`) with subtle white borders (`border border-white/10`).
*   **Hover Effects:** Implement radial gradients that activate on hover to simulate an "inner glow" or "border glow" on the cards.

---

## ⚡ The Tech Stack

1.  **Framework**: Next.js (App Router) + Tailwind CSS.
2.  **The "Magic" Libraries**:
    *   **Aceternity UI:** For glowing borders, moving background grids, and text hover effects.
    *   **Magic UI:** For animated bento grids and marquees.
3.  **Animations**: Heavy reliance on Framer Motion or GSAP. Every section should fade and slide up on scroll.

---

## 🛠️ Implementation Rules

1.  **Hero Section:** Massive gradient text heading (`bg-clip-text text-transparent bg-gradient-to-r`). A primary CTA button that glows on hover.
2.  **Bento Grid:** Create an asymmetrical grid of features. Wrap each card in a container that listens to mouse movements to create dynamic lighting effects (e.g., Aceternity's glowing cards).
3.  **Navigation:** Sticky header, fully transparent at the top, becoming `bg-black/50 backdrop-blur-md` on scroll.

## 🚦 Prompting the Agent
> *"Use the `gobblecube-dark-neon-ui` skill to build a features section. Use a dark background with an Aceternity grid, neon cyan accents, and glowing bento cards."*
