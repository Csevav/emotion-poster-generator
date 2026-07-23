---
name: emotion-poster-generator
description: 根据主题、照片、简短文案、日记片段、水果、情绪、人物、静物、清单、表格或批量简报，生成一张或多张安静克制的 zine 风情绪海报。当用户想要留白极大的竖版纸质海报——画面里只有一个极小的象征性视觉锚点、精细的微型排版、扫描纸质纹理，以及一个克制但高辨识度的强调色——时使用本 skill。
version: 1.0.0
tags: [image-generation, poster-design, prompt-engineering, batch-generation, zine-aesthetic]
---

# 情绪海报生成器 (Emotion Poster Generator)

把用户的 prompt 转换成生成的位图图像，以及可追溯的最终 prompt。

## 运行环境要求

⚠️ 本 skill 的"生成图像"这一步，依赖所在 AI agent 环境自带的文生图（text-to-image）能力。

- 目前已验证可以在具备图像生成能力的 **Codex** 环境中完整运行——走完 Mode/Category/Prompt Compiler 流程后，agent 会直接调用图像生成能力产出真实图片文件。
- **Claude Code CLI 本身不自带图像生成能力**。在纯 Claude Code CLI 环境下，本 skill 只能走完 Mode / Category / Prompt Compiler 的推理流程，产出最终的图像生成 prompt 文本，但无法直接生成图片文件。
- 如果所在环境没有可用的文生图工具：请照常完成 Workflow 中 1-3 步（解析、选配方、编译 prompt），在第 4 步"生成图像"处明确告知用户当前环境不具备生图能力，并把编译好的最终 prompt 原样交给用户，由用户拿去有文生图能力的工具（例如接了图像生成能力的 Codex、Midjourney、DALL·E 等）执行生成。不要假装已经生成了图片。

## 何时使用这个 Skill (When to Use This Skill / 触发条件)

在用户提出以下需求时触发本 skill：

- 想要一张安静、极简的"情绪海报"（emotion poster），素材来自一个主题、情绪、照片、日记片段或短文案
- 想要从一份清单、表格，或一批主题的 CSV，批量生成一系列这样的海报
- 想把一张照片转换成留白很大、有纸张纹理和微型排版的 zine 风海报

不要用它来做写实修图、完整场景插画、商业广告/海报版式，或字面意义上的人物肖像摄影——这些都超出本 skill 的视觉语法范围。

本 skill 同时支持单图和批量生产。根据用户的 prompt 自行判断模式、内容类别和视觉子风格，而不是让用户去挑选另一个 skill。

目标图像语言是"安静极简的 zine 风情绪海报"：高留白的做旧纸张、一个极小的视觉事件、精确的微型排版，以及一个令人印象深刻的强调色。保留稀疏情绪海报作品的精神内核，但不要照搬任何创作者的具体版式、标题格式、签名、水印、重复出现的专有标记，或已有图像。

## 模式路由（Mode Routing）

根据用户的 prompt 选择一种模式。

- Single Mode（单图模式）：一个主题、句子、物件、照片，或一种情绪。
- Text Mode（文字驱动模式）：主要输入是一句话、一段文字、一首诗、一句引言、一个标题，或一段日记。
- Photo Mode（照片驱动模式）：用户提供一张或多张图片，要求转换成本海报体系。
- Batch Mode（批量模式）：用户要求"batch"、"一组"、"多张"、"批量"、"系列"，或给出了一份清单、表格、CSV、文件夹，或多个独立条目。
- Series Mode（系列模式）：用户想要一组视觉上连贯、配方相关的海报。

优先级规则：

- 一份清单或表格里有 2 个或以上独立条目，判定为 Batch Mode。
- 提供一张照片加一句简报，判定为 Photo Mode。
- 提供多张照片，或一个照片文件夹加多份简报，判定为 Batch Mode 或 Series Mode。
- 一段较长的文字，除非其中包含多个独立的海报条目，否则应判定为 Text Mode。
- 如果 prompt 含糊不清，且不同判断会显著改变成本或产出数量，向用户提出一个简短的澄清问题。

## 类别路由（Category Routing）

选定模式后，把每个输出归入一个视觉类别。

