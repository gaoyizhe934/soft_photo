---
name: soft-photo
description: Expand brief image ideas into strongly narrative Japanese-anime cinematic scenes, then create environmental illustration prompts with embedded characters, bold directional light, large shadow masses, and balanced visual detail. Use when the user asks for the soft_photo look or an anime image with poetic environmental storytelling; not for photorealistic photography or exact artist imitation.
metadata:
  short-description: Generate environmental anime-cinematic image prompts
---

# Soft Photo

Turn the user's scene into a flexible, model-compatible image prompt that retains the **soft_photo** visual language: Japanese anime environmental illustration, a character embedded in a visible story, emphatic directional filmic light, large readable shadow masses, credible material cues, graphic faces and hair, and a suspended emotional moment. Narrative is the first priority: the image should feel like one consequential frame from a film, not a beautiful character display in a decorative setting.

## Brief-to-scene expansion

When the user provides only a short visual idea rather than a precise prompt, first offer meaningful directions instead of immediately generating. **Once the user selects a direction, treat that selection as authorization to complete the full image workflow without pausing.**

1. First return **two to five concise directions** for the same idea. Make their differences meaningful: for example composition and character scale, time/light/palette, degree of industrial versus natural contrast, or the implied narrative moment. Each direction must imply a different story tension, relationship, or unanswered question—not merely a different palette. Preserve every fact in the user's brief; do not treat illustrative examples as defaults.
2. After the user selects a direction—or asks you to choose one—read [references/description-expansion.md](references/description-expansion.md) and write one detailed Chinese scene expansion before generating. It should be a coherent visual paragraph at approximately the density of the user's examples, not a list of tags or a screenplay.
3. The expansion should establish, where relevant: character design and restrained pose; a concrete environment with meaningful lived-in or structural detail; one visual anchor; lighting direction and a high-contrast value relationship; palette and limited material cues; foreground/midground/background; lens, framing, and depth of field; and the quiet unresolved story implied by the image. Explicitly identify the visual cause or tension that makes this a story frame—an arrival, departure, danger, waiting, interruption, discovery, or other unresolved event. Detail must support place, scale, action, or emotion—not fill every surface.
4. After a direction is selected, complete the rest of the workflow **in the same turn and without asking for another confirmation**: write the expansion, derive the method card, fill the applicable presets, assemble the complete positive and focused negative prompt, generate the image when an image-generation tool is available, inspect it, and make any needed targeted revision. A concise progress update or a compact summary of the expansion and method is allowed, but it must not become a blocking handoff to the user. Do not wait for the user to separately say “continue,” “write the prompt,” or “generate.” Stop only when the final image passes the relevant checks, the generation tool is unavailable, or a genuinely material user choice is required.

If the user provides a full, precise scene description, skip the direction-choice stage unless they explicitly ask for ideation or expansion, but still consolidate the supplied details into a compact scene expansion and method card before writing the prompt and generating the image. If they do request directions, their selection likewise starts the non-stop completion flow.

## Direction selection starts end-to-end execution

For a direction-menu request, the only normal decision gate is the user's choice of direction. From that point, execute this sequence automatically and in order:

1. cinematic Chinese scene expansion, classified before writing: for a monumental scene, deliberately expand scale, spatial relationships, environmental forces, and the unresolved narrative into an approximately 700-Chinese-character brief; for an everyday scene, expand the ordinary setting into an approximately 500-Chinese-character brief using cinematic photographic narration—camera position, visible cause-and-effect, spatial blocking, light, and a suspended story beat—then proceed to the method card;
2. method card;
3. scene, composition/camera, background, character (if present), lighting, and calibration preset cards;
4. synthesize one final generation prompt from the selected preset-card constraints together with the scene-expansion details; resolve conflicts in favor of the user’s brief and the expansion’s narrative, spatial, and lighting decisions, then include a focused negative prompt only when the chosen generator supports it;
5. image generation;
6. visual inspection against the selected cards and cinematic/narrative gates; and
7. one mandatory audit-and-repair pass, whether or not the first inspection finds a failure: identify the most consequential improvement in composition, depth, lighting, background detail, character acting, or integration; make one focused revision affecting at most one to three fields, regenerate, and recheck while preserving every passing earlier-stage constraint.

Do not end a turn after steps 1–4, and do not ask whether to begin the next step. Keep the user informed with short non-blocking commentary while work runs. A direction selection grants permission for ordinary, reversible generation and in-scope iteration; it does not authorize unrelated file changes, publishing, or external actions. If a material creative ambiguity remains after the selection, choose the most evidence-based interpretation from the selected direction; ask only when that ambiguity would substantially change the requested result.

