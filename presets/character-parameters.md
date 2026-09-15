# 人物通用参数与预设

在场景扩写完成后填写人物卡。只保留能改变当前画面的字段；人物设计复杂度应低于环境复杂度，不能以堆砌五官、饰品或服装取代叙事。

## 紧凑人物卡

```text
character_presence: quiet / reserved / delicate / natural / melancholic / ethereal / confident / alert / energetic / cinematic_anonymous
character_energy: 0–100
character_narrative_role: hero_subject / balanced_subject / environmental_anchor / background_subject

expression_intensity: 0–5
gaze_intensity: 0–5
gaze_direction: camera / away_from_camera / downward / upward / sideways / object_focus / distant_focus / unfocused
gaze_distance: near / medium / far / infinite

hair_structure: [length + silhouette + orderliness + bangs + face-framing strands]
hair_motion: 0–5
hair_motion_distribution: root / mid-length / ends / face strands

skin_face: [value + matte/specular level + shadow hue + face/eye simplification]
body_pose: [head yaw/pitch + orientation + shoulder + spine + weight distribution + tension]
action: [one main action + one secondary action + one passive interaction]

outfit_silhouette: [fit/layering + key garment shape + decoration density]
fabric_behavior: [weight + stiffness + surface + fold logic + motion]

character_lighting: [lighting role + face-light ratio + shadow density + rim light + exposure]
separation: [depth / light / color / rim / negative-space / shape contrast]
camera_awareness: unaware_of_camera / partially_aware / aware_of_camera
pose_naturalness: natural / candid / semi_posed / posed
```

## 默认电影叙事人物

除非用户指定更强的表演或动作，可从下列默认开始：

```text
character_presence = quiet
character_energy = 20–30
character_narrative_role = environmental_anchor
expression_intensity = 0.5–2
gaze_intensity = 1.5–3
hair_motion = 1–2.5
motion_intensity = 0.5–2
decoration_density = low–medium
fold_complexity = low–medium
character_lighting = side_lit / side_backlit / mostly_in_shadow
face_light_ratio = 30_70 / 50_50
rim_light = subtle–medium
camera_awareness = unaware_of_camera
pose_naturalness = natural / candid
```

## 可选人物预设

| 预设 | 关键值 | 适用情况 |
| --- | --- | --- |
| `quiet_cinematic` | 安静、低能量、克制表情、轻微发丝动态、侧逆光、略欠曝 | 等待、观察、独处、环境主导。 |
| `urban_daylight` | 自然姿态、微风、棉麻或哑光布料、侧逆光、光与形状分离 | 日间街区、阳台、通勤或城市日常。 |
| `gentle_wind` | 发根稳定、发中段少动、发尾中等动态；衣物轻微响应 | 风是环境动作而人物仍安静。 |
| `stillness` | 极低动作与表情强度、几乎静止的头发与衣料、无镜头意识 | 停顿、等待、压抑或悬念。 |
| `look_back` | 背部三分之四、头部转 30–45°、非对称肩线、自然重心 | 回望或被环境打断的瞬间。 |

## 约束

- 表情强度通常低于眼神和身体语言的强度；一个清晰视线与姿态胜过戏剧化表情。
- 动作只保留一个主动作、一项次要手势和一项被动环境互动。双手对称摆拍、无目的的裙摆和过强风效应默认禁止。
- 头发和衣料必须遵从重力、身体张力与已说明的风或动作；不得用逐根发丝、随机褶皱或高光噪点制造“精细”。
- 人物受光必须服从场景主光。若环境是低调方向光，人物不能被单独棚拍式打亮。
- `environmental_anchor/background_subject` 不与大幅特写或超过 30% 画面占比并用，除非用户明确推翻环境主导构图。
