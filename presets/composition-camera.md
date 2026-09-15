# 电影构图与摄影机预设

先选摄影机，再决定人物、空间与细节。所有字段是语义构图约束：按扩写填入并转写为提示词，不假定图像工具有真实镜头控制。

## 构图卡

```text
aspect_ratio: 16:9 / 2.39:1 / 3:2 / user_specified
lens: 20–28mm / 28–35mm / 35–50mm / 70–100mm
camera_height: low / eye_level / slightly_high
camera_pitch: slight_upward / level / slight_downward
perspective: one_point / two_point / three_point
subject_frame_ratio: 8–18% / 15–25% / 20–35% / user_specified
subject_position: lower_center / thirds / center / edge
negative_space: low / medium / high
foreground: none / light / medium / strong; optional occlusion
depth: shallow / medium / deep; background_readability low/medium/high
leading_lines: none / architecture / street / rails / floor / natural path
large_shapes: bright_mass / dark_mass / readable_silhouette
```

## 预设匹配

| 预设 | 适用扩写 | 核心约束 |
| --- | --- | --- |
| `environment_dominant` | 城市、海面、天空、巨构吞没人物 | 24–35mm，远距离，人物 8–18%，高负空间，深景深。 |
| `urban_staircase` | 楼梯、巷道、栏杆与街区纵深 | 28–35mm，低至平视，两点透视，人物右三分、20–30%，中景深，栏杆/楼梯引导线。 |
| `central_stage` | 大厅、车站、教堂、走廊的秩序或对峙 | 24–45mm，平视，一点透视，克制对称，人物中心但中小比例。 |
| `candid_observational` | 隔窗、远观、偷看、自然日常 | 70–100mm，远距离，人物 15–25%，轻遮挡与透视压缩，人物无镜头意识。 |
| `layered_field` | 花海、树林、前景遮挡与亲密环境 | 50–85mm，三分位置，强前景、浅至中浅景深，背景可读但柔化。 |
| `low_angle_scale` | 巨构、向上动作、压迫或纪念碑感 | 20–28mm，低机位、轻仰，强垂直线；只在尺度或动作受益时使用。 |

## 约束与校准

- 每张图只选一个主预设；多种摄影机逻辑冲突时，以最能讲清人物与环境关系的一种为准。
- 人物视线方向保留 look room；人物在环境中作为锚点时，不能用大特写、低负空间或居中海报构图抵消环境叙事。
- 前景、中景、背景必须能在缩略图中分开；人物剪影和大亮/暗形要可读，边缘清晰度随焦点和光线分级。
- 迭代时先改镜头高度、焦距、人物位置和比例；再改透视、引导线、层级；最后才改负空间、密度与小细节。
