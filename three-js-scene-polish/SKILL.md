---
name: Three.js scene polish
description: >-
  Use when polishing Three.js / R3F lighting, materials, bloom/grain, or making
  a GLB mascot look premium on a web hero without killing framerate.
---
# Three.js scene polish

## Lighting order
1. Environment / HDRI (or soft ambient + hemisphere)
2. One key directional (warm), one cool fill
3. Optional rim / point for eyes and felt nap

## Post (use sparingly on marketing heroes)
Bloom → Vignette → light grain last. Prefer `@react-three/postprocessing` in R3F.
Skip heavy DOF on mobile; kill effects under reduced-motion.

## Materials
- Felt/plush: high roughness, low metal, subtle normal/noise maps
- Eyes: slightly lower roughness / controlled specular
- Never leave default MeshBasic on hero assets

## Perf
- Cap DPR; demand frameloop when idle
- One shadow light max for heroes
- Compress textures; avoid 4K maps on a mascot under 50k tris
