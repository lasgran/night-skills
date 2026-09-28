---
name: R3F Next 3D
description: >-
  Use when building or polishing Next.js + React Three Fiber / Three.js / GLB
  heroes (Florá-style sites, WebGL canvas, cursor-follow mascots). Covers
  SSR-safe Canvas, useGLTF, performance budgets, and mobile fallbacks.
---
# R3F + Next.js 3D

## When
Next.js App Router site with a 3D hero, GLB mascot, product viewer, or scroll/cursor-driven WebGL.

## Hard rules
1. **DOM wins** — CTAs, text, forms stay in the DOM. Canvas is isolated and lazy.
2. **Client-only Canvas** — wrap with `"use client"` and `dynamic(..., { ssr: false })`.
3. **Budget** — declare max DPR (`dpr={[1, 1.75]}`), triangles, and texture MB before shipping.
4. **Load models with `useGLTF` + `Suspense` + `useGLTF.preload`** — never block LCP on the GLB.
5. **Clone scenes** before mounting twice; dispose custom geometry/materials you create by hand.
6. **`frameloop="demand"`** when nothing is continuously animating; otherwise keep idle cheap.
7. **Mobile / reduced-motion fallback** — static PNG/video poster if WebGL or `prefers-reduced-motion`.
8. Compress GLBs (Draco / gltf-transform) before `public/` when files grow past ~3–5 MB without need.

## Baseline pattern
```tsx
const Character3D = dynamic(() => import("./Character3D"), { ssr: false });
// Canvas: transparent alpha, soft lights, pointer follow on a parent <group>
// Animations: useAnimations + named clip (Idle), don't stack a second breathe on top
```

## Checklist before done
- [ ] No hydration errors from Canvas
- [ ] Model faces camera (+Z or documented yaw fix)
- [ ] Scale/position readable on desktop AND mobile
- [ ] WebGL context-loss recovery or remount key
- [ ] Fallback if GLB fails to load
