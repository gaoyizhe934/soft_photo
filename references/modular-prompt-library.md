# 模块化提示词库

按需选取模块，不要为了填满模板而虚构场景、道具或天气。用户已经指定的主体、地点、动作、天气和情绪优先。

## 组装顺序

```text
[主体] + [发型/服装] + [姿态/动作] + [场景] + [环境细节]
+ [关键叙事道具] + [构图] + [镜头] + [光线]
+ [色彩] + [材质] + [氛围/叙事] + [风格/质量] + [负面]
```

默认让人物完整地处于环境之中：全身、中小景或小景，保留前景—主体—背景三层。除非用户明确要求肖像，避免把人物放大到压缩环境叙事。

## 场景模块

| 叙事方向 | 可直接加入英文提示词的场景模块 |
| --- | --- |
| 高空与边界感 | `inside a dark high-rise interior, facing a floor-to-ceiling window, the city far below` |
| 公共空间 | `a futuristic glass atrium library, layered walkways, indoor trees, quiet reading tables` |
| 暂住与等待 | `an aging hotel lobby, worn carpet, luggage cart, low sofas, a bright entrance beyond` |
| 日常都市 | `an ordinary city office after work, window reflections, desks and small personal objects` |
| 生活痕迹 | `an old apartment balcony, drying clothes, potted plants, distant rooftops and power lines` |
| 屋顶 | `a city rooftop with railings, utility pipes and a broad horizon` |
| 交通/工业 | `an aging futuristic train station, exposed structure, platforms and soft signage glow` |
| 巨构工业 | `a logistics hub with stacked crates, suspended tags, walkways and cranes` |
| 留白公共区 | `a minimalist future public hall, broad floor planes, sparse seating, light and shadow` |
| 自然对照 | `a field of spider lilies, deep foliage and a narrow path` |
| 都市尺度 | `a megacity canyon of stacked buildings and bridges, a small figure against the scale` |
| 太空尺度 | `low Earth orbit, the curved night side of Earth, distant city lights and small satellites` |

## 环境与道具模块

环境细节应服务于地点、比例或人物经历。选择一到两个重点，不要平均罗列。

- 生活痕迹：`lived-in details, worn furniture, scattered books, cables, a half-open door`
- 建筑/工业：`credible structural beams, railings, service pipes, weathered concrete, functional machinery`
- 玻璃与水：`subtle window reflections`, `a shallow reflective floor`, `water ripples catching the light`
- 植物：`indoor plants casting dappled shadows`, `overgrown balcony greenery`
- 叙事锚点：`a crimson paper boat`, `a small white cat`, `a white kite`, `an empty chair`, `a luggage cart`, `a desk with a few personal objects`

## 构图与镜头模块

- 环境优先：`environment-dominant composition, the character embedded in the setting, foreground midground and background`
- 空间秩序：`centered composition`, `asymmetrical balance`, `strong one-point perspective`, `viewed through glass`
- 情绪留白：`generous negative space`, `a small human figure in a monumental space`
- 动势：`a restrained Dutch angle`（只在用户需要不稳定感时使用）
- 镜头：20/24mm 用于巨构与广阔空间；35mm 用于带环境的人物叙事；50mm 用于较亲密的日常片段；85mm 仅用于用户明确要求人物近景或压缩空间。

## 光线、色彩与材质模块

基础目标是强方向性、明暗分区清楚、暗部仍保有可读轮廓和环境信息；高光只落在叙事焦点或有意义的材质边缘。

- 日照：`strong natural directional sunlight, defined light and shadow, retained chromatic detail in deep shadows`
- 傍晚：`low warm sun, long shadows, warm highlights against cool-gray shadows`
- 侧逆光：`selective side backlight, a thin rim light on the focal edge, restrained bloom`
- 斑驳光：`dappled light through leaves or window frames, readable shadows, no crushed blacks`
- 玻璃光：`soft glass reflections and reflected sky color, used sparingly`
- 冷暖：`cool gray and amber`, `cold white-blue with one crimson anchor`, `teal gray and warm amber`, `navy, charcoal, red and off-white`
- 材质：`believable fabric folds, concrete, wood, glass or metal appropriate to the setting`。仅保留对场所、光线或故事有贡献的材质描述，不将每个表面渲染成镜面。

### 特殊模块：高层暴风窗景

```text
low-key dark interior, exterior light dominating through a huge window,
massive storm clouds, a thin cold white-blue slit of horizon,
small distant warm orange city lights, selective light on the character's white garment,
apocalyptic calm, quiet monumental scale
```

## 氛围与叙事模块

```text
cinematic environmental storytelling, a suspended unexplained moment,
poetic ambiguity, a quiet boundary between inside and outside,
the setting carries part of the character's story
```

可替换的情绪词：`quiet daily life`, `urban solitude`, `dreamlike pause`, `travel and waiting`, `apocalyptic calm`, `monumental scale`。

## 统一风格模块

```text
Japanese anime cinematic illustration, semi-realistic anime environment,
graphic 2D anime facial features and hair, restrained painterly digital rendering,
clear value design, balanced medium-scale detail, cohesive composition
```

这里的“semi-realistic”指可信的空间、建筑与材质，不指真人皮肤、毛孔、真人发丝或 3D CGI 人脸。

## 通用负面提示词

```text
photorealistic face, skin pores, realistic individual hair strands, 3D CGI,
plastic doll skin, over-smoothed face, distorted anatomy, extra fingers, malformed hands,
oversized character, close-up portrait, character filling the frame,
flat composition, empty background, weak environment detail, inconsistent perspective,
flat lighting, crushed blacks, clipped highlights, excessive bloom,
oversaturated neon colors, random clutter, meaningless microtexture,
text, watermark, logo, signature
```

不要把“玻璃、金属、植物、反射、家具、建筑细节”一概放入负面提示词；当它们是场景真实性或叙事的一部分时，应保留并控制其密度。
