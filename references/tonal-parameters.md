# High-contrast directional-light parameters

Use this reference when the user asks for settings, a light-and-dark style block, or post-processing guidance. These values are starting points, not universal requirements; preserve the user's chosen model and interface.

## Visual target

- **Global contrast:** high, shaped by one clear directional key light and a readable deep shadow mass.
- **Detail density:** establish the large value masses first, then keep the amount of middle-scale environmental information needed to make the setting believable. Use foreground, subject, and background layers; reserve the finest detail for the focal face, hands, clothing silhouette, and a narrative anchor. Do not impose a fixed count of color blocks.
- **Shadow range:** dark and chromatic rather than crushed black; retain only essential reflected light and structure.
- **Highlight handling:** reserve near-white for the light source and small specular accents; protect broad bright surfaces from clipping.
- **Exposure shape:** avoid global high-key exposure and broad ambient fill unless explicitly requested.

## Reusable lighting block

```text
strong directional key light, cinematic chiaroscuro, clear light-shadow separation,
strong light-to-shadow ratio, one substantial deep chromatic shadow mass, dark tonal anchors,
minimal ambient fill and essential reflected color inside readable shadows,
warm ivory and soft silver bright surfaces, small controlled specular highlights only,
protected highlights, foreground midground and background, an environment-dominant composition,
a full-body medium-small character embedded in a believable setting,
coherent middle-scale environmental detail, selected material cues, focal detail only where the story needs it,
filmic high contrast, not harsh digital HDR
```

## Negative lighting block

```text
low contrast, flat lighting, evenly lit scene, uniform high-key exposure,
soft diffuse lighting, washed-out shadows, pale shadow values, no dark tonal anchor,
bright haze over the entire image, broad featureless white areas, clipped clouds, overexposed sky,
excessive ambient fill, excessive bloom, crushed blacks, pure black shadows,
plastic gloss, harsh digital HDR, oversharpening, excessive micro-texture,
oversized character, close-up portrait, character filling the frame,
flat composition, empty background, weak environment detail, inconsistent perspective,
random clutter, meaningless microtexture, repeated decorative details with no narrative purpose
```

## Diffusion starting values

For SDXL/Illustrious-style interfaces that expose these controls:

| Control | Starting value | Why |
| --- | --- | --- |
| Native canvas | long edge 1024–1344 px | Establishes the composition and shadow mass before fine detail. |
| Sampler | DPM++ 2M SDE Karras | A reliable starting point for directional high-contrast lighting. |
| Steps | 30–36 | Start near 32 to retain environmental structure and controlled middle-scale detail. |
| CFG | 5.5–6.5 | Start near 6.0; lower only if the image becomes rigid. |
| High-resolution pass | 1.4–1.5×, if needed | Use only after the base image has clear contrast, composition, and environmental hierarchy. |
| High-resolution denoise | 0.16–0.24 | Restores needed environmental information without turning every surface into texture. |
| Sharpening | low or off | Prefer the light/shadow boundary over texture sharpening. |

If the user's generator does not expose these controls, return the positive and negative lighting blocks only. Do not invent equivalent parameter names.

## Low-contrast correction starting values

Where an editor offers a basic tonal panel, begin here and adjust by eye:

| Control | Range |
| --- | ---: |
| Exposure | -0.3 |
| Highlights | -35 |
| Whites | -18 |
| Shadows | +5 to +10 |
| Blacks | +3 to +7 |
| Contrast | +12 |
| Texture / Clarity | -5 to +5 |

For a result that is uniformly too bright, first lower exposure and compress highlights; then open only enough shadow to retain hue and structure. Strengthen the light/shadow separation before adding texture. Do not use these corrections to create crushed blacks or clipped whites: the aim is a deep, legible tonal structure with clear lighting direction, not brittle HDR.

## Visual-noise correction starting values

Use these Lightroom / Camera Raw-style values when an image has the right scene and tonal structure but looks too fragmented. Values are starting points; controls vary between editors.

| Global control | Starting value | Purpose |
| --- | ---: | --- |
| Texture | `-5` to `-10` | Removes distracting material noise while preserving meaningful environmental information. |
| Clarity | `-3` to `-6` | Softens excessive local edge contrast without flattening the place. |
| Dehaze | `0` to `-2` | Prevents dry, over-separated digital detail. |
| Sharpening | `20` | Keeps a modest definition on purposeful edges. |
| Sharpening masking | `50` | Limits sharpening to meaningful edges without losing the setting. |
| Luminance noise reduction | `5` | Smooths high-frequency clutter gently. |
| Highlights | `-12` | Reduces distracting tiny reflective points. |

Then use two masks rather than softening the whole image:

| Mask | Texture | Clarity | Sharpening | Apply to |
| --- | ---: | ---: | ---: | --- |
| Background / secondary area | `-10` | `-5` | `5` | Plants, architecture, flooring, distant objects, and small props. |
| Focal subject | `0` to `+3` | `0` to `+3` | `20` | Face, hands, the main clothing silhouette, and one narrative prop. |

Stop when the subject remains legible at a small viewing size and the environment still explains where the moment happens. Do not blur the entire image, erase meaningful materials, or suppress the middle-scale forms that establish scale and story.
