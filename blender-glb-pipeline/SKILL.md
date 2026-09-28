---
name: Blender GLB pipeline
description: >-
  Use when generating or refining a web GLB from Blender (bpy scripts,
  felt/plush mascots, headless export for R3F). Covers facing/+Z, feet origin,
  Idle clips, felt materials, and re-export into public/.
---
# Blender → web GLB

## When
Image-to-3D polish, procedural mascots, or regenerating `character*.glb` for a site.

## Export contract (R3F)
- Face **+Z**, up **+Y**, origin at **feet** (y=0)
- One looping clip named clearly (`Idle` or `Astra_Idle`)
- Prefer embedded PBR (JPEG) under ~5 MB unless detail needs more
- Keep an editable `.blend` next to the build script

## Headless build
```bash
blender --background --python tools/build_*.py
```
Copy output into the Next `public/` path the component loads.

## Felt / plush look
- High roughness, low metalness, optional SSS in Blender
- Noise/felt albedo maps + UVs (smart project)
- Soft icospheres for hands (avoid faceted cylinders)
- Push crown bumps **back** so they do not clip the face cream

## After export
1. Validate glTF (anims, materials, finite verts)
2. Wire `useGLTF` + `useAnimations` with the **exact** clip name
3. Screenshot the live site; adjust scale/yaw only in the React wrapper unless the mesh is wrong

## Anti-patterns
- Shipping the 17 KB procedural fallback when Blender is available
- Double-breath: baked Idle **plus** useFrame squash on the same bones
- Leaving Tripo/Meshy paywall as the only path when bpy can rebuild
