---
name: soft-photo
description: Expand brief image ideas into strongly narrative Japanese-anime cinematic scenes, then create environmental illustration prompts with embedded characters, bold directional light, large shadow masses, and balanced visual detail. Use when the user asks for the soft_photo look or an anime image with poetic environmental storytelling; not for photorealistic photography or exact artist imitation.
metadata:
  short-description: Generate environmental anime-cinematic image prompts
---

# Soft Photo

Turn the user's scene into a flexible, model-compatible image prompt that retains the **soft_photo** visual language: Japanese anime environmental illustration, a character embedded in a visible story, emphatic directional filmic light, large readable shadow masses, credible material cues, graphic faces and hair, and a suspended emotional moment. Narrative is the first priority: the image should feel like one consequential frame from a film, not a beautiful character display in a decorative setting.

## Brief-to-scene expansion

When the user provides only a short visual idea rather than a precise prompt, do **not** generate an image or immediately turn it into a final prompt.

1. First return **two to five concise directions** for the same idea. Make their differences meaningful: for example composition and character scale, time/light/palette, degree of industrial versus natural contrast, or the implied narrative moment. Each direction must imply a different story tension, relationship, or unanswered question—not merely a different palette. Preserve every fact in the user's brief; do not treat illustrative examples as defaults.
2. After the user selects a direction—or asks you to choose one—read [references/description-expansion.md](references/description-expansion.md) and write one detailed Chinese scene expansion before generating. It should be a coherent visual paragraph at approximately the density of the user's examples, not a list of tags or a screenplay.
3. The expansion should establish, where relevant: character design and restrained pose; a concrete environment with meaningful lived-in or structural detail; one visual anchor; lighting direction and a high-contrast value relationship; palette and limited material cues; foreground/midground/background; lens, framing, and depth of field; and the quiet unresolved story implied by the image. Explicitly identify the visual cause or tension that makes this a story frame—an arrival, departure, danger, waiting, interruption, discovery, or other unresolved event. Detail must support place, scale, action, or emotion—not fill every surface.
4. Present the completed expansion to the user. Then read [references/cinematic-iteration.md](references/cinematic-iteration.md) and derive a concise method card from the expansion: choose the composition/camera method, depth method, lighting method, and the appropriate execution route. State the selected method with the prompt when it materially affects the result. Only then derive the positive prompt, negative prompt, and applicable parameters. If the user asked to create an image and an image-generation tool is available, use that derived prompt to generate only after the expansion and method selection have been shown. Otherwise, stop at the ready-to-use prompt.

If the user provides a full, precise scene description, skip the direction-choice stage unless they explicitly ask for ideation or expansion, but still consolidate the supplied details into a compact scene expansion and method card before writing the prompt.

## Prompt workflow

1. Preserve the requested subject, setting, action, emotion, weather, and framing. Do not add a fixed city, school uniform, character appearance, or narrative prop unless the user asks for it or selects it during the brief-to-scene expansion.
2. Assemble the prompt in the order in [references/prompt-template.md](references/prompt-template.md): subject and design, action, setting, environmental detail, one narrative anchor, composition, lens, lighting, palette, materials, then atmosphere and story. Make the narrative anchor actionable and visible; do not substitute vague words such as “dreamy” or “cinematic” for an implied event.
3. Select only the modules that materially support the requested narrative. Use [references/modular-prompt-library.md](references/modular-prompt-library.md) for scene, lens, light, palette, and narrative options. Select framing and lighting because they heighten the story tension, not only because they make the character attractive.
4. Prefer concrete visual descriptions and a small number of visual priorities over a long string of quality tags. Use Chinese by default; retain a small number of widely understood English camera terms only where they add precision.
5. Match the image model's syntax. Do not add weights or model names unless the user names a workflow. When the user asks for generation or post-processing settings, use [references/tonal-parameters.md](references/tonal-parameters.md) and label them as starting values rather than guarantees.
6. Include the negative prompt only when the generator supports one. Keep it focused on failures relevant to the requested image; remove any negative term that conflicts with the user's intent.

## Method matching after expansion

The expansion decides the method; do not apply a fixed visual recipe to every scene. After a full scene expansion, read [references/cinematic-iteration.md](references/cinematic-iteration.md) before writing the generation prompt. Extract the narrative state, subject's role in the frame, physical spatial structure, and required motion or stillness, then select:

1. one composition/camera method that best exposes the story relationship;
2. one depth and focus plan that separates the necessary planes;
3. one lighting and reflection plan that supports the story state; and
4. either a direct final prompt, a composition-search pass, or a staged iteration route.

Do not mix all available methods. Keep the selected route proportionate: a precise, low-risk request may go directly to a final prompt, while ambiguous camera relationships or a requested refinement should be resolved in the order composition → depth → light → detail. In an iterative route, preserve the decisions made in earlier rounds and change only the one to three variables belonging to the active round.

