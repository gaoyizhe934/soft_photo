# Soft Photo prompt template

## Base prompt

Assemble the sections in this order. Replace brackets with the user's content and delete any clause that does not serve the scene.

```text
[主体人物与外观]，[发型与服装]，[姿态与动作]，位于[场景类型]；[环境细节]与[一个关键叙事道具]共同说明人物为何在此。
日系动画电影感环境插画，人物全身、比例中小或中等，自然嵌入环境而非单独展示；明确的二维日漫角色绘制：舒展清晰的线条、略作风格化的脸部比例、清晰虹膜与富有情绪但不过分夸张的日漫眼睛，鼻子和嘴以简洁形状表达；脸部以干净色块和有限赛璐璐式明暗塑形。头发由清晰发束、鲜明外轮廓、整体明暗块和少量受光丝带构成，不渲染毛孔、皮肤纹理或密集真实发丝；服装保持用户指定的轮廓与材质，环境可保留可信的生活痕迹、建筑结构与选择性的玻璃、金属、水面或植物信息；
[时间/天气]中明确的方向性主光，[主光方向]，强烈电影明暗对照，清晰的受光面与背光面；画面中保留一块大面积、可读的深色结构作为明暗锚点，人物或关键元素跨越明暗分界；
暗部保持深度，避免压成纯黑，保留冷灰、蓝绿、橄榄或暖褐色相、少量反射光和必要结构，极少环境补光；
亮部收束为暖象牙白、银灰或淡暖色，只有太阳、玻璃、水面或金属反射等小面积高光接近纯白，避免大面积死白；
前景—人物—背景形成清晰空间层次，[构图]，[镜头]，建筑、天空、自然或城市空间承担叙事并可占据大部分画面；
[一到两项风、运动、反射或环境互动]，[主色 + 强调色]，画面像一个被时间冻结、没有明确开端和结局的故事中段：[氛围与叙事]。
contemporary Japanese anime character design, 2D anime face, clear iris shapes, expressive restrained anime eyes,
simplified nose and mouth, clean cel-shaded facial planes, graphic hair locks with a clear outer silhouette,
controlled hair highlight ribbons, approachable everyday emotional read, selective functional clothing layers,
anime cinematic illustration, strong directional light, cinematic chiaroscuro, clear light-shadow separation,
one large deep chromatic shadow mass, minimal ambient fill, controlled highlights, dark tonal anchors,
medium-small full-body character naturally embedded in the environment, environmental storytelling,
foreground-midground-background depth, believable architecture and selected material cues,
meaningful props, atmospheric perspective, cinematic negative space, balanced composition, suspended narrative moment
```

## Optional modules

Choose one or two; do not stack all of them.

- **环境主导**：`environment-dominant composition, medium-small full-body character, character embedded naturally in the scene, architecture, sky, city, or landscape occupying most of the frame.`
- **宏大尺度**：`tiny solitary figure against monumental surroundings, human dwarfed by architecture, nature, sky, or planetary scale, character as a visual anchor rather than the dominant subject.`
- **都市动态**：`广角或轻微低机位，必要时使用轻微 Dutch angle；以少量行人、招牌、设备或玻璃反射交代城市，让街景与人物共同叙事。`
- **室内静景**：`靠窗的一束硬侧光或一盏明确的实景灯，室内另一侧沉入深色结构；桌面、墙面、书本、植物或器物保留能说明生活痕迹的细节。`
- **高空/奔跑**：`宽阔天空或空白背景占据较大画面；透视舒展但人物比例自然，衣摆、发丝或一件轻物受风牵引；地面或建筑形成深色框架，人物轮廓由侧逆光切出亮边。`
- **晴日强光**：`阳光方向明确，树影、栏杆影或窗影形成清晰锐利节奏；阴影深而有色，不做死黑，也不以大面积补光冲淡。`
- **电影反差／开放暗部**：`strong directional key light, cinematic chiaroscuro, strong light-to-shadow ratio, substantial deep chromatic shadow mass, minimal ambient fill, controlled highlights, no uniform exposure.`
- **动漫角色强化：** `contemporary Japanese anime character design, clear 2D facial silhouette, readable irises, expressive but restrained eyes, simplified nose and mouth, graphic hair locks; begin with everyday or outdoor clothing and add only one to three functional design accents, avoiding a realistic portrait or overloaded gear.`
- **叙事停格**：`strong cinematic environmental storytelling, a suspended moment from the middle of an unexplained story, quiet restrained expression, meaningful environmental detail, selective visual symbolism, emotional distance, poetic ambiguity.`
- **高层暴风窗景**：`vast dark high-rise interior, colossal panoramic window wall, small solitary figure, massive storm clouds outside, a narrow cold white-blue horizon light, thin distant warm-orange city lights, exterior light as the dominant source, apocalyptic calm.`
- **阴天/雨后**：`低饱和冷灰环境中设置一处明确暖光或窗光，使人物与背景形成深色结构和有限的亮部焦点，避免均匀发白的平光。`
- **亲密肖像**：`中近景，一侧主光让面部与衣物跨越明暗分界；以眼神、手部动作和光影作为重点，减少复杂环境。`

## Cross-model negative prompt

Only include it where supported. Remove terms that conflict with the request—for example, do not use `motion blur` as a negative term when intentionally表现动态。

```text
low resolution, blurry focal subject, bad anatomy, malformed hands, extra fingers,
duplicate limbs, distorted face, crossed eyes, unreadable expression,
low contrast, flat lighting, evenly lit scene, uniform high-key exposure, soft diffuse lighting,
washed-out shadows, pale shadow values, no dark tonal anchor, bright haze over the entire image,
broad featureless white areas, clipped clouds, overexposed sky, excessive ambient fill, excessive bloom,
crushed blacks, pure black shadows, empty dark areas, plastic gloss, harsh digital HDR,
photorealistic face, realistic skin texture, skin pores, subsurface scattering, realistic hair,
live-action facial proportions, fashion-photo model face, overly realistic eyelashes, individual hair strand rendering,
fuzzy flyaway hairs, 3D character render, CGI, waxy doll-like skin,
oversharpening, every surface equally sharp, excessive meaningless micro-texture, random meaningless clutter,
oversized character, close-up portrait, character filling the frame, flat composition, simple empty background,
weak environment detail, inconsistent perspective, excessive fisheye distortion, oversaturated colors, excessive neon,
excessive accessories, clutter obscuring the subject, warped perspective, incoherent background,
watermark, signature, logo, text
```

## Compatibility notes

- For models that respond better to English, translate the subject and scene as well; keep the camera terms in English.
- For models that ignore long prompts, retain the first subject sentence plus the style, strong-directional-lighting, and one composition clause.
- For image-to-image editing, describe only the intended changes after the base style; do not repeat characteristics that must remain untouched.
- For tonal adjustments, keep the positive prompt's phrases about deep chromatic shadows, directional light, and controlled highlights together; do not pair them with `pure black`, `high-key`, or blanket `low contrast` language.
