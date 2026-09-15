# 全场景电影光影与阴影预设

用于所有场景的电影光影组织：先匹配真实的主光来源，再建立选择性亮部、有层次的阴影、受控高光与局部接触阴影。城市硬日光是其中一个专用分支，不是默认光源。

## 参数卡

```text
lighting_preset: hard_sun / window_directional / practical_low_key / moonlight_directional / overcast_shaped / user_specified
key_light_type: [match the actual source]
key_direction: [one clear direction or deliberately soft source]
primary_light_area: [scene-appropriate, selective]
shadow_area: [scene-appropriate, with one substantial readable shadow mass]

value_structure: L1 primary lit plane / L2 reflected or secondary light / L3 open shadow / L4 deep occlusion
cast_shadow: match source size and occluder, direction-consistent
cast_shadow_edge: near occluder sharper; farther edges softer when physically appropriate
form_shadow: soft_to_medium unless the material/source requires otherwise
deep_shadow_area: limited and readable rather than crushed

ambient_fill: match sky, room, or practical bounce; restrained
environment_bounce: subtle and scene-derived
negative_fill: the scene's dark structure
key_temperature: match source
shadow_temperature: complementary restrained bias
warm_cool_separation: only when the source supports it

subject_exposure: match narrative; preserve value separation
face_light_ratio: match source and emotional read
rim_light: only on source-facing edges when physically present
highlight_control: high; clipping minimal
contact_shadow: strong_but_localized
ambient_occlusion: subtle_medium
```

## 光源分支

| 场景条件 | `lighting_preset` | 光影匹配 |
| --- | --- | --- |
| 城市或自然中的直射日光与硬遮挡 | `hard_sun` | 硬投影、大而连贯的遮阴、略暖日光与冷开放阴影。 |
| 窗、门、天窗或缝隙光 | `window_directional` | 明确窄光束，暗室形成容器；投影硬度按窗距与漫射程度匹配。 |
| 夜景、室内灯、霓虹或单一实景灯 | `practical_low_key` | 灯具是可见或可推断的主光；保留暗部结构，反射只服务视觉路径。 |
| 月光、远处冷光或夜空 | `moonlight_directional` | 冷色主光、低曝光、受控轮廓与少量暖色实景点光。 |
| 阴天、雾、雪或柔光日常 | `overcast_shaped` | 软方向性与可读深色结构；避免平均泛白，不伪造硬日光。 |

## 写入提示词的通用核心块

```text
one clear motivated key light, large coherent shadow masses,
selective primary-lit planes, readable reflected light and open shadows,
source-appropriate cast-shadow edges with softer form shadows,
deep shadows with preserved detail, restrained ambient fill and scene-derived bounce,
natural negative fill from dark structures, controlled highlights,
localized contact shadows, physically coherent light and shadow direction,
no crushed blacks, no flat ambient illumination
```

硬日光分支可额外加入：`strong directional urban sunlight, hard architectural cast shadows, cool open shadows and slightly warm highlights, cool sky fill, subtle warm ground bounce`。只加入能被扩写支持的局部项：例如栏杆、楼梯或窗框存在时才写其投影；白衣、黑发、花、猫或金属也只有在用户已要求时才写其具体受光。

## 阴影逻辑与约束

- 阴影必须是大而连贯的图形；不要用许多无来源的小阴影代替主明暗结构。
- 同一主光必须统一人物、环境、地面与任何道具的投影方向。硬日光中的 `broken architectural light` 只能由几何遮挡形成，不能随机散布。
- 硬的是投射阴影；人物脸部、肢体与布料的形体阴影保持软至中等过渡。脸部不可被不合理的硬阴影整块切开。
- 开放阴影不是纯黑：保留冷灰、青灰或蓝灰信息；深遮蔽只占有限区域，压缩暗调但不压死细节。
- 高光只给受日光的皮肤、布料、纸张、植物或建筑边缘；白色布料仍要分出受光面、半明面、形体阴影、褶皱遮蔽与投影。
- 轮廓光只出现在朝日光的边缘。不得画出角色一整圈发光，也不得为让黑发显眼而整体提亮。
- AO 与接触阴影是小且局部的：鞋底/脚掌接地、手接触物体、包贴近身体、衣物层叠处。它们用于防止漂浮，不得吞没大结构。

## 样例图校准

与城市楼梯样例比对时，检查：

1. 直射阳光是否只落在人物和建筑的选择性区域，而不是平均照明？
2. 大建筑阴影是否组织了画面，并保留冷色结构？
3. 投影方向、栏杆/楼梯节奏与人物受光是否同源？
4. 白色或浅色衣物是否保持材质、褶皱和半明变化，而没有过曝成一片？
5. 人物是否略欠曝、通过局部暖亮边与形状对比嵌入环境？

出现问题时优先改光向、阴影面积、投影逻辑或高光控制；不要先加纹理、锐化或更多小型反射。
