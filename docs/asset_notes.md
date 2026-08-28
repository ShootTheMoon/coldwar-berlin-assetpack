# Cold War Berlin Asset Pack — Asset Notes

Historical setting: 1970s–1980s Cold War Berlin (pre-1989, GDR still active).
Scale convention: **1 Blender Unit = 1 meter**, +Z up, +Y world-forward.
Production rule: **one asset at a time**, user-validated. Nothing is APPROVED by the AI.

Quality benchmarks (targets): Brandenburg Gate (landmark), Apartment_Brick_Hero.011 /
WestAltbauHero_Material2 (West Berlin), EastPlattenbauHero (East Berlin).

---

## CP_CheckpointBooth_A  —  status: PENDING_USER_REVIEW
- **Category / Collection:** Checkpoint_Charlie / CHECKPOINT_Charlie_Final
- **Source method:** Manually modeled. (Sketchfab was searched first per priority order — the
  only on-subject result, "Checkpoint Charlie Berlin", was 2,512 faces with low-res textures
  and bundled extra geometry, far below the close-up hero bar, so it was rejected. A guard booth
  is a simple structure with clear real-world reference, so manual modeling was chosen to control
  topology, bevels, pivot, naming and PBR quality.)
- **Real-world dimensions:** 3.76 m (W, incl. roof overhang) × 3.23 m (D) × 2.95 m (H). Booth
  body ≈ 2.6 × 2.0 m; roof canopy cantilevers ≈ 0.5 m on all sides.
- **Geometry:** 4,837 faces / 5,844 verts / 8,456 tris. Clean bevelled edges (2-seg, ~8 mm).
- **Materials (2 slots):**
  - `CP_Booth_Atlas` — baked image PBR (BaseColor + Roughness + Normal, 2K) covering all opaque
    parts: white painted frame, dark metal door/handle/rivets, grey roof metal, concrete plinth,
    sign panel + extruded "ALLIED CHECKPOINT CHARLIE" lettering, gooseneck lamp. Weathering grime
    gradient, pointiness edge-wear and noise roughness variation were baked into the maps.
  - `CP_Booth_Glass` — transparent window material (low roughness, transmission/IOR 1.45).
- **Texture status:** Baked 2K atlas, saved to the asset `Textures/` folder and EMBEDDED in both
  GLB and FBX. No missing texture links. No default-gray material.
- **Pivot/transforms:** Origin at ground center (0,0,0); rotation & scale applied (scale = 1.0).
- **UVs:** Smart-projected, single `UVMap`, non-overlapping (used for the bake atlas).
- **Previews:** front / 3q / detail / scale (with 1.8 m human reference). Cycles, AgX.
- **Notes:** Sandbags, the separate "YOU ARE LEAVING THE AMERICAN SECTOR" sign, boom barrier and
  guard post are intentionally NOT part of this asset — they are their own Checkpoint Charlie kit
  items to be produced later.
- **Possible revision directions (if requested):** heavier grime/streaking, baked metallic + AO
  maps, 4K atlas for extreme close-ups, separate interior detailing, door handle escutcheon.