## Prompt workflow

1. Preserve the requested subject, setting, action, emotion, weather, and framing. Do not add a fixed city, school uniform, character appearance, or narrative prop unless the user asks for it or selects it during the brief-to-scene expansion.
2. Assemble the prompt in the order in [references/prompt-template.md](references/prompt-template.md): subject and design, action, setting, environmental detail, one narrative anchor, composition, lens, lighting, palette, materials, then atmosphere and story. Make the narrative anchor actionable and visible; do not substitute vague words such as “dreamy” or “cinematic” for an implied event.
3. Select only the modules that materially support the requested narrative. Use [references/modular-prompt-library.md](references/modular-prompt-library.md) for scene, lens, light, palette, and narrative options. Select framing and lighting because they heighten the story tension, not only because they make the character attractive.
4. After selecting the method, read [presets/cinematic-parameters.md](presets/cinematic-parameters.md). Fill one concise parameter preset card from the expansion and method card, then translate only its relevant values into prompt constraints. The preset card is semantic prompt control, not an excuse to invent model-specific settings. After a direction choice, proceed directly to the remaining cards, prompt, generation, and inspection rather than presenting this card as a stopping point.
5. Read [presets/composition-camera.md](presets/composition-camera.md) for every scene and fill its camera/composition card before writing the prompt. Choose one matching preset or a restrained custom card; use camera, subject scale, perspective, foreground, negative space, and large value shapes to make the story readable.
6. Read [presets/background-details.md](presets/background-details.md) and fill one matching environment-detail card. Translate only its macro structure, medium-scale functional detail, material families, density falloff, and focal buffer into the prompt; never use micro-detail as a substitute for environment design.
7. Read [presets/character-parameters.md](presets/character-parameters.md) and fill a compact character card from the user’s requested character and the expansion. Select only the fields that make the character’s acting, silhouette, motion, and lighting legible in this scene.
8. Before each generation and when judging its result, use [presets/reference-urban-staircase-black-hair.md](presets/reference-urban-staircase-black-hair.md) as a calibration card. Compare only the requested or scene-relevant dimensions; it is not a default character design and must not add its black hair, white outfit, flower, cats, or setting unless the user asks for them.
9. For every scene, read [presets/urban-hard-sun-shadows.md](presets/urban-hard-sun-shadows.md) and match its universal lighting card to the actual source: hard sun, window/door light, practical artificial light, moonlight, overcast light, or another explicit source. Use the hard-sun branch only when its physical preconditions hold.
10. Prefer concrete visual descriptions and a small number of visual priorities over a long string of quality tags. Use Chinese by default; retain a small number of widely understood English camera terms only where they add precision.
11. Match the image model's syntax. Do not add weights or model names unless the user names a workflow. When the user asks for generation or post-processing settings, use [references/tonal-parameters.md](references/tonal-parameters.md) and label them as starting values rather than guarantees.
12. Include the negative prompt only when the generator supports one. Keep it focused on failures relevant to the requested image; remove any negative term that conflicts with the user's intent.

## Method matching after expansion

The expansion decides the method; do not apply a fixed visual recipe to every scene. After a full scene expansion, read [references/cinematic-iteration.md](references/cinematic-iteration.md) before writing the generation prompt. Extract the narrative state, subject's role in the frame, physical spatial structure, and required motion or stillness, then select:

1. one composition/camera method that best exposes the story relationship;
2. one depth and focus plan that separates the necessary planes;
3. one lighting and reflection plan that supports the story state; and
4. either a direct final prompt, a composition-search pass, or a staged iteration route.

Do not mix all available methods. Keep the selected route proportionate: a precise, low-risk request may go directly to a final prompt, while ambiguous camera relationships or a requested refinement should be resolved in the order composition → depth → light → detail. In an iterative route, preserve the decisions made in earlier rounds and change only the one to three variables belonging to the active round.

## Closed-loop generation and optimization

After showing the expansion, select scene, camera, background, character, and lighting presets strictly from the expanded text. For each selected preset, compare the relevant dimensions with the stored urban-staircase example: retain only transferable execution qualities and explicitly discard unmatched appearance or setting traits. Merge the expansion, method card, selected preset cards, constraints, and focused negative prompt into one complete generation prompt.