## Style invariants

- Japanese anime character rendering rather than literal photography: clean, relaxed linework, clearly animated facial proportions, readable anime eyes and irises, simplified nose and mouth, restrained semi-painterly color, and only the material detail needed to make the subject convincing.
- Face and hair stay graphic: describe a cel-shaded or simply painted face with a small number of clean facial planes and limited skin texture. Build hair from intentional locks, a clear outer silhouette, and value masses with a few controlled highlight ribbons; never prioritize pore detail, fuzzy individual hairs, subsurface skin rendering, or a 3D character-sculpt look.
- Character-design balance: favor a contemporary, approachable Japanese animation character with an everyday emotional read. Preserve the user’s requested outfit; let its silhouette read clearly before adding secondary ornament or functional design cues.
- Environment before display: default to a full-body medium-small or small character naturally embedded in the environment. Do not default to a close-up or oversized character unless the user explicitly asks for a portrait.
- Directional key light: establish a clear light-facing plane and shadow-facing plane. Use hard sunlight, a narrow window beam, a practical lamp, moonlight, or another explicit directional source; do not default to flat diffuse illumination. A request for “soft” rendering means soft linework or color transitions, never low-contrast or uniformly lit light.
- High global contrast: default to decisive cinematic contrast, with one substantial, readable deep chromatic shadow mass occupying a meaningful portion of the composition unless the user explicitly requests high-key lighting. The subject or a key element should cross the light/shadow boundary, so the contrast creates story tension and spatial hierarchy rather than merely darkening the scene.
- Deep chromatic shadows: avoid crushed pure black. Shadows stay decisively dark while retaining restrained cool gray, blue-green, olive, or warm brown information, reflected light, and essential structure.
- Controlled highlights: reserve near-white for the light source, a reflection, or a small specular accent. Use glass, water, metal, fabric, or reflected light only when those material cues help establish the place or the story.
- Minimal fill, not haze: use only enough bounce light to retain form inside shadow. Avoid broad ambient fill, overall misty glow, or equal brightness across the whole frame.
- Environmental storytelling: every scene should establish foreground, subject plane, and background depth. The setting, weather, architecture, and a small number of meaningful props must imply a story rather than decorate a character display. The frame should make the viewer ask what just happened, what is about to happen, or why the character is here.
- Detail hierarchy: establish large value relationships first, then render as much middle-scale environmental information as the selected setting needs. Keep the focal face, hands, and important prop clearest; group only details that do not carry setting, scale, or narrative information.
- A camera-aware composition: choose a Dutch angle, wide-angle perspective, low/high angle, shallow depth of field, or motion blur only when it reinforces the requested mood, action, or narrative tension. Use foreground occlusion, negative space, a deep shadow frame, or an off-center subject when they make the image read as a cinematic story frame. A calm, level composition is equally valid only when its stillness itself carries the story.
- Natural physical detail: choose one or two interactions—such as wind in hair, a moving hem, a kite line, or a reflection—instead of adding every possible effect.
- Narrative stillness: prefer a suspended, unexplained moment—waiting, observing, arriving, departing, floating, or being dwarfed by a larger world—over an isolated character pose. Let the image feel like a frame from the middle of a story, with a concrete visual clue to the before or after of that moment.

## Narrative and cinematic gate

Before returning a prompt or generating, verify that the image has all of the following:

- A visible narrative trigger or unresolved relationship, expressed through action, scale, environment, or a meaningful prop.
- A composition that prioritizes the story beat over a centered character showcase.
- A clear directional key light and a large, chromatic shadow mass; “soft” must never flatten the value structure.
- A readable light-versus-shadow crossing on the character, action, or visual anchor.

If any item is missing, revise the scene expansion and prompt before generating. Favor a single clear story tension over adding decorative detail.

## Output

For a precise request, return a ready-to-paste positive prompt and, if useful, a negative prompt. For a brief request, follow the brief-to-scene expansion before returning the prompt or generating. In either case, make the narrative trigger, cinematic composition, large shadow mass, and directional contrast explicit in the prompt. When the user asks for parameters, include the applicable starting values from the tonal-parameters reference. State the recommended aspect ratio only when it is implied by the request or would materially improve composition.

For prompt assembly, read [references/prompt-template.md](references/prompt-template.md). After every completed scene expansion, read [references/cinematic-iteration.md](references/cinematic-iteration.md) to match the scene to its composition, depth, lighting, and iteration method. For selectable scene and narrative modules, read [references/modular-prompt-library.md](references/modular-prompt-library.md). For brief-to-scene expansion, read [references/description-expansion.md](references/description-expansion.md). For tonal controls and diffusion settings, read [references/tonal-parameters.md](references/tonal-parameters.md).
