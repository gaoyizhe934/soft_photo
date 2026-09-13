---
name: soft-photo
description: Create anime-cinematic illustrations with luminous natural light, dynamic photography-inspired composition, and detailed environmental storytelling. Use when the user asks for the soft_photo look or an anime image in this airy, cinematic style; not for photorealistic photography or exact artist imitation.
metadata:
  short-description: Generate airy anime-cinematic image prompts
---

# Soft Photo

Turn the user's scene into a flexible, model-compatible image prompt that retains the **soft_photo** visual language: animated-film illustration, luminous daylight, spatial depth, and an energetic camera.

## Prompt workflow

1. Preserve the requested subject, setting, action, emotion, weather, and framing. Do not add a fixed city, school uniform, or character appearance unless the user asks for it.
2. Use the compact base prompt in [references/prompt-template.md](references/prompt-template.md). Replace only the bracketed fields, then add one optional composition or lighting module when it supports the scene.
3. Prefer concrete visual descriptions over a long string of quality tags. Use Chinese by default; retain a small number of widely understood English camera terms only where they add precision.
4. Match the image model's syntax. Do not add weights, model names, sampler settings, or artist names unless the user names a specific supported workflow.
5. Include the negative prompt only when the generator supports one. Keep it focused on failures relevant to the requested image; remove any negative term that conflicts with the user's intent.

## Style invariants

- Anime-cinematic illustration rather than literal photography: clean expressive linework, softly painted color transitions, and credible material detail.
- Directional natural light: edge light, dappled shadows, reflected highlights, atmosphere, and controlled lens flare when the sun is visible.
- A readable subject inside a rich setting: build foreground, subject plane, and background depth without letting background detail obscure the face or action.
- A camera-aware composition: use a Dutch angle, wide-angle perspective, low/high angle, shallow depth of field, or foreground motion blur only if it reinforces the requested mood or motion.
- Lively physical detail: wind in hair and clothing, drifting paper, reflections, or moving crowds when appropriate—not all effects in every image.

## Output

Return a ready-to-paste positive prompt and, if useful, a negative prompt. State the recommended aspect ratio only when it is implied by the request or would materially improve composition.

For templates and optional modules, read [references/prompt-template.md](references/prompt-template.md).
