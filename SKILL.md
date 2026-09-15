---
name: soft-photo
description: Expand brief image ideas into strongly narrative Japanese-anime cinematic scenes, then create environmental illustration prompts with embedded characters, bold directional light, large shadow masses, and balanced visual detail. Use when the user asks for the soft_photo look or an anime image with poetic environmental storytelling; not for photorealistic photography or exact artist imitation.
metadata:
  short-description: Generate environmental anime-cinematic image prompts
---

# Soft Photo

Turn the user's scene into a flexible, model-compatible image prompt that retains the **soft_photo** visual language: Japanese anime environmental illustration, a character embedded in a visible story, emphatic directional filmic light, large readable shadow masses, credible material cues, graphic faces and hair, and a suspended emotional moment. Narrative is the first priority: the image should feel like one consequential frame from a film, not a beautiful character display in a decorative setting.

## Execution directory and progress

Use this directory for every request. After completing each stage, reread it, identify the next stage, and continue unless the directory explicitly requires the user's selection or a genuinely material choice cannot be resolved safely.

```text
User input prompt, regardless of length
  → read and understand
  → offer 10 derivative expansion directions
  → user selects one direction
  → classify the selected scene as everyday or monumental
  → expand according to scene type
  → match examples and select parameters from the expansion
  → combine expansion and parameters into one final prompt
  → generate from the final prompt
  → inspect the generated image; strictly audit every selected parameter and requirement, then repair it
  → generate and deliver the final image
```

The only normal user interactions are the original prompt and one direction selection. Do not ask the user to confirm expansion, parameter selection, prompt assembly, generation, inspection, repair, or delivery. Maintain rigorous internal reasoning; in user-visible commentary, report the active directory stage, a concise execution summary, and truthful current progress as a percentage without exposing private chain-of-thought. Use: stages 1–2 = 0–20%, selection = 20–25%, expansion = 25–40%, parameters = 40–55%, final prompt = 55–65%, first generation = 65–75%, audit and repair = 75–95%, final delivery = 100%.

## 1. Read and understand the user prompt

Read the whole prompt regardless of length. Preserve every stated subject, setting, action, emotion, weather, framing, and visual constraint. Distinguish explicit facts from safe genre inferences, but do not add a fixed city, character appearance, costume, or narrative prop as a hidden default.

## 2. Offer 10 derivative expansion directions

Always return exactly **10** concise, meaningfully different directions before generating, including when the user supplies a full and precise prompt. Every direction must preserve the user's facts while varying consequential choices such as character-to-environment scale, camera relationship, time and light, spatial structure, narrative tension, or unanswered story beat—not merely palette. Initially return only the 10 numbered directions and current progress.

## 3. Receive the user's direction selection

The user's selection—or an explicit instruction for the skill to choose—is the only normal decision gate. Treat it as authorization to execute all remaining stages in the same turn. Reread the execution directory and proceed immediately; do not ask a second confirmation or stop after expansion, cards, prompt, generation, inspection, or repair.

## 4. Classify and expand the selected scene

Read [references/description-expansion.md](references/description-expansion.md), then classify the scene before writing: for a **monumental** scene, deliberately expand scale, spatial relationships, environmental forces, layered structures, visual anchor, and unresolved narrative into an approximately 700-Chinese-character cinematic paragraph; for an **everyday** scene, write an approximately 500-Chinese-character cinematic-photographic paragraph using camera position, visible cause and effect, spatial blocking, directional light, environmental detail, and a suspended story beat.

The expansion must establish, where relevant: restrained character design and natural pose; a concrete environment; one visible narrative anchor; foreground/midground/background; lens, framing, and depth; explicit directional light; a high-contrast value relationship; deep chromatic readable shadows; controlled highlights; and a concrete unresolved trigger such as arrival, departure, danger, waiting, interruption, discovery, or aftermath. It is one coherent Chinese visual paragraph, never a tag list or screenplay. Detail must support place, scale, action, or emotion rather than fill every surface.

## 5. Match examples and select parameters

