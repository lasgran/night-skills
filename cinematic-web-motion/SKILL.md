---
name: Cinematic web motion
description: >-
  Use when polishing scroll/hover/cinematic Next.js marketing sites
  (Florá-style): Framer Motion vs GSAP choice, hover day/night reveals, scroll
  storytelling, reduced-motion.
---
# Cinematic web motion

## Pick the tool
| Need | Library |
|---|---|
| Scroll timelines, pin, long choreography | GSAP + ScrollTrigger |
| React UI enter/exit, hover, shared layout | Framer Motion |
| Designer AE loops / icons | Lottie |

## Rules
1. Honor `prefers-reduced-motion`
2. Animate `transform` + `opacity` only on hot paths
3. One driver per property (do not fight GSAP vs Framer on the same node)
4. Kill ScrollTriggers / timelines on unmount (Next route changes)

## Florá-like patterns
- Hero: large type + masked day/night landscape on pointer
- 3D mascot: bottom canvas, pointer yaw, optional Idle clip
- Story section: scroll-expand image / parallax; keep CTA in DOM
- Keep motion hierarchy: hero bold → scroll subtle → ambient gentle

## Done when
- Hover/scroll feel premium without jank at 60fps desktop
- Mobile still readable if motion is reduced or 3D is poster-fallback
