---
name: emotion-poster-generator
description: Generate one or many quiet emotion posters and stationery-cover images from themes, photos, short copy, diary notes, objects, moods, lists, tables, or batch briefs. Use when the user wants sparse vertical paper posters with large negative space, small visual anchors, delicate typography, handmade stationery texture, and restrained color accents.
---

# Emotion Poster Generator

Turn the user's prompt into generated raster images plus traceable prompts.

This skill supports both single-image and batch production. Choose the mode from the user's prompt rather than asking the user to pick a separate skill.

It abstracts public visual methods common in quiet emotion posters, stationery design, and social cover layouts. Do not copy a specific creator's exact layout, signature, wording, watermark, recurring proprietary marks, or existing images.

## Mode Routing

Use the user's prompt to choose a mode.

- Single Mode: one theme, sentence, object, photo, or mood.
- Text Mode: the main input is a sentence, paragraph, poem, quote, title, or diary note.
- Photo Mode: the user provides one or more images to transform into the poster system.
- Batch Mode: the user asks for "batch", "一组", "多张", "批量", "系列", or gives a list, table, CSV, folder, or multiple independent items.
- Series Mode: the user wants a visually coherent set with related recipes.

Priority rules:

- A list or table with 2 or more independent items means Batch Mode.
- One supplied photo plus one brief means Photo Mode.
- Multiple photos, or a photo folder plus multiple briefs, means Batch Mode or Series Mode.
- A long paragraph should become Text Mode unless it contains multiple separate poster items.
- If the prompt is ambiguous and the choice would materially change cost or output count, ask one concise clarification.

## Input Contract

For batch work, accept CSV rows, Markdown tables, numbered lists, plain lists of themes, or a folder of reference images plus a short brief.

Normalize batch inputs internally to:

```csv
id,theme,copy,mood,accent,reference_image,notes
001,橘子汽水,夏天慢慢醒来,summer,warm-orange,,
```

Required fields:

- `id`: stable output ID. Create one if missing.
- `theme`: central subject or idea.

Optional fields:

- `copy`: exact short in-image phrase.
- `mood`: emotional direction.
- `accent`: requested accent color.
- `reference_image`: local path or attached image role.
- `notes`: constraints, target platform, aspect ratio, or series direction.

Keep user-supplied text exact when it is meant to appear in the image. For long copy, extract one short phrase for the image and keep the rest as interpretation context.

## Prompt Compiler

Write each final image prompt as four compact paragraphs describing visible pixels only.

Paragraph 1: canvas and composition

- Tall vertical poster, default 4:5 unless the user asks otherwise.
- Warm white, off-white, pale gray, or lightly aged matte paper.
- 65%-90% quiet empty paper.
- One small visual cluster, roughly 10%-28% of the canvas.
- Cluster position: center, upper-middle, lower-middle, lower-left, or upper-right.
- No border, realistic frame, app UI, or mockup.

Paragraph 2: subject and image anchor

- Convert the theme into one imageable anchor.
- Good anchors: fruit, plant, star, window, paper scrap, daily object, small photo crop, landscape fragment, hand-drawn specimen, or abstract emotional symbol.
- If a photo is supplied, treat it as a small paper clipping, contact sheet, washed photo panel, or cropped fragment inside the layout.
- Prefer one clear metaphor over a complete illustrated scene.

Paragraph 3: typography, accent, and print behavior

- Use small serif, monospaced, typewriter, or delicate editorial caption text.
- Use one short readable phrase in Chinese or English.
- Optional microtext: date, weather, place, material label, index number, or tiny archive note.
- Use one restrained but visible accent color.
- Add paper fibers, scan noise, faint pencil marks, risograph grain, light ink bleed, xerox softness, or halftone degradation.

Paragraph 4: mood and negative constraints

- Flat orthographic scanned-paper mood.
- Quiet, diary-like, gentle, private, poetic, slow, handmade, airy, slightly nostalgic.
- Avoid full-bleed scenes, commercial ads, large headlines, logos, CTA, glossy mockups, hard shadows, cinematic lighting, 3D, neon, anime, cute stickers, dense collage, and stock-photo realism.

## Recipe Axes

Pick one value from each axis for every image. For batch work, vary the recipe across rows while preserving the requested series direction.

### Layout

- `center-specimen`: one tiny object or photo fragment centered in large empty paper
- `lower-left-diary`: small cluster low and left, with quiet empty upper space
- `upper-right-note`: tiny paper/photo block upper-right with loose microtext
- `six-card-contact-sheet`: 4-6 small panels arranged as a tiny contact sheet
- `paper-fragment-stack`: two or three overlapping scraps
- `type-and-object`: short phrase and one small object form the cluster
- `star-orbit`: stars, dots, or scattered letters loosely orbit a small anchor
- `fruit-study`: fruit or botanical element as a stationery specimen
- `thin-diagram`: fine annotation lines around one object

