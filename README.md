<div align="center">

# ✨ Soft Photo

**为日系动画电影感环境叙事插画生成兼顾强方向光、深色结构、空间层次与镜头语言的跨模型提示词。**

**Create cross-model prompts for anime-cinematic environmental storytelling with strong directional light, dark tonal anchors, spatial layers, and deliberate camera language.**

</div>

---

## ⚠️ 使用声明 / Usage Notice

> 本技能中的提示词、工作流设计、文档及其他原创内容仅供个人、教育、研究和非商业用途使用。未经原始作者事先书面授权，不得将其用于商业产品、付费服务、客户项目、企业商业应用、商业化 AI Agent／工作流、付费课程，或以出售、再授权、商业分发等方式使用。
>
> The prompts, workflow design, documentation, and other original materials in this skill are provided for personal, educational, research, and non-commercial use only. Prior written permission from the original author is required for commercial products, paid services, client work, enterprise commercial use, commercial AI agents/workflows, paid courses, resale, sublicensing, or commercial redistribution.
>
> 如在个人项目、研究、开源项目或社交媒体中使用，欢迎注明 `soft_photo` 与原始作者。/ If you use this skill in a personal project, research, open-source work, or social media, attribution to `soft_photo` and its original author is appreciated.

完整条款见 [LICENSE.md](LICENSE.md)。 / See [LICENSE.md](LICENSE.md) for the full terms.

---

## 📖 关于本项目 / About

`soft-photo` 是一项 Codex Skill，用于把人物、场景、天气、动作和情绪转写成一套可调整的日系动画电影感图像提示词。

`soft-photo` is a Codex Skill that turns a requested subject, setting, weather, action, and mood into adaptable prompts for anime-cinematic imagery.

- ✅ 使用“模块化叙事提示词”，让人物嵌入前景—主体—背景完整的环境；细节随场景和叙事需要调整，不用死记具体场景。
  Uses modular narrative prompts that embed the character in a complete foreground–subject–background setting; detail adapts to the story instead of memorising fixed scenes.
- ✅ 提供可跨模型使用、可按任务删减的负面提示词。  
  Includes a cross-model negative prompt that can be shortened for the task.
- ✅ 保留用户对人物、地点、构图和氛围的控制权。  
  Keeps the user in control of subject, setting, framing, and mood.
- ✅ 对简短画面概念，先提供可选叙事方向，再扩写为完整的图像创作简报，最后才生成提示词或图像。
  For a brief visual idea, offers narrative directions first, expands the selected one into a complete creative brief, and only then produces a prompt or image.
- ❌ 不保证生成器会精确复现任何参考图，也不用于模仿特定在世艺术家的风格。  
  Does not guarantee an exact reproduction of any reference image or imitate a specific living artist.

---

## 🚀 使用方法 / How to use

### 作为 Codex Skill / As a Codex Skill

1. 将整个 `soft-photo` 文件夹放入 Codex 的 skills 目录，例如 `~/.codex/skills/`。
2. 在新对话中使用 `$soft-photo`，随后描述你希望生成的场景。
3. 说明主体、场景、动作、天气、情绪以及偏好的构图或画幅；若描述简短，技能会先给出方向供选择，再扩写并生成提示词或图像。

1. Place the complete `soft-photo` folder in your Codex skills directory, for example `~/.codex/skills/`.
2. Invoke `$soft-photo` in a new conversation and describe the image you want.
3. Provide the subject, setting, action, weather, mood, and any preferred framing or aspect ratio. For a brief idea, the skill first offers directions to choose from, then expands it before producing a prompt or image.

### 直接使用提示词模板 / Use the prompt template directly

打开 [references/prompt-template.md](references/prompt-template.md)，替换方括号中的内容，并选择一到两个与场景匹配的可选模块。 / Open [references/prompt-template.md](references/prompt-template.md), replace the bracketed fields, and select one or two relevant optional modules.

---

## 🎛️ 可自由调整的部分 / What you can adjust

| 项目 / Item | 说明 / Guidance |
| :--- | :--- |
| 人物与叙事 / Subject & story | 人物外观、关系、动作与情绪完全由你的请求决定。 / Define appearance, relationships, action, and emotion in the request. |
| 场景与天气 / Setting & weather | 可使用都市、室内、自然或幻想场景，并改变时段与天气。 / Use urban, indoor, natural, or imaginative settings and vary time or weather. |
| 镜头与构图 / Camera & composition | 按叙事需要选择广角、低机位、俯视、轻微 Dutch angle 或静态中近景。 / Choose wide-angle, low/high angle, a subtle Dutch angle, or a calm closer framing as the scene needs. |
| 光线与色彩 / Light & color | 调整强方向主光、明暗分界、深色有色暗部、反射、高光及冷暖关系。 / Adjust directional key light, light-shadow separation, deep chromatic shadows, reflections, highlights, and color temperature. |
| 负面提示词 / Negative prompt | 仅在生成器支持时使用；删除与目标动态、虚化或文字需求冲突的词。 / Use only where supported; remove terms that conflict with intended motion, blur, or text. |

---

## 💡 核心原则 / Core principles

1. **叙事优先**：风格应支撑用户描述的画面，而不是把每张图变成同一个城市、人物或姿势。  
   **Story first:** style supports the requested image rather than forcing a single city, character, or pose.
2. **效果有选择地使用**：倾斜构图、耀斑、拖影和风的动态只在它们增强画面时加入。  
   **Use effects selectively:** add Dutch angles, flare, motion blur, and wind only when they improve the image.
3. **主体清晰**：复杂环境必须服务于面部、动作和情绪的可读性。  
   **Keep the subject legible:** environmental richness must serve the face, action, and emotion.

---

## 📁 内容结构 / Contents

```text
soft_photo/
├── SKILL.md                       # Skill workflow and constraints
├── README.md                      # Bilingual release notes and usage notice
├── LICENSE.md                     # Bilingual non-commercial license
├── pay/                           # Optional voluntary-support QR codes
│   ├── AliPay.jpg
│   └── WeChatPay.jpg
└── references/
    ├── prompt-template.md         # Prompt template and optional modules
    ├── modular-prompt-library.md  # Scene, composition, lighting, and narrative modules
    ├── description-expansion.md   # Brief idea to detailed visual-brief workflow
    └── tonal-parameters.md        # High-contrast lighting prompts and settings
```

---

## ☕ 自愿支持 / Voluntary support

如果这个 Skill 对你有帮助，欢迎通过下方二维码自愿支持创作与维护。支持完全自愿、没有最低金额，也不会影响 Skill 的获取、功能或后续使用。

If this Skill is useful to you, you are welcome to support its creation and maintenance through the QR codes below. Support is entirely voluntary, with no minimum amount, and never affects access to, functionality of, or future use of the Skill.

<p align="center">
  <img src="./pay/AliPay.jpg" width="32%" alt="Voluntary support via Alipay">
  <img src="./pay/WeChatPay.jpg" width="32%" alt="Voluntary support via WeChat Pay">
</p>

## 🤝 商业使用 / Commercial use

如需商业使用、定制授权或合作，请通过 [1978255744@qq.com](mailto:1978255744@qq.com) 联系原始作者商议。未经事先书面授权，不得商业使用。

For commercial use, custom licensing, or collaboration, contact the original author at [1978255744@qq.com](mailto:1978255744@qq.com) to discuss terms. Commercial use is not permitted without prior written authorization.

---

## 📄 许可证 / License

本项目适用 [LICENSE.md](LICENSE.md) 中的非商业使用条款。  
This project is governed by the non-commercial terms in [LICENSE.md](LICENSE.md).
