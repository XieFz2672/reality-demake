# Reality Demake

**Skill ID:** `reality-lowpoly-remake`  
**Version:** `1.1.0`  
**Definition:** Remake real-world photos as 2004-era game screenshots. This is not a filter—it is a demake.

---

## 1. Goal

When the user provides a real-world photo and invokes this skill, reinterpret the image as an early-3D game screenshot from around 2004.

Preserve:

- the main subject and identity anchors;
- composition and crop relationships;
- camera angle and perspective;
- pose and orientation;
- major architectural silhouettes;
- spatial layout;
- key props and their positions.

Rebuild:

- mesh complexity;
- material textures;
- lighting behavior;
- vegetation and environmental assets;
- character and object model quality;
- overall image quality and old-game-map atmosphere.

Core criterion:

> The result must look as if the real scene was broken into old game assets and rebuilt—not as if a retro, pixel, blur, or low-resolution filter was placed over the original photo.

---

## 2. When to use

Use this skill when:

- the user asks for a demake, low-poly remake, or old-game screenshot;
- the user references early Source-engine visuals, 2004-era 3D games, or early GMod map aesthetics;
- the user wants to turn travel photos, streets, architecture, environmental portraits, food, or objects into an old-game scene or prop;
- the user invokes the skill by name.

Do not automatically apply the skill when the user only requests lower resolution, pixel art, or a retro filter. Follow the user’s exact request instead.

---

## 3. Default behavior

Unless the user says otherwise:

- preserve the original aspect ratio;
- use Standard intensity;
- add no text, logos, HUD elements, borders, or watermarks;
- add no new people, animals, buildings, or unrelated props;
- do not change weather, season, time of day, or location;
- do not remove key elements;
- preserve recognizable identity, pose, clothing colors, and accessories;
- return a single final image rather than a before/after poster.

User-specified aspect ratio, weather, time, text, removals, or additions take priority.

---

## 4. Workflow

### Step 1: Read the source image

Before generation, identify and lock:

1. the main subject, position, and scale;
2. pose, face direction, hairstyle, clothing, and accessories;
3. camera height, view direction, perspective lines, and depth;
4. positions of architecture, roads, vegetation, furniture, vehicles, and other major objects;
5. recognition anchors that must survive;
6. elements the user explicitly wants preserved, removed, or emphasized.

Do not expose a long internal analysis. Use it directly in generation.

### Step 2: Select a scene adapter

#### A. Urban and architecture

For streets, residential areas, malls, subway stations, parking lots, convenience stores, campuses, plazas, and interiors.

Emphasize:

- simplified architectural geometry;
- low-resolution, repeated, slightly stretched wall and ground textures;
- stiff direct lighting and baked shadows;
- navigable old-game-map paths;
- lower level of detail in distant architecture.

Avoid:

- physically accurate glass and metal reflections;
- cinematic global illumination;
- excessive architectural detail.

#### B. Nature

For forests, streams, mountain paths, parks, waterfronts, and courtyards.

Emphasize:

- low-poly tree masses or unmistakable old-game vegetation assets;
- simplified billboard vegetation at a distance without turning every plant into a flat card;
- low-resolution repeating rock, soil, and grass textures;
- simple reflections and early-game water materials;
- preserved terrain, path, and stream direction.

Avoid:

- modern photoreal foliage systems;
- highly detailed leaves, fur, or fluid simulation;
- simple pixelation of the source photo.

#### C. Environmental portraits

For travel photos and street portraits where a person is placed inside a complete scene.

Emphasize:

- a recognizable low-poly NPC model;
- identity anchors such as face shape, hairstyle, glasses, camera, bags, and clothing silhouette;
- clear polygonal planes on limbs and garments;
- low-resolution skin and fabric textures rather than toy-like plastic materials.

Avoid:

- generating a different face;
- changing age, gender expression, body shape, or pose;
- turning the subject into anime, cartoon, or modern CG.

#### D. Props and food

For food, drinks, exhibits, furniture, or individual objects.

Emphasize:

- treating the subject as a collectible old-game prop or environment asset;
- preserving shape, arrangement, container, and main colors;
- low-poly silhouettes and low-resolution materials;
- slightly stiff highlights and shadows.

Avoid:

- adding inventory UI, buttons, text, or HUD elements;
- changing the food or object into a different category;
- modern advertising render quality.

### Step 3: Select intensity

#### Light

- maximum source-image recognizability;
- moderate mesh and texture simplification;
- more character and scene detail;
- best for visually gentle outputs.

#### Standard — default

- clearly visible low-poly geometry;
- clearly low-resolution textures;
- stiff, slightly unnatural early-game lighting;
- balance between source fidelity and old-game-map character.

#### Heavy

- strongly reduced polygon count and texture detail;
- repeated, stretched, and visibly joined textures are acceptable;
- stronger cheap-asset-pack, custom-map, and old-PC-game feeling;
- subject, composition, and spatial layout must still remain intact.

### Step 4: Generate

Use this core prompt:

> Remake this photo as an early Source-engine-style 3D game screenshot from around 2004. Strictly preserve the original subject, composition, viewpoint, perspective, pose, spatial layout, and key recognition anchors. Do not apply a surface filter; instead, break the entire photo into old-game assets and rebuild it. Render people, architecture, trees, roads, rocks, furniture, food, and all objects with clearly simplified low-poly geometry. Use low-resolution textures that are slightly blurry, dirty, repeated, and limited in detail. Simulate stiff, mildly inconsistent direct lighting and baked shadows typical of early 3D engines. The final image should feel like a genuinely playable 2004-era game-map screenshot with cheap assets, NPC presence, old-map atmosphere, and navigable space. Avoid modern 3D rendering, PBR materials, cinematic lighting, anime, illustration, simple pixelation, identity changes, or removal of key elements.

Append scene-adapter and intensity instructions as needed.

---

## 5. Anchor preservation

### People

Preserve as closely as possible:

- face shape and relative feature placement;
- hairstyle, hair color, and glasses;
- body pose and hand action;
- clothing silhouette and main colors;
- key accessories such as cameras, bags, hats, and scarves.

The person may become low-poly, but must not become an obviously different person.

### Architecture and environment

Preserve:

- building volume and primary silhouette;
- positional relationships between roads, stairs, rivers, windows, and entrances;
- foreground, midground, and background structure;
- location-specific recognition anchors.

Details may be simplified, but the space must not be arbitrarily rearranged.

### Text and signage

Do not promise accurate reconstruction of small text unless the user explicitly requires it. Avoid invented brands, gibberish signs, or unnecessary lettering. When the user asks to remove text, remove it fully rather than replacing it.

---

## 6. Negative constraints

Do not introduce:

- Unreal Engine, modern AAA, or high-end CG aesthetics;
- high-resolution PBR materials, realistic ray tracing, or cinematic global illumination;
- anime, manga, hand-drawn, oil-painting, or cartoon styles;
- simple pixelation, mosaics, or compression filters;
- soft beauty lighting or polished skin;
- unsolicited cyberpunk neon;
- added HUDs, subtitles, borders, logos, or watermarks;
- unrelated people, vehicles, architecture, or props.

---

## 7. Automatic repair loop

After generation, check for the following problems and apply the matching patch before regenerating.

### Still looks like a filtered photo

> Do not preserve photographic surfaces. Rebuild the people, architecture, vegetation, roads, and objects as visible low-poly 3D models. Strengthen polygonal planes, hard silhouettes, low-resolution textures, and old-game asset character.

### Too polished or modern

> Reduce polygon count and material precision. Remove PBR, advanced reflections, depth-of-field, and cinematic lighting. Use rougher low-resolution textures, stiff direct lighting, baked shadows, and cheap asset-pack quality.

### Only pixelated or blurred

> Do not create the effect by enlarging pixels or blurring the image. The geometry itself must be simplified into genuine low-poly planes and block forms while remaining readable.

### The person became someone else

> Lock the original face shape, relative facial-feature placement, hairstyle, glasses, pose, clothing silhouette, and key accessories. Reduce only mesh and texture fidelity; do not redesign the person.

### Main subject or prop disappeared

> Restore the original main subject and key props at their original position, scale, pose, and orientation. Stylization may change only geometry, materials, and lighting—not narrative content.

### Composition or spatial layout changed

> Realign to the source camera angle, horizon, perspective lines, foreground/midground/background relationships, and object positions. Do not move, enlarge, shrink, or rearrange major elements.

### Low-poly effect is too weak

> Strengthen simplified polygonal planes on people, architecture, trees, rocks, and objects. Reduce curves and small details, make edges harder and forms chunkier, while keeping the subject recognizable.

### Too dark or unreadable

> Keep early-game lighting stiff, but increase ambient visibility and subject readability. Avoid crushed black shadows; keep scene structure and character details visible.

---

## 8. Pre-delivery quality check

A result is complete only when most of the following are true:

- [ ] Subject, pose, composition, and viewpoint match the source
- [ ] The effect is not merely a filter, blur, mosaic, or pixel-art conversion
- [ ] People and objects have genuine low-poly structure
- [ ] Materials are visibly low-resolution, limited, repeated, or rough
- [ ] Lighting is stiff and slightly unnatural but readable
- [ ] The image resembles a playable 2004-era game screenshot
- [ ] No modern PBR, cinematic, or high-end 3D look
- [ ] No unsolicited text, people, props, or scenery
- [ ] Identity and location recognition anchors remain present

---

## 9. User interaction

- When the user provides an image and a clear request, execute without repeating confirmation.
- Ask only when the image is missing, the target image is unclear, or instructions conflict.
- Do not expose internal analysis.
- After completion, keep the response minimal and show the result.
- When the user says “not rough enough,” “too polished,” or “not like an old game,” use the repair patches instead of switching to another visual style.

---

## 10. Copyright, privacy, and usage

- Process only images the user has the right to use.
- For real people, rely on the user-provided image and do not infer sensitive identity information.
- Do not precisely imitate the personal style of a living artist.
- “Source Engine,” “Half-Life 2,” and “Garry’s Mod” are references to an era and visual character only.
- Do not generate copyrighted characters, logos, exact maps, or recognizable proprietary assets from those works unless the user has rights and explicitly requests them.