- Fruit（水果）：苹果、梨、橙子、番茄、番石榴、柠檬、西瓜、草莓、樱桃、水果汽水、以水果形式出现的食物。
- Mood（情绪）：空、压力、治愈、等待、慢下来、孤独、脆弱、平静、记忆、呼吸、发呆、自由、光、雨、夜晚。
- People（人物）：自我、孩子、女性、老年、凝视、关系、对话、关怀、自由、脆弱、身体、姿态、肖像类 prompt。
- Still Object（静物）：风筝、时钟、陶瓷、灯笼、贝壳、咖啡、树枝、花、树、纸、椅子、锥形物、扇子、窗、书、日常物件。

类别判定规则：

- 如果 prompt 点名了一种具体水果，即便文案很情绪化，也归为 Fruit。
- 如果 prompt 点名了一个人或肖像，归为 People，但除非用户明确要求正面写实肖像，否则避免字面意义上的正脸构图。
- 如果 prompt 点名了一个非水果的实体物件，归为 Still Object。
- 如果 prompt 是抽象的或以情绪为主，归为 Mood。
- 批量生产时，为每一行记录类别，让视觉语法有意地产生变化。

## 分类视觉语法（Category Grammars）

在选定最终配方之前，先套用以下按类别划分的视觉语法。

### Fruit（水果）

- 把水果当作标本、切面、半透明切片、撕纸印刷,或一次小型色彩研究来处理。
- 水果簇放在画面中心或略低于中心；保持足够小，让纸张本身先被读到。
- 使用一种高辨识度的水果色：番茄红、苹果红、浅黄、番石榴粉、柑橘黄、暖橙,或柔和绿。
- 加入微型标签、极小的日期/天气文字、若隐若现的类似成分说明,或几乎看不清的编辑体文字碎片。
- 避免可爱的水果贴纸、生鲜广告、多汁的商业食物摄影、盘子、桌子、手,以及完整的静物场景。

### Mood（情绪）

- 把情绪转化成一个抽象但可成像的符号：蓝色圆点、散落的星星、一条细线、一小片阴影、一个灰色色块、雾蒙蒙的纸窗、一处极小的远景,或一张稀疏的图解。
- 主体可以几乎"什么都没有"；情绪张力应该来自位置、留白、纸张色调和微型排版本身。
- 电光蓝、钴蓝、浅青、灰黑,或一个极小的红色标记都很合适。
- 使用简短的诗意文字、断裂的词语、小小的注解、序号,或低对比的"幽灵文字"。
- 避免字面意义的表情符号、治愈系海报式语言、鸡汤金句版式、大幅书法,或装饰性的色块团。

### People（人物）

- 不要默认画成写实肖像。把"人"转译成剪影、被裁切的姿态、阴影、极小的背影、纸质剪影、照片碎片、一条视线,或某个代指人的物件。
- 除非用户明确要求一个可辨认的人物，否则脸部应保持极小、局部、被遮挡,或干脆不出现。
- 使用纪实风格的微型文字、日期/地点注解、一句安静的文案,以及附着在"人物符号"上的一小块强调色。
- 好用的锚点：一个小外套剪影、一个手部裁切、作为纸张纹理的一双眼睛、一个极小的行走人影、一张撕破的证件照碎片、一把椅子、一扇窗,或一片阴影。
- 避免时装编辑大片、写实证件照式头像、美妆写真、电影感人物场景、社交媒体金句卡片,以及煽情插画。

### Still Object（静物）

- 把物件当作一份扫描标本，或纸上的一件小型博物馆标签物品来处理。
- 只用一个物件，或一个物件加一小块纸张/照片碎片。
- 优先选择细线条的树枝图解、旧扇子、时钟、陶瓷、贝壳、风筝、花、纸片、杯子、书、灯笼、窗,或日常工具。
- 给物件配上微型注解、少量英文字词碎片、日期/天气、一个极小的索引号,或类似测量数据的排版。
- 避免产品广告感、写实的桌面摄影、温馨生活方式场景、密集拼贴、大面积阴影,以及明显的样机效果。

## 视觉子风格路由（Visual Substyle Routing）

完成类别路由后，选择一种视觉子风格。子风格控制画面语法；内容类别控制主体会变成什么。

- `blue-signal`：饱和的蓝色圆点、蓝色文字、蓝色笔刷/剪切标记,或蓝色碎片承载情绪。
- `photo-window`：一张小照片、两张叠放的照片面板，或一条窄窄的竖向小图条浮在纸面上。
- `fruit-specimen`：水果被处理成切面、半透明切片、老式印刷标本,或一次小型色彩研究。
- `person-obscured`：人物以极小的背影、被裁切的姿态、阴影、证件照碎片,或被遮挡的脸出现。
- `text-field`：排版本身是主要的视觉事件；图像可以缺席或退居次要。
- `object-archive`：一件非水果物件变成带标签、测量文字或图解标记的扫描标本。
- `editorial-page`：更接近杂志式的构图，有更大的文字、长段的幽灵文字、装订本/书页的质感，或分层的文字块。

