# Soft Photo prompt template

## Base prompt

Use this as a template, replacing the brackets with the user's content. Delete any clause that does not fit the scene.

```text
[主体与外观]，位于[场景]，[动作/瞬间]，[神态与情绪]。
日系动画电影感插画，精细干净的线稿与柔和半厚涂结合，可信的材质细节；
[时间/天气]的自然光，[主光方向]，柔和边缘光、空气透视与细碎反射高光；
前景—人物—背景形成清晰空间层次，[镜头与构图]，环境细节服务于人物与叙事；
[风、运动、反射或环境互动]，克制的电影级冷暖色彩，通透明亮、安静而富有瞬间感。
anime cinematic illustration, detailed environment, natural light, clear focal subject
```

## Optional modules

Choose one or two; do not stack all of them.

- **都市动态**：`广角低机位，轻微 Dutch angle；近景路人与车辆形成受控拖影，玻璃幕墙与金属表面映出天空。`
- **室内静景**：`窗边或温室式空间，植物叶影在家具与衣物上流动；以大面积柔光和微小高光表现安静的呼吸感。`
- **高空/奔跑**：`透视夸张但人物比例自然；衣摆、发丝与悬浮物受风牵引，动作像被高速快门定格。`
- **晴空逆光**：`太阳靠近画面边缘，适度体积光与镜头耀斑，保留脸部和服装的可读细节。`
- **阴天/雨后**：`漫射冷光，湿地与玻璃反射，低饱和蓝灰与微暖室内光形成对比。`
- **亲密肖像**：`中近景，背景柔和虚化；将光影、眼神和手部动作作为视觉重点，减少复杂环境。`

## Cross-model negative prompt

Only include it where supported. Remove terms that conflict with the request—for example, do not use `motion blur` as a negative term when intentionally表现动态。

```text
low resolution, blurry focal subject, bad anatomy, malformed hands, extra fingers,
duplicate limbs, distorted face, crossed eyes, unreadable expression,
flat lighting, muddy colors, overexposed face, underexposed subject,
warped perspective, clutter obscuring the subject, incoherent background,
plastic skin, overly glossy 3D render, watermark, signature, logo, text
```

## Compatibility notes

- For models that respond better to English, translate the subject and scene as well; keep the camera terms in English.
- For models that ignore long prompts, retain the first subject sentence plus the style, lighting, and one composition clause.
- For image-to-image editing, describe only the intended changes after the base style; do not repeat characteristics that must remain untouched.
