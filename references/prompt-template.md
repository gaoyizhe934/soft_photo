# Soft Photo prompt template

## Base prompt

Use this as a template, replacing the brackets with the user's content. Delete any clause that does not fit the scene.

```text
[主体与外观]，位于[场景]，[动作/瞬间]，[神态与情绪]。
日系动画电影感插画，舒展清晰的线条与柔和半厚涂，以概括性的材质和有限细节保留呼吸感；
[时间/天气]的柔和自然光，[主光方向]，平缓的明暗过渡、可读的中间调与克制的高光；
前景—人物—背景形成简洁空间层次，[镜头与构图]，保留适当留白，环境只用少量关键元素服务人物与叙事；
[一到两项风、运动、反射或环境互动]，低饱和而协调的冷暖色彩，安静、自然、像被恰好捕捉到的一瞬。
anime cinematic illustration, soft natural daylight, restrained detail, balanced composition, clear focal subject
```

## Optional modules

Choose one or two; do not stack all of them.

- **都市动态**：`广角或轻微低机位，必要时使用轻微 Dutch angle；以少量行人、招牌或玻璃反射交代城市，不把街景填满。`
- **室内静景**：`窗边或温室式空间，植物叶影轻轻落在家具与衣物上；以大面积柔光和简化陈设表现安静的呼吸感。`
- **高空/奔跑**：`宽阔天空或空白背景占据较大画面；透视舒展但人物比例自然，衣摆、发丝或一件轻物受风牵引。`
- **晴日柔光**：`阳光温和地落在人物和衣物上，阴影边缘柔软；避免刺目的直射高光、厚重体积光与夸张镜头耀斑。`
- **阴天/雨后**：`漫射冷光，湿地或玻璃只保留少量安静反射；低饱和蓝灰与微暖室内光形成柔和对比。`
- **亲密肖像**：`中近景，背景自然虚化；以眼神、手部动作和一处柔和光影作为重点，减少复杂环境。`

## Cross-model negative prompt

Only include it where supported. Remove terms that conflict with the request—for example, do not use `motion blur` as a negative term when intentionally表现动态。

```text
low resolution, blurry focal subject, bad anatomy, malformed hands, extra fingers,
duplicate limbs, distorted face, crossed eyes, unreadable expression,
flat lifeless lighting, harsh lighting, extreme contrast, overexposed face, underexposed subject,
overly detailed background, excessive micro-texture, every surface equally sharp, busy tiny objects,
excessive accessories, clutter obscuring the subject, warped perspective, incoherent background,
plastic skin, overly glossy 3D render, excessive lens flare, excessive glow effects,
watermark, signature, logo, text
```

## Compatibility notes

- For models that respond better to English, translate the subject and scene as well; keep the camera terms in English.
- For models that ignore long prompts, retain the first subject sentence plus the style, soft-lighting, and one composition clause.
- For image-to-image editing, describe only the intended changes after the base style; do not repeat characteristics that must remain untouched.