子风格选择规则：

- Fruit 通常从 `fruit-specimen` 起手；只有当水果与天空、田野、季节,或记忆搭配时，才用 `photo-window`。
- Mood 可以用 `blue-signal`、`text-field`、`photo-window`,或 `editorial-page`。
- People 通常用 `person-obscured`；记忆/背影类场景用 `photo-window`，身份/自我定义类 prompt 用 `text-field`。
- Still Object 通常用 `object-archive`；贝壳、圆点、星星,或抽象物件场时用 `blue-signal`；海、天空、雪,和风景碎片用 `photo-window`。
- 批量生产时轮换子风格，不要让每张图都变成同一种小照片窗口，或同一种蓝点场。

## 第一性原理 Prompt 字段（First-Principles Prompt Fields）

每条最终 prompt 都必须按顺序回答以下渲染问题。把答案当作具体的视觉约束来写，而不是分析性的散文。

1. 画布（Canvas）：竖版 3:5 纸质海报，满幅做旧纸张，不要边框或样机效果。
2. 注意力几何（Attention Geometry）：70%-90% 空白纸面，一个视觉簇或文字事件占画面约 8%-24%，除非所选子风格需要漂浮文字，否则不要贴边。
3. 内容类别（Content Category）：Fruit（水果）、Mood（情绪）、People（人物）,或 Still Object（静物）。
4. 视觉子风格（Visual Substyle）：`blue-signal`、`photo-window`、`fruit-specimen`、`person-obscured`、`text-field`、`object-archive`,或 `editorial-page` 之一。
5. 图像锚点（Image Anchor）：一个物件、一张照片裁切、一个剪影、一个色块、一个文字区域、一道痕迹,或一件标本。
6. 锚点处理方式（Anchor Treatment）：扫描纸张、旧照片、影印、网点、孔版印刷墨色、撕边、软边、套印错位、线条图解,或低对比印刷。
7. 排版系统（Typography System）：极小的衬线体/打字机体/等宽字体、破碎的中英文、日期/天气/地点、标签文字,或幽灵正文。
8. 色彩逻辑（Color Logic）：一个在缩略图尺寸下依然清晰可见的高辨识度色彩锚点，其余保持克制。
9. 分辨率与清晰度（Resolution and Clarity）：高分辨率原图、锚点边缘清晰、主要短文字可读，纹理作为印刷质感呈现而非模糊。
10. 情绪温度（Emotional Temperature）：安静、疏离、私密、诗意、档案感、稀疏、克制。
11. 硬性避免项（Hard Avoids）：不要完整场景、广告、大幅商业标题、贴纸拼贴、时装/美妆肖像、3D、霓虹、光面样机,或千篇一律的模板化精修感。

## 色彩引擎（Color Engine）

每张图使用一种主要的高辨识度色彩。

- 默认使用一个可见的、不透明或高饱和的色彩锚点：电光蓝、钴蓝、天蓝、番茄红、苹果红、番石榴粉、柑橘黄、浅黄、柔和绿,或暖橙。
- 保持纸张、灰阶照片、微型文字和次要标记的克制感。
- 色彩锚点大约占整个画布的 0.8%-3%，或占视觉簇的 15%-40%。
- 色彩可以是主体本身、一个笔刷/剪切标记、一个印刷色块、蓝色圆点、破碎字体、照片色调,或一个小的平面剪影。
- 不要用 `muted`（柔和）、`faded`（褪色）、`pastel`（粉彩）、`low saturation`（低饱和）,或 `near-monochrome`（近乎单色）这类措辞削弱主色，除非用户明确要求柔和的输出。
- 只有当海报依赖黑白档案/照片逻辑时，才用 `charcoal-black`（炭黑）作为强调色；否则选择一个彩色强调色。
- 批量生产时，至少一半的输出应该有清晰可见的彩色锚点，不要全是灰色照片和极小的黑色文字。

## 分辨率与清晰度（Resolution and Clarity）

低保真的印刷风格，不等于低分辨率的输出。

