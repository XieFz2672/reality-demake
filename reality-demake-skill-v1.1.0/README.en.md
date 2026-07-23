# Reality Demake

> Remake real-world photos as 2004-era game screenshots. This is not a filter—it is a demake.

Reality Demake is a free and open image-editing skill. It reads the subject, composition, viewpoint, and spatial layout of a photo, then rebuilds people, architecture, vegetation, roads, furniture, food, and objects as early-3D game assets: low-poly meshes, low-resolution textures, stiff lighting, and the slightly awkward yet explorable feel of an old game map.

## What v1.1.0 improves

The original release centered on one reusable prompt. This iteration adds:

1. **A clear workflow**: analyze the image before selecting intensity and scene adaptation.
2. **Anchor-preservation rules**: protect identity, pose, composition, architectural silhouettes, and key props.
3. **Three intensity presets**: Light, Standard, and Heavy; Standard is the default.
4. **Four scene adapters**: urban/architecture, nature, environmental portrait, and props/food.
5. **An automatic repair loop**: fixes results that are too realistic, too polished, off-identity, or structurally inaccurate.
6. **A quality checklist**: verifies that the output is a genuine rebuild rather than a surface filter.
7. **Chinese and English versions** for RED Skill, GitHub, and different AI assistants.
8. **A GitHub-ready structure** with prompts, troubleshooting, example guidelines, contribution notes, and a changelog.

## Best input photos

Choose scenes with readable spatial structure:

- Streets, residential areas, parks, and campuses
- Malls, convenience stores, subway stations, parking lots, and stairwells
- Plazas, waterfronts, mountain paths, and courtyards
- Travel photos with a person inside a complete environment
- Food or objects that can be reinterpreted as game props

## Less suitable inputs

- Tight face-only selfies
- Photos with little or no background
- Images where the subject is tiny and the scene is unreadable
- Heavily retouched portraits
- Images requiring exact preservation of small text, logos, or signage

## Quick start

1. Upload a photo.
2. Tell the assistant: “Use the Reality Demake skill on this image.”
3. Unless otherwise requested, the skill defaults to:
   - preserving the original aspect ratio;
   - Standard intensity;
   - strict preservation of subject, composition, viewpoint, and spatial layout;
   - no added text, people, or unrelated objects.
4. If the first result misses the target, apply the relevant repair patch.

## Files

- `SKILL.md`: complete Chinese version and the primary RED Skill file.
- `SKILL.en.md`: complete English version.
- `prompts/`: full and compact copy-ready prompts.
- `docs/`: design principles, troubleshooting, and repair methods.
- `examples/`: naming and submission guidance for example images.
- `assets/`: repository banners, covers, and demo assets.

## Attribution and trademark notice

This project was initiated and released for free by **Cyber Traveler / 赛博旅者**.

“Source Engine,” “Half-Life 2,” and “Garry’s Mod” are referenced only to communicate a visual era and rendering character. This project is not affiliated with, endorsed by, or sponsored by Valve, Facepunch Studios, or any other rights holder. All trademarks belong to their respective owners.

## License

MIT License. You may use, modify, and redistribute the project, provided that the original copyright and license notice are retained.
