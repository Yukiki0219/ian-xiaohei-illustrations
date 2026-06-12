# Black-and-White Technical Line Art Illustrations

> 将技术内容（流程、架构、判断、隐喻）转为黑白技术线描插画，适用于技术文档、产品文档、博客与方法论文章的正文配图。
>
> 16:9 横版 | 纯白背景 | 黑色技术线描 | 强调结构与动作 | Codex Skill（风格分支）

---

## 这个仓库是什么

本仓库是对原有 Ian Xiaohei Illustrations 的风格分支，目标是支持 "Black-and-White Technical Line Art" 风格的正文配图生成。它为 Codex Skill 提供风格规范、示例、提示模板与可复用资产，帮助 AI Agent 将文章中的判断、流程、结构或隐喻可视化为清晰的黑白技术线描插画。

该分支关注点：

- 纯白背景，黑色线条为主，线条清晰且保留少量手绘抖动感以维持人手绘质感；
- 强调技术感与信息传达（适合架构、工作流、系统说明类内容）；
- 每张图只表达一个核心认知动作或结构，避免变成说明书式的信息密集图；
- 插画中应包含主角或示意元素来承担核心动作（技术示意符号、人物轮廓或设备原型均可）；

---

## 适合谁用

特别适合：

- 需要为技术文章、产品文档、流程说明、架构解析或方法论写作配图的人；
- 希望图像保持干净、结构化且具有一定手绘质感的内容生产者；
- 想把抽象判断或系统行为可视化为工程/技术隐喻的作者。

不适合：

- 需要商业广告级别的彩色海报或品牌 KV（请使用专业商业插画服务）；
- 需要儿童卡通、表情包或过度拟人化的吉祥物风格；
- 需要严格可编辑的矢量源文件（SVG/AI）作为最终交付物的人（本 Skill 输出为 PNG）。

---

## 输出内容

默认输出：

- 16:9 横版 PNG 插画（黑白技术线描）
- 一篇文章的 4-8 张 shot list（由 Agent 提供）
- 每张图的主题说明、核心意思、结构类型与简短中文标注建议
- 最终 PNG 图片保存路径： `assets/<article-slug>-illustrations/`

默认不输出：

- PPTX / PDF / Keynote 源文件
- 可编辑矢量源（如 AI / SVG 作为交付）
- 彩色商业海报或复杂信息图

---

## 视觉规范（Black-and-White Technical Line Art）

- 背景：纯白（#FFFFFF）；不使用纸纹、渐变或阴影效果；
- 线条：黑色线描（#000000），线宽按导出分辨率调整，保留轻微的手绘抖动以保持自然感；
- 配色：仅使用黑/白为主；如需注记，优先使用灰度或非常克制的单色（默认禁用彩色注记）；
- 构图：大量留白；主体占比约 30%–60%；每张图仅表达一个核心动作或结构；
- 元素：使用技术符号（图标化的服务器、流程块、箭头、连线）、简洁人物轮廓或设备示意；
- 禁止：不使用渐变阴影、丰富色彩填充、过度卡通化的处理、或将插画做成 PPT 式信息图。

---

## 示例效果

> 下列示例文件存放于 `examples/images/`，本分支会提供对应的黑白技术线描示例（示例文件将在 PR 中新增或替换）。

示例：

- `examples/images/01-two-breakpoints.png`
- `examples/images/02-sort-by-purpose.png`
- `examples/images/03-one-fish-many-uses.png`
- `examples/images/04-handoff-path.png`

（合并到主分支前，你可以在分支中检查示例预览）

---

## 安装与使用

克隆仓库并使用：

```bash
git clone https://github.com/Yukiki0219/ian-xiaohei-illustrations.git
cd ian-xiaohei-illustrations
```

将 skill 文件夹复制到 Codex 的 skills 目录：

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R ./ian-xiaohei-illustrations "${CODEX_HOME:-$HOME/.codex}/skills/"
```

在 Codex 中使用示例：

```text
Use $ian-xiaohei-illustrations 以 Black-and-White Technical Line Art 风格为这篇文章生成 4 张插图。
要求：16:9 横版、纯白背景、黑色技术线描、简短中文注记（如需）。
```

---

## 怎么用（示例 prompt）

### 只做配图规划

```text
Use $ian-xiaohei-illustrations 先不要生成图片。
请分析下面这篇文章哪里值得配图，输出 5 张左右的 shot list。
每张图写清楚：放在哪段后、主题、核心意思、结构类型、主角/示意元素在图里做什么、建议中文标注词。

<粘贴文章>
```

### 直接生成正文配图

```text
Use $ian-xiaohei-illustrations 把下面这篇文章生成 4 张 16:9 黑白技术线描插图。
要求：纯白背景、黑色技术线描、每张图只讲一个核心结构、中文标注尽量精简。

<粘贴文章>
```

更多示例见 `examples/prompts.md`。

---

## 工作流程与 QA

本 Skill 的工作流程保留原有的步骤：消化正文、输出 shot list、单张生成并检查 QA。QA 检查要点示例：

- 画面是否为纯白背景？
- 线条是否为黑色技术线描、避免彩色填充？
- 是否只表达一个核心结构或动作？
- 中文注记是否短且准确？
- 是否避免 PPT 式的拥挤流程图？

---

## 目录结构（示意）

```
.
├── README.md
├── LICENSE
├── NOTICE.md
├── assets/
│   └── my-ip/
│       ├── images/
│       ├── thumbnails/
│       ├── metadata.json
│       └── LICENSE
├── examples/
│   ├── images/
│   │   ├── 01-two-breakpoints.png
│   │   ├── 02-sort-by-purpose.png
│   │   └── ...
│   └── prompts.md
└── ian-xiaohei-illustrations/
    ├── SKILL.md
    ├── agents/
    ├── assets/
    └── references/
        ├── style-dna.md
        ├── technical-lineart.md
        ├── composition-patterns.md
        ├── prompt-template.md
        └── qa-checklist.md
```

---

## License

MIT License. See [LICENSE](LICENSE).
