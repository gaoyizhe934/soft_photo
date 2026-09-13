---
name: soft-photo
description: Create anime-cinematic illustrations with soft natural light, restrained visual detail, and balanced photography-inspired composition. Use when the user asks for the soft_photo look or an anime image in this airy, understated style; not for photorealistic photography or exact artist imitation.
metadata:
  short-description: Generate airy anime-cinematic image prompts
---

# Soft Photo

Turn the user's scene into a flexible, model-compatible image prompt that retains the **soft_photo** visual language: animated-film illustration, gentle daylight, breathing room, and natural movement.

## Prompt workflow

1. Preserve the requested subject, setting, action, emotion, weather, and framing. Do not add a fixed city, school uniform, or character appearance unless the user asks for it.
2. Use the compact base prompt in [references/prompt-template.md](references/prompt-template.md). Replace only the bracketed fields; add at most one or two optional modules when they clearly support the scene.
3. Prefer concrete visual descriptions and a small number of visual priorities over a long string of quality tags. Use Chinese by default; retain a small number of widely understood English camera terms only where they add precision.
4. Match the image model's syntax. Do not add weights, model names, sampler settings, or artist names unless the user names a specific supported workflow.
5. Include the negative prompt only when the generator supports one. Keep it focused on failures relevant to the requested image; remove any negative term that conflicts with the user's intent.

## Style invariants

- Anime-cinematic illustration rather than literal photography: clear, relaxed linework, softly painted color transitions, and only the material detail needed to make the subject convincing.
- Soft natural light: broad, gentle tonal transitions and readable midtones. Use rim light, glare, dappled shadow, or flare sparingly; never stack them merely to make the image more spectacular.
- A readable subject inside a selective setting: establish foreground, subject plane, and background depth with a few meaningful forms. Preserve empty sky, wall, water, or shadow when it gives the composition room to breathe.
- A camera-aware composition: choose a Dutch angle, wide-angle perspective, low/high angle, shallow depth of field, or motion blur only when it reinforces the requested mood or motion. A calm, level composition is equally valid.
- Natural physical detail: choose one or two interactions—such as wind in hair, a moving hem, a kite line, or a reflection—instead of adding every possible effect.
- Coherence over density: do not render every surface equally sharp, textured, reflective, or decorated. Let secondary areas simplify and let the focal subject carry the detail.

## Output

Return a ready-to-paste positive prompt and, if useful, a negative prompt. State the recommended aspect ratio only when it is implied by the request or would materially improve composition.

For templates and optional modules, read [references/prompt-template.md](references/prompt-template.md).
