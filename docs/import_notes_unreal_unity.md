# Import Notes — Unreal Engine & Unity

Scale authoring: **1 Blender Unit = 1 meter**. Up axis = +Z (Blender). GLB exported +Y up.

## General
- Prefer the **GLB** files for fastest round-trip — baked PBR textures (BaseColor, Roughness,
  Normal) are embedded, so materials reconstruct automatically.
- **FBX** files also have textures embedded (`embed_textures=True`). On import, let the engine
  extract embedded media to its own texture folder.
- Every asset has its pivot at **ground center** and transforms applied, so it drops onto a floor
  at world Z/Y = 0 with no offset.

## Unreal Engine 5
- Import scale: Blender meters → Unreal centimeters. UE import auto-applies the 100× FBX unit
  scale; verify the booth reads ~376 cm wide × 295 cm tall after import.
- Use GLB via Interchange, or FBX with "Convert Scene Unit" = true.
- Material: BaseColor → Base Color, Roughness → Roughness (ensure sRGB OFF), Normal → Normal
  (sRGB OFF, flip green if needed — maps are OpenGL/tangent space). Glass: make a Translucent or
  Thin-Translucent material; the GLB glass material is low-roughness, transmissive.
- Recommended: enable Nanite later (after LODs are decided); current asset is a single static mesh.

## Unity (URP/HDRP)
- Import the GLB (via glTFast/UnityGLTF) or FBX. Set "Convert Units" so 1 m = 1 Unity unit.
- Normal map: mark texture as Normal Map type. Roughness map: Unity uses Smoothness — invert
  roughness or use a Metallic/Smoothness packing step in your shader/material.
- Glass: assign a transparent/glass shader; base material is a separate slot named `*_Glass`.

## Per-asset texture set
- CP_CheckpointBooth_A: `CP_CheckpointBooth_A_BaseColor.png`, `_Roughness.png`, `_Normal.png`
  (2048², in the asset `Textures/` folder; also embedded in GLB/FBX).