- 在 prompt 中要求高分辨率的竖版海报原图，适合在手机上清晰查看，也便于之后做 2 倍放大导出。
- 让纸张纹理、扫描噪点、网点、影印磨损和墨渍保持轻微，不要模糊到主锚点。
- 主要的短文字、日期标签、标本标签和主要的微型排版，字形应该清晰锐利。次要的幽灵文字可以半透明、半可读。
- 水果果肉纹理、照片窗口边缘、剪影、蓝色圆点、色块、树枝图解和物件轮廓，都应保持干净、边界清晰。
- 除非用户明确要求，否则避免使用 `blurry`（模糊）、`out of focus`（失焦）、`soft overall image`（整体柔焦）、`low resolution`（低分辨率）、`pixelated`（像素化）,或 `heavy degradation`（严重劣化）这类措辞。
- 如果内置生成器返回的图像尺寸较小，向用户报告实际的像素尺寸。用于正式项目时，应重新生成或请求更高分辨率的版本，而不是把小尺寸预览图当作最终成品。

## 输入契约（Input Contract）

对于批量任务，接受 CSV 行、Markdown 表格、编号列表、纯主题清单，或一个参考图片文件夹加一段简短简报。

将批量输入内部归一化为：

```csv
id,theme,copy,mood,accent,reference_image,notes
001,橘子汽水,夏天慢慢醒来,summer,warm-orange,,
```

必填字段：

- `id`：稳定的输出编号。如果缺失就自己创建一个。
- `theme`：中心主题或想法。

可选字段：

- `copy`：要出现在图中的确切短句。
- `mood`：情绪方向。
- `accent`：用户指定的强调色。
- `reference_image`：本地路径，或已附带图片的角色说明。
- `notes`：约束条件、目标平台、画幅比例，或系列方向。

当用户提供的文字是要出现在图像中的内容时，保持原文精确不变。对于较长的文案，为图像本身提炼出一句短语，其余部分作为解读上下文保留。

## Prompt 编译器（Prompt Compiler）

把每条最终图像 prompt 写成四段紧凑的段落，只描述画面里可见的像素。

第一段：画布与构图

- 竖版纸质海报，默认 3:5。只有当用户或目标平台要求时才用 4:5。
- 暖白、米白、浅灰、灰米色，或轻微做旧的哑光纸张。
- 70%-90% 安静的空白纸面。
- 一个小的视觉簇，大约占画布的 8%-24%。
- 视觉簇位置：居中、略高于中心、略低于中心、左下、右上，或一个安静的偏心位置。
- 不要边框、写实相框、app UI，或产品样机效果。

第二段：主体与图像锚点

- 根据类别语法和视觉子风格，把主题转化成一个可成像的锚点。
- 锚点在缩略图尺寸下必须清晰可辨，但在整张海报上依然物理意义上很小。
- 好用的锚点：水果切面、植物枝条、星场、蓝点星座、蓝色笔刷遮罩、小张照片裁切、撕纸色块、细线图解、日常物件、极小剪影、被遮挡的脸、阴影、窗、风景碎片、幽灵文字块，或抽象的情绪符号。
- 如果提供了照片，把它当作版面内的一张小纸质剪贴、一张联系样片、一块洗印过的照片面板，或一个裁切碎片来处理。
- 用一个清晰的隐喻，而不是一整个完整的插画场景。

第三段：排版、强调色与印刷质感

- 使用极小的衬线体、等宽字体、打字机体，或精致的编辑体标注文字。
- 用中文或英文写一句简短可读的短语，再加上可以部分难以辨认的可选微型文字。在 `text-field` 和 `editorial-page` 里，排版可以成为主要的视觉事件。
- 可选微型文字：日期、天气、地点、材料标签、索引号、极小的档案注记、测量数据、破碎的英文单词、散落的字母，或低对比的正文文字区域。
- 使用色彩引擎里一种克制但清晰可见的强调色；它应该在缩略图尺寸下承载整张海报的记忆点。
- 加入纸纤维、扫描噪点、淡淡的铅笔痕迹、孔版印刷颗粒、轻微墨渍、影印质感、洗印感,或网点劣化。
- 保持主锚点边缘和主要短文字清晰；纸张瑕疵应该停留在表层，不要糊到主体上。

第四段：情绪与负面约束

- 平铺直叙、正视角的扫描纸张氛围。
- 安静、私密、诗意、缓慢、通透、克制、略带怀旧、编辑感、低保真印刷。
- 避免满版场景、商业广告、大幅标题、logo、CTA、光面样机、生硬阴影、电影感打光、3D、霓虹、动漫风、可爱贴纸、密集拼贴、图库摄影式写实、鸡汤金句海报,以及千篇一律的通用 AI 海报精修感。