1. Preserve the requested subject, setting, action, emotion, weather, and framing. Do not add a fixed city, school uniform, character appearance, or narrative prop unless the user asks for it or it is selected during the direction-and-expansion stages.
2. Read [references/cinematic-iteration.md](references/cinematic-iteration.md) and derive the narrative state, subject role, physical spatial structure, required motion or stillness, and a direct-final, composition-search, or staged-iteration route from the expansion.
3. Read [references/modular-prompt-library.md](references/modular-prompt-library.md) and select only scene, lens, lighting, palette, and narrative modules that materially support the chosen story.
4. After selecting the method, read [presets/cinematic-parameters.md](presets/cinematic-parameters.md). Fill one concise parameter preset card from the expansion and method card, then translate only its relevant values into prompt constraints. The preset card is semantic prompt control, not an excuse to invent model-specific settings. After a direction choice, proceed directly to the remaining cards, prompt, generation, and inspection rather than presenting this card as a stopping point.
5. Read [presets/composition-camera.md](presets/composition-camera.md) for every scene and fill its camera/composition card before writing the prompt. Choose one matching preset or a restrained custom card; use camera, subject scale, perspective, foreground, negative space, and large value shapes to make the story readable.
6. Read [presets/background-details.md](presets/background-details.md) and fill one matching environment-detail card. Translate only its macro structure, medium-scale functional detail, material families, density falloff, and focal buffer into the prompt; never use micro-detail as a substitute for environment design.
7. Read [presets/character-parameters.md](presets/character-parameters.md) and fill a compact character card from the user’s requested character and the expansion. Select only the fields that make the character’s acting, silhouette, motion, and lighting legible in this scene.
8. Before each generation and when judging its result, use [presets/reference-urban-staircase-black-hair.md](presets/reference-urban-staircase-black-hair.md) as a calibration card. Compare only the requested or scene-relevant dimensions; it is not a default character design and must not add its black hair, white outfit, flower, cats, or setting unless the user asks for them.
9. For every scene, read [presets/urban-hard-sun-shadows.md](presets/urban-hard-sun-shadows.md) and match its universal lighting card to the actual source: hard sun, window/door light, practical artificial light, moonlight, overcast light, or another explicit source. Use the hard-sun branch only when its physical preconditions hold.
10. Prefer concrete visual descriptions and a small number of visual priorities over a long string of quality tags. Use Chinese by default; retain a small number of widely understood English camera terms only where they add precision.
11. Match the image model's syntax. Do not add weights or model names unless the user names a workflow. When the user asks for generation or post-processing settings, use [references/tonal-parameters.md](references/tonal-parameters.md) and label them as starting values rather than guarantees.
12. Include the negative prompt only when the generator supports one. Keep it focused on failures relevant to the requested image; remove any negative term that conflicts with the user's intent.

### Method matching after expansion

The expansion decides the method; do not apply a fixed visual recipe to every scene. After a full scene expansion, read [references/cinematic-iteration.md](references/cinematic-iteration.md) before writing the generation prompt. Extract the narrative state, subject's role in the frame, physical spatial structure, and required motion or stillness, then select:

1. one composition/camera method that best exposes the story relationship;
2. one depth and focus plan that separates the necessary planes;
3. one lighting and reflection plan that supports the story state; and
4. either a direct final prompt, a composition-search pass, or a staged iteration route.

Do not mix all available methods. Keep the selected route proportionate: a precise, low-risk request may go directly to a final prompt, while ambiguous camera relationships or a requested refinement should be resolved in the order composition → depth → light → detail. In an iterative route, preserve the decisions made in earlier rounds and change only the one to three variables belonging to the active round.

### Consolidate selected cards

After showing the expansion, select scene, camera, background, character, and lighting presets strictly from the expanded text. For each selected preset, compare the relevant dimensions with the stored urban-staircase example: retain only transferable execution qualities and explicitly discard unmatched appearance or setting traits. Lock the compatible expansion details, method card, preset cards, and constraints for final prompt assembly.

Use the locked information only for the final prompt and later audit. Do not reopen a passing composition, depth, or lighting decision for decorative detail.

### Parameter presets

After method matching, use [presets/cinematic-parameters.md](presets/cinematic-parameters.md) to turn the selected method into a small parameter preset card. Fill the card with the values that follow from the expansion; then use it to constrain prompt assembly and, when applicable, the next iteration. Do not expose unsupported entries as generator controls, and do not fill a field whose value is not supported by the scene.

### Composition and camera presets

For every scene, use [presets/composition-camera.md](presets/composition-camera.md) to choose the camera before detail: aspect ratio, lens width, height, pitch, perspective, subject scale and position, foreground, depth, negative space, leading lines, and major light/dark shapes. The composition card is a prompt constraint, not a claim that the generator exposes literal camera controls. Before accepting a result, apply its thumbnail, silhouette, look-room, depth, and poster-versus-film-still checks.

### Background detail presets

For every scene, use [presets/background-details.md](presets/background-details.md) after the composition card. Choose one preset that matches the setting, preserve a clear macro-to-micro hierarchy, cluster detail around functional or narrative structures, reduce detail near the focal silhouette, and simplify distant objects. Judge background success by spatial readability and story support—not by how many tiny objects or readable labels it contains.

### Character presets and reference calibration

