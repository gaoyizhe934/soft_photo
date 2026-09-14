---
name: soft-photo
description: Create Japanese-anime cinematic environmental illustrations with narrative settings, small-to-medium characters embedded in space, selective directional light, and balanced visual detail. Use when the user asks for the soft_photo look or an anime image with poetic environmental storytelling; not for photorealistic photography or exact artist imitation.
metadata:
  short-description: Generate environmental anime-cinematic image prompts
---

# Soft Photo

Turn the user's scene into a flexible, model-compatible image prompt that retains the **soft_photo** visual language: Japanese anime environmental illustration, a character embedded in narrative space, directional filmic light, credible material cues, graphic faces and hair, and a suspended emotional moment.

## Prompt workflow

1. Preserve the requested subject, setting, action, emotion, weather, and framing. Do not add a fixed city, school uniform, or character appearance unless the user asks for it.
2. Assemble the prompt in the order in [references/prompt-template.md](references/prompt-template.md): subject and design, action, setting, environmental detail, one narrative anchor, composition, lens, lighting, palette, materials, then atmosphere and story.
3. Select only the modules that materially support the requested narrative. Use [references/modular-prompt-library.md](references/modular-prompt-library.md) for scene, lens, light, palette, and narrative options.
4. Prefer concrete visual descriptions and a small number of visual priorities over a long string of quality tags. Use Chinese by default; retain a small number of widely understood English camera terms only where they add precision.
5. Match the image model's syntax. Do not add weights or model names unless the user names a workflow. When the user asks for generation or post-processing settings, use [references/tonal-parameters.md](references/tonal-parameters.md) and label them as starting values rather than guarantees.
6. Include the negative prompt only when the generator supports one. Keep it focused on failures relevant to the requested image; remove any negative term that conflicts with the user's intent.

## Style invariants

- Japanese anime character rendering rather than literal photography: clean, relaxed linework, clearly animated facial proportions, readable anime eyes and irises, simplified nose and mouth, restrained semi-painterly color, and only the material detail needed to make the subject convincing.
- Face and hair stay graphic: describe a cel-shaded or simply painted face with a small number of clean facial planes and limited skin texture. Build hair from intentional locks, a clear outer silhouette, and value masses with a few controlled highlight ribbons; never prioritize pore detail, fuzzy individual hairs, subsurface skin rendering, or a 3D character-sculpt look.
- Character-design balance: favor a contemporary, approachable Japanese animation character with an everyday emotional read. Preserve the user’s requested outfit; let its silhouette read clearly before adding secondary ornament or functional design cues.
- Environment before display: default to a full-body medium-small or small character naturally embedded in the environment. Do not default to a close-up or oversized character unless the user explicitly asks for a portrait.
- Directional key light: establish a clear light-facing plane and shadow-facing plane. Use hard sunlight, a narrow window beam, a practical lamp, or another explicit directional source; do not default to flat diffuse illumination.
- High global contrast: preserve one substantial, readable deep shadow mass unless the user explicitly requests high-key lighting. The subject or a key element should cross the light/shadow boundary, so the contrast shapes the composition rather than merely darkening it.
- Deep chromatic shadows: avoid crushed pure black. Shadows stay decisively dark while retaining restrained cool gray, blue-green, olive, or warm brown information, reflected light, and essential structure.
- Controlled highlights: reserve near-white for the light source, a reflection, or a small specular accent. Use glass, water, metal, fabric, or reflected light only when those material cues help establish the place or the story.
- Minimal fill, not haze: use only enough bounce light to retain form inside shadow. Avoid broad ambient fill, overall misty glow, or equal brightness across the whole frame.
- Environmental storytelling: every scene should establish foreground, subject plane, and background depth. The setting, weather, architecture, and a small number of meaningful props should imply a story rather than decorate a character display.
- Detail hierarchy: establish large value relationships first, then render as much middle-scale environmental information as the selected setting needs. Keep the focal face, hands, and important prop clearest; group only details that do not carry setting, scale, or narrative information.
- A camera-aware composition: choose a Dutch angle, wide-angle perspective, low/high angle, shallow depth of field, or motion blur only when it reinforces the requested mood or motion. A calm, level composition is equally valid.
- Natural physical detail: choose one or two interactions—such as wind in hair, a moving hem, a kite line, or a reflection—instead of adding every possible effect.
- Narrative stillness: prefer a suspended, unexplained moment—waiting, observing, arriving, departing, floating, or being dwarfed by a larger world—over an isolated character pose. Let the image feel like a frame from the middle of a story.

## Output

Return a ready-to-paste positive prompt and, if useful, a negative prompt. When the user asks for parameters, include the applicable starting values from the tonal-parameters reference. State the recommended aspect ratio only when it is implied by the request or would materially improve composition.

For prompt assembly, read [references/prompt-template.md](references/prompt-template.md). For selectable scene and narrative modules, read [references/modular-prompt-library.md](references/modular-prompt-library.md). For tonal controls and diffusion settings, read [references/tonal-parameters.md](references/tonal-parameters.md).
