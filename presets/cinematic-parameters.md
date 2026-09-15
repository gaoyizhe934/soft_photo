# 电影感参数预设

在扩写与方法卡完成后使用本文件。它把叙事判断变成可复核的提示词约束；字段均为语义参数，不是某个图像模型的 API 或界面设置。只有用户指定工作流时，才额外使用对应的模型参数。

## 参数预设卡

从每组选择一个最符合扩写的值，并删去不适用字段。先填写卡，再将其中的英文约束自然写入正向提示词；不要把整张卡逐字堆叠进提示词。

```text
composition_preset: environment_pressure / depth_narrative / axial_stage / offset_observation / framed_observation / kinetic_environment
shot_type: extreme_wide / wide / medium / close
subject_scale: tiny / small / medium / large
subject_position: lower_center / left_third / right_third / center / edge
negative_space: low / medium / high
camera_height: low / eye_level / high
leading_lines: none / architecture / railing / floor / corridor / street / natural_path

depth_preset: scale_readability / layered_focus / staged_depth / intimate_focus
depth_layers: 2 / 3 / 4
foreground_occlusion: none / light / medium / strong
dof_strength: shallow / medium_shallow / medium / deep
focus_priority: subject / environment / balanced
background_readability: low / medium / high
atmospheric_depth: low / medium / strong

lighting_preset: low_key_directional / side_backlight / controlled_soft_directional / bright_entry_dark_interior / selective_reflection
shadow_density: light / medium / deep
shadow_softness: soft / medium / hard
rim_light: none / subtle / medium / strong
highlight_control: restrained / moderate / bright
reflection: none / glass / water / wet_ground / polished_surface
contrast: medium / high

route: direct_final / composition_search / staged_iteration
locked_from_prior_round: [only for staged_iteration]
```

## 构图预设

| 预设 | 适用扩写 | 建议填入值 | 提示词约束 |
| --- | --- | --- | --- |
| `environment_pressure` | 人物被城市、海面、天空或巨构环境吞没 | `extreme_wide` 或 `wide`；`tiny` 或 `small`；`high` 负空间；环境相关引导线 | `environment-dominant composition, small figure against monumental surroundings, generous negative space` |
| `depth_narrative` | 花木、街景、室内物件或灯光形成连续遮挡 | `medium`；`3` 层；`medium/strong` 前景遮挡；`medium_shallow`；背景 `medium` 可读 | `blurred foreground, sharp midground subject, readable but softer background, three-layer depth` |
| `axial_stage` | 大厅、走廊、车站、教堂等依赖秩序或对峙 | `wide` 或 `medium`；通常 `center`；`medium` 负空间；`architecture/floor/corridor` 引导线 | `restrained symmetry, strong one-point perspective, leading lines guide the eye to the story anchor` |
| `offset_observation` | 等待、离开、观察或孤立是故事重心 | `wide` 或 `medium`；`left_third/right_third/edge`；`medium/high` 负空间 | `off-center narrative composition, environmental negative space, avoid poster-like centered framing` |
| `framed_observation` | 门、窗、玻璃、家具、植物或洞口构成观看边界 | `medium` 或 `wide`；按实际边界选 `light/medium` 遮挡 | `frame within frame, foreground boundary establishes an observing distance` |
| `kinetic_environment` | 跳跃、奔跑、风、水、坠落等动作关系需要被读出 | `wide`；`small/medium` 主体；低机位仅在动作路径或尺度受益时使用 | `motion path readable through the environment, one or two physical interactions, no decorative effects overload` |

## 景深预设

| 预设 | 何时使用 | 约束 |
| --- | --- | --- |
| `scale_readability` | 地理关系、巨构尺度或动作路径必须清楚 | `3/4` 层，`medium/deep` 景深，环境或平衡焦点，背景 `high` 可读；不用无意义散景。 |
| `layered_focus` | 观察距离和前中后景关系承担叙事 | `3` 层，`medium/strong` 前景遮挡，`medium_shallow`，主体最清晰，背景 `medium` 可读。 |
| `staged_depth` | 中轴空间或多人调度依赖全景关系 | `3` 层，`medium` 景深，焦点 `balanced`，背景 `high` 可读。 |
| `intimate_focus` | 手势、眼神或一件叙事道具压倒环境尺度 | `2/3` 层，`shallow`，主体焦点；仍保留足以定位人物的环境信息。 |

## 光影预设

| 预设 | 何时使用 | 建议填入值与约束 |
| --- | --- | --- |
| `low_key_directional` | 等待、威胁、巨大空间、风暴前、从暗处望向亮处 | `deep` 阴影、`medium/hard` 阴影边缘、`restrained` 高光、`high` 对比；`one clear directional key light, large chromatic shadow mass, preserved shadow detail`。 |
| `side_backlight` | 离开、边界、回望、风或水的动作 | `subtle/medium` 轮廓光、`medium/deep` 阴影、`high` 对比；高光只切出人物或动作的叙事边缘。 |
| `controlled_soft_directional` | 温柔日常、树影、花海或窗边 | `soft` 阴影过渡、`medium/deep` 阴影密度、`restrained` 高光、`high` 对比；柔和绝不等同于平均照明。 |
| `bright_entry_dark_interior` | 室内外强烈对照、车站、大厅、入口或大窗 | 外部入口为受控亮面、内部为深色容器；只在引导视线时加入地面或玻璃反射。 |
| `selective_reflection` | 水、雨、玻璃、金属或湿地面能延长故事线索 | 只选一种对应的 `reflection`；反射重复主光、人物路径或视觉锚点，不把所有表面做成镜面。 |

## 约束与兼容性

- 每张图只选一个 `composition_preset`、一个 `depth_preset` 和一个主 `lighting_preset`。`selective_reflection` 可以作为光影预设的附加项，但必须有扩写依据。
- `environment_pressure` 不与 `large` 主体或 `low` 负空间并用；如用户明确要求人物特写，应改用亲密叙事方法而非强行保留巨构尺度。
- `axial_stage` 只有故事依赖秩序、对峙或仪式性时才使用 `center`；否则改用 `offset_observation`。
- `layered_focus` 不与 `deep` 景深或“全画面同样锐利”并用；`scale_readability` 不与强散景并用。
- 所有光影预设默认 `contrast: high`。不得同时请求平均照明、泛白氛围、纯黑阴影、大面积过曝或无目的的高光。
- 迭代路线中，本轮只解锁所属组的字段：构图轮改 `composition_*`；景深轮改 `depth_*`；光影轮改 `lighting_*`；细节轮不得改动已锁定的前三组。

## 填写示例

扩写：少女站在高楼阳台俯瞰城市老区，人物很小，老城区与新楼构成尺度对照，夕光切过栏杆。

```text
composition_preset: environment_pressure
shot_type: extreme_wide
subject_scale: small
subject_position: left_third
negative_space: high
leading_lines: railing

depth_preset: scale_readability
depth_layers: 3
dof_strength: medium
focus_priority: balanced
background_readability: high

lighting_preset: side_backlight
shadow_density: deep
rim_light: subtle
highlight_control: restrained
contrast: high

route: direct_final
```

该卡会转化为“人物小、环境主导、栏杆引导线、中景深保留城市尺度、侧逆光与深色有色阴影”等自然提示词，而不是输出一串无上下文的参数名。