## 配方维度（Recipe Axes）

每张图从每个维度中选一个值。批量生产时，在保持系列方向一致的前提下，让各行之间的配方产生变化。

### 版式（Layout）

- `center-specimen`：一个极小的物件或照片碎片，居中放在大片空白纸面上
- `lower-left-diary`：小视觉簇偏左下，上方留白安静
- `upper-right-note`：右上方一小块纸/照片，配松散的微型文字
- `micro-contact-sheet`：3-6 个极小的画格，排成一张紧凑的联系样片
- `paper-fragment-stack`：两三张互相叠放的纸片
- `type-and-object`：一句短语加一个小物件组成视觉簇
- `blue-dot-field`：饱和蓝色圆点稀疏地散布在安静纸面上
- `blue-brush-mask`：一笔饱和的蓝色笔刷或纸条，遮住一张脸、一个字，或一小张图
- `star-orbit`：星星、圆点，或散落字母松散地环绕一个小锚点
- `fruit-cutaway-study`：水果切片或切面，作为一份极小的标本
- `thin-diagram`：环绕一个物件的细线注解
- `small-window-block`：一小块方形照片/色块，配微型标签
- `vertical-photo-strip`：两三张极小照片窗口竖向叠放
- `dual-photo-panel`：两张相邻或叠放的照片面板，中间留一道窄缝
- `quiet-silhouette`：一个极小的人物、阴影、姿态,或局部人影，置于空白纸面上
- `ghost-text-page`：一大片淡淡的文字区域或正文色块，成为背景纹理
- `type-as-object`：更大幅的实验性文字，作为主要锚点

### 锚点（Anchor）

- `fruit-specimen`
- `translucent-fruit-slice`
- `blue-dot-constellation`
- `blue-brush-obscuration`
- `scattered-star-sign`
- `thin-branch-diagram`
- `tiny-faded-photo`
- `washed-paper-block`
- `paper-clipping`
- `small-landscape-window`
- `daily-object-specimen`
- `quiet-person-silhouette`
- `partial-gesture-crop`
- `obscured-face-fragment`
- `shadow-or-trace`
- `ghost-body-text`
- `abstract-texture-window`
- `micro-contact-sheet`

### 排版（Typography）

- `tiny-caption`
- `edge-phrase`
- `archive-microtext`
- `broken-english-fragments`
- `date-weather-label`
- `scattered-letters`
- `vertical-note`
- `gray-ghost-text`
- `large-quiet-type`
- `body-copy-texture`
- `almost-textless`
- `specimen-label`
- `small-title-plus-index`

### 纹理（Texture）

- `aged-paper-fibers`
- `soft-scan-noise`
- `xerox-softness`
- `risograph-grain`
- `light-ink-bleed`
- `faint-pencil-annotation`
- `washed-photo-print`
- `subtle-halftone`
- `low-contrast-photocopy`

### 情绪（Mood）

- `summer`
- `quiet`
- `solitude`
- `inward`
- `afternoon`
- `night`
- `seaside`
- `childhood`
- `memory`
- `fruit-soda`
- `waiting`
- `small-joy`
- `rainy`
- `sleepy`
- `breathing`
- `vulnerable`
- `slow`
- `blank`

### 强调色（Accent）

- `electric-blue`
- `cobalt-blue`
- `sky-blue`
- `pale-cyan`
- `tomato-red`
- `apple-red`
- `guava-pink`
- `citrus-yellow`
- `pale-yellow`
- `soft-green`
- `warm-orange`
- `charcoal-black`

## 工作流程（Workflow）

1. 解析用户的内容。
   - 识别模式、类别、视觉子风格、中心主题、情绪、用户提供的确切文字（如有）、视觉隐喻，以及是否使用了参考图片。
   - 对于复杂的想法，把它压缩成一个可成像的隐喻。
   - 如果用户没有提供图内文字，用用户所用的语言，创作一句简短的诗意短语。

2. 选择一套变化配方。
   - 在有用时，从 `prompt-recipes.md` 里挑选一个对应类别的配方。
   - 选定子风格、版式、锚点、排版、纹理、情绪,和强调色。
   - 批量生产时，除非用户要求严格的系列一致性，否则避免重复同一种子风格或版式。
   - 如果构图变得拥挤，先移除物件，而不是压缩留白。

