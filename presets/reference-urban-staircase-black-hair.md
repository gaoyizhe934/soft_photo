# 校准样本：城市楼梯中的黑发少女

这是用户提供图像及其已填参数的校准记录。对应原图保存在 [reference-images/urban-staircase-black-hair.jpg](reference-images/urban-staircase-black-hair.jpg)。它不是默认角色预设：除非用户明确要求，不得自动加入黑发、白色制服、白花、猫、楼梯或商业街。每次生成只对照下列与当前任务相关的“执行质量”维度。

## 样本人物卡

```text
character_presence = quiet
character_energy = 20/100
character_narrative_role = environmental_anchor
camera_awareness = unaware_of_camera
pose_naturalness = candid

hair = deep black, mid-back to waist, medium-heavy, slightly messy,
       irregular layered bangs, moderate face-framing strands,
       gentle motion at loose ends, subtle warm rim and reflected highlights
face = light soft-matte skin, soft oval face, medium-small soft-almond eyes,
       lowered eyelids, relaxed brows and closed lips
gaze = downward, object-focused, near, intensity 1.5–2/5
pose = 30–45° head turn, slightly down, three-quarter body, relaxed shoulders,
       asymmetric weight, low motion
action = quietly examining a flower; one active hand, one passive arm
outfit = loose layered white sailor-inspired silhouette, above-knee layered skirt,
         medium-low decoration and low accessories
fabric = light-medium matte woven, soft, medium folds following gravity,
         localized compression, subtle tension and wind
lighting = side-backlit, 30/70–50/50 face light, slightly underexposed,
           medium-deep preserved shadows, subtle rim light
separation = light contrast + shape contrast + subtle depth
frame = 20–30% subject, right third, environment complexity above character complexity
```

## 每次生成的对比校准

生成前写明本次哪些维度应与样本一致、哪些必须不同。生成后只给相关项打分：`0` 不成立、`1` 可用、`2` 清晰成立。若总分不足或一个必需项为 `0`，下一轮只修改一至三个相应变量。

| 校准维度 | 检查问题 |
| --- | --- |
| 环境融合 | 人物是否像真实处于同一光线、尺度与空间中，而非叠在背景前？ |
| 自然表演 | 视线、身体重心、手势与动作目标是否一致，而非摆拍？ |
| 轮廓与布料 | 服装首先是否读作清晰轮廓，褶皱是否服从重力、张力和运动？ |
| 头发动态 | 发根、发中段、发尾的运动程度是否不同，且与风或动作匹配？ |
| 人物受光 | 人物是否服从场景方向光，阴影保留信息，高光只落在有意义边缘？ |
| 主体分离 | 是否以形状、明暗、少量轮廓光或层级分离，而非过度散景或过锐人物？ |
| 叙事比例 | 人物的画面占比、位置和环境复杂度是否支持当前故事，而非角色海报？ |

## 样本的可迁移结论

- 环境细节可以丰富，但人物造型、表情和动作保持克制。
- 人物清晰但不棚拍式过锐；亮边更清楚，暗边更柔和。
- 方向性侧逆光、保留细节的深影和少量暖高光能使人物融入复杂空间。
- 用自然动作对象、非对称重心和“无镜头意识”代替正面展示。

当用户要求直接匹配该参考时，才启用样本人物卡的外观字段；若只是常规生成，仅使用对比校准和可迁移结论。
