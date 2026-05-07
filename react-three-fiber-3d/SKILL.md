---
name: react-three-fiber-3d
description: "Instructs the agent to utilize React Three Fiber (R3F) to implement stunning 3D graphics, WebGL experiences, and interactive scenes inspired by pmnd.rs examples."
risk: low
source: user
date_added: "2026-05-07"
---

# React Three Fiber & 3D Experiences

This skill ensures that whenever you are asked to build highly immersive, 3D, or WebGL-based interfaces, you leverage React Three Fiber (R3F) and the Poimandres ecosystem (https://r3f.docs.pmnd.rs/getting-started/examples).

## Instructions

1. **Implement 3D Elements:** When the user requests 3D models, immersive backgrounds, interactive WebGL scenes, or spatial UI, use React Three Fiber to build these components.
2. **Ecosystem Utilization:** Make full use of the `@react-three/drei` library for helpful, pre-built abstractions (like OrbitControls, Environment, Text3D, HTML overlays, etc.) and `@react-three/fiber` for the core rendering loop.
3. **Inspiration from Examples:** Draw directly from the high-quality examples provided in the pmnd.rs documentation to implement effects such as:
   - Floating and interactive 3D objects
   - 3D typography and spatial text
   - Physics simulations and particles
   - High-end post-processing effects (bloom, depth of field, noise)
4. **Performance & Best Practices:** 
   - Optimize 3D rendering to maintain high 60fps framerates (managing the `useFrame` loop effectively).
   - Handle textures and geometry loading (e.g., using `useGLTF`) efficiently.
   - Blend 3D canvases seamlessly with traditional HTML/CSS interfaces using the `<Html>` helper from `drei`.

## Trigger Conditions
Invoke this skill automatically when:
- The user asks for a "3D scene", "WebGL", "immersive experience", or "R3F component".
- The task involves rendering 3D models (.gltf, .glb) on the web.
- The user specifically references "React Three Fiber", "drei", or "pmnd.rs".