Generate from that complete prompt, then inspect the result against the selected cards and the required narrative/cinematic gates. Record only concrete failures or the most consequential remaining opportunity across composition/camera, space/depth, lighting/shadow, background detail, character acting, or subject integration. Always perform exactly one audit-and-repair revision, even when the first result passes: choose the highest-priority applicable category, change at most one to three fields, preserve all earlier passing constraints, regenerate, and recheck. Follow the order composition → depth → lighting → background detail → character detail; never repair a late-stage defect by reopening a passing earlier stage. Do not pause between these phases for approval. Stop once the audit-and-repair result passes the applicable checks, the tool cannot continue, or a remaining choice genuinely requires user direction.

## Parameter presets

After method matching, use [presets/cinematic-parameters.md](presets/cinematic-parameters.md) to turn the selected method into a small parameter preset card. Fill the card with the values that follow from the expansion; then use it to constrain prompt assembly and, when applicable, the next iteration. Do not expose unsupported entries as generator controls, and do not fill a field whose value is not supported by the scene.

## Composition and camera presets

For every scene, use [presets/composition-camera.md](presets/composition-camera.md) to choose the camera before detail: aspect ratio, lens width, height, pitch, perspective, subject scale and position, foreground, depth, negative space, leading lines, and major light/dark shapes. The composition card is a prompt constraint, not a claim that the generator exposes literal camera controls. Before accepting a result, apply its thumbnail, silhouette, look-room, depth, and poster-versus-film-still checks.

## Background detail presets

For every scene, use [presets/background-details.md](presets/background-details.md) after the composition card. Choose one preset that matches the setting, preserve a clear macro-to-micro hierarchy, cluster detail around functional or narrative structures, reduce detail near the focal silhouette, and simplify distant objects. Judge background success by spatial readability and story support—not by how many tiny objects or readable labels it contains.

## Character presets and reference calibration

Use [presets/character-parameters.md](presets/character-parameters.md) after the scene expansion to create a compact character card. Treat character presence, gaze, pose, action, silhouette, fabric behavior, character lighting, and camera awareness as linked decisions rather than a list of appearance tags. Preserve the user’s explicit character description over any preset.

For every generation, compare the intended character card and the result against the execution criteria in [presets/reference-urban-staircase-black-hair.md](presets/reference-urban-staircase-black-hair.md): environmental integration, natural acting, silhouette clarity, hair/fabric motion, selective lighting, and subject–environment separation. When a reference image is supplied or the user asks to match it, compare its requested traits directly; otherwise use only the calibration criteria, never the example’s identity or props. If calibration finds a meaningful failure, change at most one to three character or scene variables in the next iteration.

## Universal cinematic light-and-shadow preset

For every scene, use [presets/urban-hard-sun-shadows.md](presets/urban-hard-sun-shadows.md) to choose a physically appropriate source branch while preserving its four-level value structure, cast-shadow/form-shadow distinction, readable darks, controlled highlights, and local contact shadows. Direct outdoor sunlight uses the hard-sun branch; other scenes must adapt the source, softness, temperature, and reflection rather than pretending sunlight is present. The preset never mandates stairs, cats, white clothing, or any other sample-specific element.

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

For a direction-menu request, initially return only the direction choices. After the user selects one, generate and deliver the final image in that same turn; include the expansion, method, prompt, and preset information only as compact supporting context, never as a reason to stop before generation. For a precise request, generate directly after the required compact expansion and method matching. In either case, make the narrative trigger, cinematic composition, large shadow mass, and directional contrast explicit in the prompt. When the user asks for parameters, include the applicable starting values from the tonal-parameters reference. State the recommended aspect ratio only when it is implied by the request or would materially improve composition.

For prompt assembly, read [references/prompt-template.md](references/prompt-template.md). After every completed scene expansion, read [references/cinematic-iteration.md](references/cinematic-iteration.md) to match the scene to its composition, depth, lighting, and iteration method, then read [presets/cinematic-parameters.md](presets/cinematic-parameters.md), [presets/composition-camera.md](presets/composition-camera.md), [presets/background-details.md](presets/background-details.md), [presets/character-parameters.md](presets/character-parameters.md), and [presets/urban-hard-sun-shadows.md](presets/urban-hard-sun-shadows.md) to fill compatible constraints. For every generation, use [presets/reference-urban-staircase-black-hair.md](presets/reference-urban-staircase-black-hair.md) for relevant-dimension calibration. For selectable scene and narrative modules, read [references/modular-prompt-library.md](references/modular-prompt-library.md). For brief-to-scene expansion, read [references/description-expansion.md](references/description-expansion.md). For tonal controls and diffusion settings, read [references/tonal-parameters.md](references/tonal-parameters.md).