### Anchor

- `tiny-faded-photo`
- `paper-clipping`
- `botanical-specimen`
- `fruit-specimen`
- `hand-drawn-line-object`
- `small-monochrome-landscape`
- `irregular-color-scrap`
- `thin-annotation-diagram`
- `abstract-texture-window`
- `mini-contact-sheet`

### Typography

- `tiny-caption`
- `edge-phrase`
- `archive-microtext`
- `scattered-letters`
- `vertical-note`
- `gray-ghost-text`
- `almost-textless`
- `specimen-label`
- `small-title-plus-index`

### Texture

- `paper-fibers`
- `soft-scan-noise`
- `xerox-softness`
- `risograph-grain`
- `light-ink-bleed`
- `faint-pencil-annotation`
- `washed-photo-print`
- `subtle-halftone`

### Mood

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

### Accent

- `cobalt-blue`
- `ultramarine`
- `leaf-green`
- `lemon-yellow`
- `tomato-red`
- `cherry-red`
- `pale-cyan`
- `warm-orange`
- `lavender`
- `fruit-pink`

## Workflow

1. Parse the user's content.
   - Identify central subject, mood, exact text if supplied, visual metaphor, and whether reference images are used.
   - For a complex idea, reduce it to one imageable metaphor.
   - If no image text is supplied, invent one short poetic phrase in the user's language.

2. Select a variation recipe.
   - Pick layout, anchor, typography, texture, mood, and accent.
   - For batches, avoid repeating the same layout unless the user asks for strict series consistency.
   - If the composition becomes dense, remove objects before reducing empty space.
   - Optional: use `prompt-recipes.md` for quick recipe selection.

3. Compile one final image prompt per output.
   - Use the four-paragraph Prompt Compiler.
   - Specify the exact in-image phrase only when useful.
   - Keep text short because image models often distort long text.
   - State anchor location, approximate size, accent color, and paper treatment.

4. Generate images.
   - Use built-in image generation by default.
   - For each batch row, generate one image first.
   - Regenerate only when the output fails the Quality Gate or the user asks for variants.
   - Do not stop after prompt-only unless the user explicitly asks for prompt-only.

5. Record the run.
   - For one image, return image, final prompt, recipe, and a short interpretation note.
   - For batch work, maintain an index with one section per output.

## Series Rules

For a series, keep these consistent:

- aspect ratio
- paper tone
- general text scale
- overall negative-space discipline
- image treatment family

Vary these across images:

- layout position
- anchor metaphor
- accent hue
- typography behavior
- texture mode

For a coherent 9-image batch, use no more than 3 paper tones and no more than 5 accent hues.

## Quality Gate

Before returning, check every generated image:

- Is it vertical and paper-like?
- Is 65%-90% of the image empty paper?
- Is there only one main visual anchor?
- Is the cluster small enough for a quiet cover?
- Is typography delicate rather than commercial?
- Is the accent color visible but not loud?
- Does the image avoid copying a specific creator's signature, watermark, title format, or existing image?
- Does it avoid full-bleed illustration, dense scrapbook, glossy ad, 3D, neon, anime, and stock-photo realism?

If an output fails, regenerate once with stronger constraints.

## Output Format

For one image:

````markdown
**生成图**

![emotion poster](absolute-image-path-or-rendered-image)

**最终 Prompt**

```text
[final prompt used for image generation]
```

**说明**

- Mode: [Single / Photo / Text]
- Recipe: [layout / anchor / typography / accent / texture / mood]
- [one short note about how the user's input was interpreted]
````

For batch output, return a compact index first, then image sections:

````markdown
# Batch Run: [run name]

| ID | Theme | Output | Recipe | Review |
| --- | --- | --- | --- | --- |
| 001 | 橘子汽水 | 001-orange-soda.png | lower-left-diary / fruit-specimen / tiny-caption / warm-orange / paper-fibers / summer | pass |

## 001 - 橘子汽水

![001 - 橘子汽水](absolute-image-path-or-rendered-image)

```text
[final prompt]
```
````

## Example Requests

- "用这个 skill 做一张关于周末的图"
- "主题：橘子汽水，文案：夏天慢慢醒来"
- "把这张照片做成安静手帐海报"
- "批量生成 9 张，主题分别是：周末、看星星、失眠、橘子、风筝、梨、夏天、向内生长、海边"
