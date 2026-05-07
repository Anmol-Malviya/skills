---
name: modern-saas-bento-ui
description: Rapidly build premium, high-conversion SaaS landing pages (Bento Grids, Dark/Light Mode, Scroll Animations) using Next.js, Tailwind, and pre-built UI libraries. Includes visual references.
---

# Modern SaaS Bento UI Framework

This skill provides an in-depth blueprint for agents and users to recreate the premium, modern SaaS aesthetic seen on cutting-edge sites like Zangoh and GobbleCube in the absolute minimum amount of time. 

---

## 📸 Visual References & Deconstruction

### 1. The Light-Mode Minimalist (Zangoh Aesthetic)
![Zangoh UI Reference](https://image.thum.io/get/width/1200/crop/1000/https://zangoh.com/)

**Deconstruction:**
*   **Hero Section:** Hyper-focused. A massive, high-contrast headline (black text on off-white). No noisy backgrounds, just clean space to draw the eye to the primary Call-To-Action (CTA).
*   **Bento Grid Layout:** The feature section utilizes distinct, asymmetrical cards. Notice the soft, barely-there drop shadows (`shadow-sm`) and ultra-thin borders (`border border-gray-200`).
*   **Typography:** A modern geometric sans-serif font (like Inter or Geist) heavily relies on weight contrast (e.g., ExtraBold for headings, Medium for body).

### 2. The Dark-Mode Neon (GobbleCube Aesthetic)
![GobbleCube UI Reference](https://image.thum.io/get/width/1200/crop/1000/https://gobblecube.ai/)

**Deconstruction:**
*   **Deep Dark Mode:** The background is an expansive dark canvas (often a deep navy or pure black) layered with subtle radial gradients or grid lines to create an "infinite depth" feel.
*   **Neon Accents & Glows:** Primary buttons, icons, and active card states utilize bright, saturated colors (cyan, purple, or electric blue) paired with heavy box-shadow glows (`shadow-[0_0_20px_rgba(0,255,255,0.4)]`).
*   **Glassmorphism:** The sticky navigation bar and overlay cards use translucent backgrounds (`bg-black/40`) combined with a heavy backdrop blur (`backdrop-blur-md`).

---

## 🎨 The Aesthetic DNA (Design Tokens)

To perfectly replicate this UI/UX, you must enforce the following design tokens in your Tailwind config:

### Typography
*   **Primary Fonts**: Inter, Plus Jakarta Sans, or Geist.
*   **Headings**: Large-scale, Extra-Bold, tight letter-spacing (`tracking-tight` or `tracking-tighter`).
*   **Text Gradients**: Use text-gradients for the most important word in the hero section:
    ```html
    <span class="bg-clip-text text-transparent bg-gradient-to-r from-blue-400 to-cyan-300">
      AI Powered
    </span>
    ```

### Layout Patterns
*   **Bento Box Grids**: Use Tailwind CSS Grid (`grid-cols-1 md:grid-cols-3 md:grid-rows-2`). Mix card sizes using `col-span-2` or `row-span-2` to create visual interest.
*   **Padding/Rhythm**: Generous spacing is critical. Use `py-24` or `py-32` between major sections to let the design breathe. Cards should use uniform internal padding (`p-8`).

---

## ⚡ The "Minimum Time" Tech Stack

**Do not build complex modern UI components from scratch.** To save resources, time, and budget, compose the UI using these specific libraries:

1.  **Framework & Styling**: Next.js (App Router) + Tailwind CSS.
2.  **Base Components**: **[Shadcn UI](https://ui.shadcn.com/)** (Use this for accessible Buttons, Dropdowns, Inputs, and Dialogs).
3.  **The "Wow" Components**: **[Aceternity UI](https://ui.aceternity.com/)** & **[Magic UI](https://magicui.design/)**. Copy-paste their code for:
    *   *Grid & Dot Backgrounds* (Aceternity)
    *   *Bento Grids & Marquees* (Magic UI)
    *   *Border Magic/Glowing Cards* (Aceternity)
4.  **Animations**: **Framer Motion** or **GSAP**. Use these for scroll-triggered micro-interactions.

---

## 🛠️ Step-by-Step Implementation Guide

Follow this strict path to build a page in under an hour:

### Phase 1: Rapid Setup
1. Scaffold Next.js with Tailwind CSS (`npx create-next-app@latest`).
2. Initialize Shadcn UI (`npx shadcn-ui@latest init`).
3. Define your exact color palette (Dark or Light) in `globals.css` and configure your font in `layout.tsx`.

### Phase 2: The Foundation (The Shell)
1. **Glass Nav**: Create a `<Header>` with `sticky top-0 z-50 bg-background/50 backdrop-blur-md border-b border-white/10`.
2. **Hero Section**: 
    *   Center text alignment.
    *   Add a subtle grid background component from Aceternity.
    *   Add a bold `h1` with a gradient keyword, and a Shadcn Button with a hover scale effect (`hover:scale-105 transition-transform`).
3. **Bento Section**: 
    *   Create a `<BentoGrid>` container.
    *   Create a reusable `<BentoCard>` component with `rounded-3xl border border-white/10 bg-black/40 overflow-hidden backdrop-blur-sm relative group`.

### Phase 3: The Polish (Animations & Micro-interactions)
1. **Scroll Reveals**: Wrap your major sections (Hero, Bento Grid, Footer) in Framer Motion `<motion.div>` tags.
    ```tsx
    <motion.div initial={{ opacity: 0, y: 30 }} whileInView={{ opacity: 1, y: 0 }} viewport={{ once: true }}>
    ```
2. **Hover Glows (The Secret Sauce)**: For the dark mode aesthetic, add a hidden radial gradient inside your cards that follows the mouse or reveals on hover using CSS/Tailwind group-hover:
    ```html
    <div class="absolute inset-0 bg-gradient-to-br from-cyan-500/20 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500" />
    ```

---

## 🚦 Prompting the Agent

When you want to invoke this skill, prompt the AI with:
> *"Use the `modern-saas-bento-ui` skill. Build me a landing page Hero and Features section in Next.js. Use the dark-mode GobbleCube aesthetic, with a neon glowing CTA, a grid background, and an asymmetrical 3-column Bento grid for the features."*