Use [presets/character-parameters.md](presets/character-parameters.md) after the scene expansion to create a compact character card. Treat character presence, gaze, pose, action, silhouette, fabric behavior, character lighting, and camera awareness as linked decisions rather than a list of appearance tags. Preserve the user’s explicit character description over any preset.

For every generation, compare the intended character card and the result against the execution criteria in [presets/reference-urban-staircase-black-hair.md](presets/reference-urban-staircase-black-hair.md): environmental integration, natural acting, silhouette clarity, hair/fabric motion, selective lighting, and subject–environment separation. When a reference image is supplied or the user asks to match it, compare its requested traits directly; otherwise use only the calibration criteria, never the example’s identity or props. If calibration finds a meaningful failure, change at most one to three character or scene variables in the next iteration.

### Universal cinematic light-and-shadow preset

For every scene, use [presets/urban-hard-sun-shadows.md](presets/urban-hard-sun-shadows.md) to choose a physically appropriate source branch while preserving its four-level value structure, cast-shadow/form-shadow distinction, readable darks, controlled highlights, and local contact shadows. Direct outdoor sunlight uses the hard-sun branch; other scenes must adapt the source, softness, temperature, and reflection rather than pretending sunlight is present. The preset never mandates stairs, cats, white clothing, or any other sample-specific element.

## 6. Combine expansion and parameters into one final prompt

Reread the execution directory and read [references/prompt-template.md](references/prompt-template.md). Synthesize one final generation prompt from the user's brief, selected direction, cinematic expansion, method card, locked preset-card constraints, and applicable modules. Resolve conflicts in favor of the user's explicit brief, then the expansion's narrative, spatial, and lighting decisions. Assemble the prompt in this order: subject and design, action, setting, environmental detail, visible narrative anchor, composition and lens, lighting and value structure, palette and materials, then atmosphere and unresolved story. Make the narrative anchor actionable and visible; never substitute vague words such as “dreamy” or “cinematic” for an implied event.

Use Chinese by default; retain English camera or generator terms only where they add precision. Include a focused negative prompt only when the generator supports it, removing any term that conflicts with the user's intent. Before generation, verify a visible narrative trigger, story-first composition, clear motivated directional key light, one large chromatic shadow mass, and a character/action/anchor crossing the light-shadow boundary. If any is missing, revise the final prompt before proceeding.

### Style invariants

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

### Narrative and cinematic gate

Before returning a prompt or generating, verify that the image has all of the following:

- A visible narrative trigger or unresolved relationship, expressed through action, scale, environment, or a meaningful prop.
- A composition that prioritizes the story beat over a centered character showcase.
- A clear directional key light and a large, chromatic shadow mass; “soft” must never flatten the value structure.
- A readable light-versus-shadow crossing on the character, action, or visual anchor.

If any item is missing, revise the scene expansion and prompt before generating. Favor a single clear story tension over adding decorative detail.

## 7. Generate from the final prompt

Reread the execution directory, report current progress, and generate one image from the final prompt when an image-generation tool is available. Preserve the selected aspect ratio and locked composition, depth, and lighting constraints. Do not pause for approval. If generation is unavailable, report the limitation and provide the final prompt instead.

## 8. Inspect, strictly audit, and repair

Reread the execution directory. Inspect the generated image against every selected composition, depth, background, character, lighting, calibration, narrative, and cinematic requirement. Check thumbnail readability, silhouette, look room, perspective, foreground–midground–background separation, environmental integration, natural acting, hair and fabric behavior, source-consistent light, readable chromatic shadows, controlled highlights, detail hierarchy, and whether the unresolved story reads without explanation.

Always perform exactly one audit-and-repair pass, even if the first image already passes. Identify the highest-priority concrete defect or remaining opportunity in this order: composition → depth → lighting → background detail → character detail. Make a focused revision affecting at most one to three fields in that category, preserve all earlier passing constraints, regenerate, and recheck. Never repair a late-stage detail by reopening a passing earlier stage, and do not pause for approval between inspection, repair, regeneration, and recheck.

## 9. Generate and deliver the final image

After the repaired image passes the applicable checks, reread the execution directory, report 100% progress, and deliver the final image. Give only compact supporting context: the selected direction, scene classification, and the material audit repair. Do not expose private chain-of-thought, reprint the full prompt unless requested, or require further user action. When the user asks for parameters, include the applicable starting values from [references/tonal-parameters.md](references/tonal-parameters.md). State the recommended aspect ratio only when it is implied by the request or materially improves composition.

At every directory checkpoint, confirm that the next required reference and card have been read before advancing. For prompt assembly, use the final-prompt template; for expansion, use the expansion reference; for parameter matching and audit, use the method, module, composition, background, character, calibration, and lighting references listed in step 5.
