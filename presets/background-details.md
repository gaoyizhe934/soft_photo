# 电影背景细节预设

高环境复杂度不等于高微细节密度。先建立大结构，再添加中尺度功能细节；微细节稀少、聚类且随深度衰减。

## 环境细节卡

```text
background_preset: balanced / dense_industrial / urban_lived_in / clean_hotel / glass_library / observational_office / distant_simplified
macro_structure: high
secondary_structure: medium_high
functional_detail: low_medium / medium
micro_detail_budget: 5–30
detail_clustering: high
visual_rest_area: 20–45
background_contrast: 30–58
background_microcontrast: 28–42
material_families: 3–6
repetition: medium_high / high
randomness: low / medium_low
depth_detail_falloff: strong
focal_buffer: enabled
```

## 预设匹配

| 预设 | 场景 | 细节组织 |
| --- | --- | --- |
| `balanced` | 一般电影叙事环境 | 高大结构、清楚中结构、稀少微细节；高聚类与 30% 左右休息区。 |
| `dense_industrial` | 工业、巨构、物流、站台 | 大量中尺度重复结构，少量微细节；高重复、低随机、强深度衰减。 |
| `urban_lived_in` | 老城区、楼梯、巷道、街区 | 功能性生活痕迹聚类，适度磨损，远处文字不可读。 |
| `clean_hotel` | 酒店、展厅、简洁公共室内 | 低噪点、高大形清晰度、更多休息区、低磨损。 |
| `glass_library` | 书店、图书馆、玻璃空间 | 书与植物只作为中尺度节奏，反射受控，文字不可读。 |
| `observational_office` | 办公室、工作台、隔窗观察 | 家具和设备交代使用痕迹，前景遮挡可用，远处细节降级。 |
| `distant_simplified` | 远景城市、山体、背景层 | 保留宏观轮廓，降低对比、饱和、锐度、语义与纹理。 |

## 通用提示词与约束

```text
rich but controlled environmental detail, clear large-scale structure,
medium-scale functional details, sparse micro-details,
details grouped into coherent clusters, visual rest areas,
background complexity without visual noise, strong detail falloff with depth,
mostly unreadable background text, simplified distant geometry,
clear environmental storytelling, no unnecessary decorative clutter
```

- 背景原始细节可多于人物，但视觉优先级不得高于人物或叙事锚点。
- 近景边缘较清楚，中景适中，远景柔化；背景文字默认不可读。
- 每个表面不能都有独特装饰、磨损与高光；材料族控制在 3–6 种，细节按功能或结构聚类。
- 在人物剪影附近创建细节缓冲区；缩略图中先读到大形、空间与叙事，再读到细节。