3. 为每个输出编译一条最终图像 prompt。
   - 使用四段式 Prompt 编译器。
   - 只在有必要时指定图内确切文字。
   - 保持主要可读文字简短，因为图像模型经常会扭曲较长的文字。
   - 说明锚点位置、大致尺寸、强调色，以及纸张处理方式。
   - 明确说明这是一张平铺、被扫描的图像，不是一个场景、样机,或广告。

4. 生成图像。
   - 默认使用所在环境内置的图像生成能力。
   - 如果所在环境（如纯 Claude Code CLI）没有可用的图像生成能力，明确告知用户，并把编译好的最终 prompt 原样交给用户，供其在有文生图能力的工具中使用；不要虚构或假装已生成图片。
   - 每一批量行，先生成一张图。
   - 只有当输出未通过质量校验（Quality Gate），或用户要求变体时，才重新生成。
   - 除非用户明确要求仅输出 prompt，否则不要在只给出 prompt 后就停下。

5. 记录本次运行。
   - 单图任务：返回图像、最终 prompt、类别、配方，以及一段简短的解读说明。
   - 批量任务：维护一份索引，每个输出各占一个小节。

## 系列规则（Series Rules）

对于一个系列，保持以下内容一致：

- 画幅比例
- 纸张色调
- 整体文字尺度
- 整体留白纪律
- 图像处理风格家族
- 每一行一种视觉类别，并记录在输出索引中
- 每一行一种视觉子风格，并记录在输出索引中

在不同图像之间做出变化：

- 版式位置
- 锚点隐喻
- 视觉子风格
- 强调色色相
- 排版行为
- 纹理模式

对于一个连贯的 9 张图批量任务，最多使用 3 种纸张色调，最多使用 5 种强调色。

## 质量校验（Quality Gate）

在返回之前，检查每一张生成的图像：

- 是否是竖版纸质海报，最好是 3:5？
- 是否有 70%-90% 的画面是空白纸张？
- 是否只有一个主要视觉锚点？
- 锚点是否够小，但在缩略图尺寸下依然可辨认？
- 类别语法是否与主题匹配？
- 视觉子风格是否与类别匹配，并避免和最近的输出重复？
- 排版是否微小、精致、编辑感十足，而不是大幅标题？
- 是否有一种克制但高辨识度的强调色？
- 强调色在缩略图尺寸下是否可见，且面积足以被读到？
- 主锚点、照片窗口边缘、水果/物件轮廓,和主要短文字，是否在手机屏幕上足够清晰？
- 画面是否给人扫描、印刷、做旧、低保真的感觉，而不是数字感很强的"干净"？
- 是否避免了照搬某个具体创作者的签名、水印、标题格式，或已有图像？
- 是否避免了满版插画、密集的拼贴本、光面广告感、3D、霓虹、动漫风、可爱贴纸、鸡汤金句卡片、商业封面设计,以及图库摄影式写实？

如果某个输出未通过，用更强的约束重新生成一次。

## 输出格式（Output Format）

单图输出：

````markdown
**生成图**

![emotion poster](absolute-image-path-or-rendered-image)

**最终 Prompt**

```text
[final prompt used for image generation]
```

**说明**

- Mode: [Single / Photo / Text]
- Category: [Fruit / Mood / People / Still Object]
- Substyle: [blue-signal / photo-window / fruit-specimen / person-obscured / text-field / object-archive / editorial-page]
- Recipe: [substyle / layout / anchor / typography / accent / texture / mood]
- [一句简短说明，解读了用户输入的哪些内容]
````

批量输出：先返回一份简明索引，再逐个给出每张图的小节：

````markdown
# Batch Run: [run name]

| ID | Category | Substyle | Theme | Output | Recipe | Review |
| --- | --- | --- | --- | --- | --- | --- |
| 001 | Fruit | fruit-specimen | 橘子汽水 | 001-orange-soda.png | fruit-specimen / fruit-cutaway-study / translucent-fruit-slice / tiny-caption / warm-orange / aged-paper-fibers / summer | pass |

## 001 - 橘子汽水

![001 - 橘子汽水](absolute-image-path-or-rendered-image)

```text
[final prompt]
```
````

## 示例请求

- "用这个 skill 做一张关于周末的图"
- "主题：橘子汽水，文案：夏天慢慢醒来"
- "把这张照片做成安静情绪海报"
- "批量生成 9 张，主题分别是：周末、看星星、失眠、橘子、风筝、梨、夏天、向内生长、海边"
