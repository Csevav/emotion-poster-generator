# Emotion Poster Generator（情绪海报生成器）

[English](README.md)

一个 AI skill，能把一个主题、一张照片、一句短文案，或一批 prompt，转换成安静、极简的 zine 风格情绪海报——高留白的干净扫描纸面、一个象征性视觉锚点、具有方向感的实验排版，以及一个克制的强调色。

## 它能做什么

给定一个主题、物品、日记片段或参考照片,该 skill 会:

1. 判断 **模式（Mode）**——单图、文字驱动、照片驱动、批量,或系列。
2. 把主题归入一个 **类别（Category）**——水果、情绪、人物,或静物。
3. 选择一个 **视觉子风格（Substyle）**（`blue-signal`、`photo-window`、`fruit-specimen`、`person-obscured`、`text-field`、`object-archive`、`editorial-page`),决定画面的视觉语法。
4. 默认生成语义统一的英文文案包，把关键词、单行句和正文块组织成点、线、面，并建立三档灰度层级。
5. 从九种纸张基底中按主题选择颜色、纹理和强度，避免每张海报使用相同底色。
6. 按四段式结构编译最终的图像 prompt（画布与构图 / 主体与锚点 / 排版与强调色 / 情绪与负面约束),遵循一套严格的构图与配色规则。
7. 生成图像,通过质量校验（Quality Gate）,返回图像、最终 prompt,以及一段简短的解读说明。

批量请求（列表、表格,或 CSV 形式的多个主题）会生成一份完整的产出,包含索引表和每张海报各自的小节。

## 运行环境要求

图像生成这一步依赖所在 AI agent 环境自带的文生图能力。目前已验证可以在具备图像生成能力的 **Codex** 环境中完整运行。**Claude Code CLI 本身不带图像生成能力**，所以在纯 Claude Code CLI 环境下，本 skill 只能走完 Mode/Category/Prompt Compiler 流程、产出最终的 prompt 文本，无法直接生成图片文件。

## 示例

| 柠檬 | 下雨天 |
| --- | --- |
| ![柠檬](examples/lemon.png) | ![下雨天](examples/rainy-day.png) |

## 仓库内容

| 文件 | 说明 |
| --- | --- |
| [`SKILL.md`](SKILL.md) | skill 的完整定义——模式/类别/子风格的路由规则、prompt 编译器、配方（recipe）维度、质量校验、输出格式。 |
| [`prompt-recipes.md`](prompt-recipes.md) | 按内容类别整理的参考配方。 |
| [`references/style-study.md`](references/style-study.md) | 对 163 篇公开笔记封面的综合视觉研究、文字引擎、构图原型与反例。 |
| [`references/cases/`](references/cases/) | 12 张低体积代表案例，仅供内部视觉校验，不作为图生图参考。 |
| [`batch-input.example.csv`](batch-input.example.csv) | 标准化批量输入格式示例（`id, theme, copy, mood, accent, reference_image, notes`）。 |
| [`batch-output.example.md`](batch-output.example.md) | 一份批量产出的渲染示例。 |

## 使用方式

这是一个 AI skill——把 `SKILL.md`（以及配套的参考文件）放进支持 skill 的 AI 助手/agent 平台的技能目录里（例如 Claude Code,或任何能够加载 `SKILL.md` 格式 skill 的系统）。当用户的 prompt 是在要求稀疏、极简的情绪海报风格图像时,助手会自动调用它。

示例请求:

- "用这个 skill 做一张关于周末的图"
- "主题：橘子汽水，文案：夏天慢慢醒来"
- "把这张照片做成安静情绪海报"
- "批量生成 9 张，主题分别是：周末、看星星、失眠、橘子、风筝、梨、夏天、向内生长、海边"

## License

[MIT](LICENSE)
