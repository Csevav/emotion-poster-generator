---
name: emotion-poster-generator
description: Generate one or many quiet minimal zine emotion posters from themes, photos, short copy, diary notes, fruits, moods, people, still objects, lists, tables, or batch briefs. Use when the user wants sparse vertical paper posters with huge negative space, one small symbolic anchor, micro typography, scanned-paper texture, and one restrained high-recognition accent color.
---

# Emotion Poster Generator

Turn the user's prompt into generated raster images plus traceable prompts.

This skill supports both single-image and batch production. Choose the mode, content category, and visual substyle from the user's prompt rather than asking the user to pick a separate skill.

The target image language is a quiet minimal zine emotion poster: tall aged paper, a very small visual event, precise micro typography, and one memorable accent color. Preserve the essence of sparse emotion-poster work without copying any creator's exact layout, title format, signature, watermark, recurring proprietary marks, or existing image.

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

## Category Routing

After choosing the mode, classify each output into one visual category.

- Fruit: apple, pear, orange, tomato, guava, lemon, watermelon, strawberry, cherry, fruit soda, food-as-fruit.
- Mood: empty space, pressure, healing, waiting, slow down, solitude, vulnerability, calmness, memory, breathing, staring blankly, freedom, light, rain, night.
- People: self, child, woman, old age, gaze, relationship, dialogue, care, freedom, vulnerability, body, gesture, portrait prompt.
- Still Object: kite, clock, ceramic, lantern, shell, coffee, branch, flower, tree, paper, chair, cone, fan, window, book, daily object.

Category rules:

- If a prompt names a concrete fruit, use Fruit even when the copy is emotional.
- If a prompt names a person or portrait, use People, but avoid literal face-forward portrait unless the user explicitly asks for one.
- If a prompt names a physical non-fruit object, use Still Object.
- If the prompt is abstract or mainly emotional, use Mood.
- For batch work, record the category per row so the visual grammar varies intentionally.

## Category Grammars

Use these category-specific visual grammars before selecting the final recipe.

### Fruit

- Treat fruit as a specimen, cutaway, translucent slice, torn paper print, or small color study.
- Put the fruit cluster at center or slightly lower than center; keep it small enough that the paper reads first.
- Use one high-recognition fruit color: tomato red, apple red, pale yellow, guava pink, citrus yellow, warm orange, or soft green.
- Add micro labels, tiny date/weather text, faint ingredient-like notes, or barely readable editorial fragments.
- Avoid cute fruit stickers, grocery ads, juicy commercial food photography, plates, tables, hands, and full still-life scenes.

### Mood

- Convert the mood into an abstract but imageable sign: blue dots, scattered stars, a thin line, a small shadow, a gray block, a misty paper window, a tiny distant landscape, or a sparse diagram.
- The subject may be almost nothing; the emotional charge should come from position, empty space, paper tone, and micro type.
- Electric blue, cobalt blue, pale cyan, gray-black, or one tiny red mark work well.
- Use short poetic text, broken words, small annotations, serial numbers, or low-contrast ghost text.
- Avoid literal emoji, therapy poster language, motivational quote layouts, large calligraphy, or decorative blobs.

### People

- Do not default to a realistic portrait. Translate people into a silhouette, cropped gesture, shadow, tiny back view, paper cutout, photo fragment, eye-line, or object that stands for a person.
- Keep faces small, partial, obscured, or absent unless the user explicitly asks for an identifiable person.
- Use documentary microtext, date/place notes, one quiet line of copy, and a small color accent attached to the person-symbol.
- Good anchors: a small coat silhouette, a hand crop, a pair of eyes as paper texture, a tiny walking figure, a torn ID-photo fragment, a chair, a window, or a shadow.
- Avoid fashion editorial, realistic headshots, beauty portraits, cinematic people scenes, social-media quote cards, and sentimental illustration.

### Still Object

- Treat the object as a scanned specimen or tiny museum label object on paper.
- Use one object only, or one object plus one small paper/photo fragment.
- Favor thin branch diagrams, old fan, clock, ceramic, shell, kite, flower, paper scrap, cup, book, lantern, window, or everyday tool.
- Pair the object with micro annotations, small English fragments, date/weather, a tiny index number, or measurement-like type.
- Avoid product ads, realistic tabletop photography, cozy lifestyle scenes, dense collage, large shadows, and obvious mockups.

## Visual Substyle Routing

After category routing, choose one visual substyle. The substyle controls the image grammar; the content category controls what the subject becomes.

- `blue-signal`: saturated blue dots, blue words, blue brush/cutout marks, or blue fragments carry the emotion.
- `photo-window`: one small photo, two stacked photo panels, or a narrow vertical strip of tiny images floats on paper.
- `fruit-specimen`: fruit is treated as a cutaway, translucent slice, old printed specimen, or small color study.
- `person-obscured`: people appear as a tiny back view, cropped gesture, shadow, ID-photo fragment, or obscured face.
- `text-field`: typography is the main visual event; image may be absent or secondary.
- `object-archive`: a non-fruit object becomes a scanned specimen with labels, measurement text, or diagram marks.
- `editorial-page`: a more magazine-like composition with larger text, long ghost text, binder/page feeling, or layered text blocks.

Substyle selection rules:

- Fruit usually starts with `fruit-specimen`; use `photo-window` only when a fruit is paired with sky, field, season, or memory.
- Mood can use `blue-signal`, `text-field`, `photo-window`, or `editorial-page`.
- People usually use `person-obscured`; use `photo-window` for memory/back-view scenes and `text-field` for identity/self-definition prompts.
- Still Object usually uses `object-archive`; use `blue-signal` for shells, dots, stars, or abstract object fields; use `photo-window` for sea, sky, snow, and landscape fragments.
- For a batch, rotate substyles. Do not let every image become the same tiny photo window or blue-dot field.

## First-Principles Prompt Fields

Every final prompt must answer these rendering questions in order. Use the answers as concrete visual constraints, not as analysis prose.

1. Canvas: tall 3:5 paper poster, full-frame aged paper, no border or mockup.
2. Attention Geometry: 70%-90% empty paper, one cluster or text event around 8%-24% of the canvas, no edge-hugging unless the chosen substyle requires drifting text.
3. Content Category: Fruit, Mood, People, or Still Object.
4. Visual Substyle: one of `blue-signal`, `photo-window`, `fruit-specimen`, `person-obscured`, `text-field`, `object-archive`, or `editorial-page`.
5. Image Anchor: one object, photo crop, silhouette, color block, text field, trace, or specimen.
6. Anchor Treatment: scanned paper, old photo, photocopy, halftone, risograph ink, torn edge, soft edge, misregistration, line diagram, or low-contrast print.
7. Typography System: tiny serif/typewriter/monospaced text, fragmented English/Chinese, date/weather/place, label text, or ghost body copy.
8. Color Logic: one high-recognition color anchor visible at thumbnail size, with the rest subdued.
9. Resolution and Clarity: high-resolution source, crisp anchor edges, readable main short text, and texture applied as print character rather than blur.
10. Emotional Temperature: quiet, distant, private, poetic, archival, sparse, restrained.
11. Hard Avoids: no full scene, ad, large commercial headline, sticker collage, fashion/beauty portrait, 3D, neon, glossy mockup, or generic template polish.

## Color Engine

Use one main high-recognition color per image.

- Default to a visible opaque or saturated color anchor: electric blue, cobalt blue, sky blue, tomato red, apple red, guava pink, citrus yellow, pale yellow, soft green, or warm orange.
- Keep paper, grayscale photos, microtext, and secondary marks subdued.
- The color anchor should occupy about 0.8%-3% of the whole canvas or 15%-40% of the visual cluster.
- Color can be the subject itself, a brush/cutout mark, a printed block, blue dots, broken type, a photo tint, or a small flat silhouette.
- Do not weaken the main color with wording like `muted`, `faded`, `pastel`, `low saturation`, or `near-monochrome` unless the user explicitly asks for muted output.
- Use `charcoal-black` as an accent only when the poster depends on black-and-white archive/photo logic; otherwise choose a chromatic accent.
- For batches, at least half the outputs should have a clearly visible chromatic anchor, not only gray photos and tiny black text.

## Resolution and Clarity

Low-fidelity print style must not mean low-resolution output.

- Prompt for a high-resolution vertical poster source suitable for sharp mobile viewing and later 2x export.
- Keep the paper texture, scan noise, halftone, xerox wear, and ink bleed subtle enough that they do not blur the main anchor.
- Main short text, date labels, specimen labels, and primary micro typography should have crisp letterforms. Secondary ghost text may be semi-legible.
- Fruit pulp lines, photo-window edges, silhouettes, blue dots, color blocks, branch diagrams, and object contours should remain clean and defined.
- Avoid wording such as `blurry`, `out of focus`, `soft overall image`, `low resolution`, `pixelated`, or `heavy degradation` unless the user explicitly asks for that defect.
- If the built-in generator returns a small image, report the actual pixel size. For project-bound use, create or request a higher-resolution version rather than treating a small preview as final.

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

- Tall vertical paper poster, default 3:5. Use 4:5 only when the user or target platform requires it.
- Warm white, off-white, pale gray, gray-beige, or lightly aged matte paper.
- 70%-90% quiet empty paper.
- One small visual cluster, roughly 8%-24% of the canvas.
- Cluster position: center, slightly above center, slightly below center, lower-left, upper-right, or a quiet off-center point.
- No border, realistic frame, app UI, or product mockup.

Paragraph 2: subject and image anchor

- Convert the theme into one imageable anchor based on its category grammar and visual substyle.
- The anchor must be readable at thumbnail size but still physically small on the page.
- Good anchors: fruit cutaway, plant branch, star field, blue-dot constellation, blue brush mask, small photo crop, torn paper block, thin diagram, daily object, tiny silhouette, obscured face, shadow, window, landscape scrap, ghost text block, or abstract emotional symbol.
- If a photo is supplied, treat it as a small paper clipping, contact sheet, washed photo panel, or cropped fragment inside the layout.
- Prefer one clear metaphor over a complete illustrated scene.

Paragraph 3: typography, accent, and print behavior

- Use tiny serif, monospaced, typewriter, or delicate editorial caption text.
- Use one short readable phrase in Chinese or English, plus optional microtext that can be partly unreadable. In `text-field` and `editorial-page`, typography may become the main visual event.
- Optional microtext: date, weather, place, material label, index number, tiny archive note, measurement, broken English words, scattered letters, or a low-contrast body-text field.
- Use one restrained but visible accent color from the Color Engine; it should carry the poster's memory at thumbnail size.
- Add paper fibers, scan noise, faint pencil marks, risograph grain, light ink bleed, xerox softness, washed print, or halftone degradation.
- Keep the main anchor edges and primary short text crisp; paper defects should stay in the surface, not smear the subject.

Paragraph 4: mood and negative constraints

- Flat orthographic scanned-paper mood.
- Quiet, private, poetic, slow, airy, restrained, slightly nostalgic, editorial, low-fidelity print.
- Avoid full-bleed scenes, commercial ads, large headlines, logos, CTA, glossy mockups, hard shadows, cinematic lighting, 3D, neon, anime, cute stickers, dense collage, stock-photo realism, motivational quote posters, and generic AI poster polish.

## Recipe Axes

Pick one value from each axis for every image. For batch work, vary the recipe across rows while preserving the requested series direction.

### Layout

- `center-specimen`: one tiny object or photo fragment centered in large empty paper
- `lower-left-diary`: small cluster low and left, with quiet empty upper space
- `upper-right-note`: tiny paper/photo block upper-right with loose microtext
- `micro-contact-sheet`: 3-6 very small panels arranged as a compact contact sheet
- `paper-fragment-stack`: two or three overlapping scraps
- `type-and-object`: short phrase and one small object form the cluster
- `blue-dot-field`: saturated blue dots placed sparsely across quiet paper
- `blue-brush-mask`: one saturated blue brush or paper strip obscures a face, word, or small image
- `star-orbit`: stars, dots, or scattered letters loosely orbit a small anchor
- `fruit-cutaway-study`: fruit slice or cutaway as a tiny specimen
- `thin-diagram`: fine annotation lines around one object
- `small-window-block`: one small rectangular photo/color block with micro labels
- `vertical-photo-strip`: two or three tiny photo windows stacked vertically
- `dual-photo-panel`: two adjacent or stacked photo panels with a narrow gap
- `quiet-silhouette`: tiny person, shadow, gesture, or partial figure in empty paper
- `ghost-text-page`: faint large text field or body-copy block becomes background texture
- `type-as-object`: larger experimental text acts as the main anchor

### Anchor

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

### Typography

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

### Texture

- `aged-paper-fibers`
- `soft-scan-noise`
- `xerox-softness`
- `risograph-grain`
- `light-ink-bleed`
- `faint-pencil-annotation`
- `washed-photo-print`
- `subtle-halftone`
- `low-contrast-photocopy`

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
- `breathing`
- `vulnerable`
- `slow`
- `blank`

### Accent

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

## Workflow

1. Parse the user's content.
   - Identify mode, category, visual substyle, central subject, mood, exact text if supplied, visual metaphor, and whether reference images are used.
   - For a complex idea, reduce it to one imageable metaphor.
   - If no image text is supplied, invent one short poetic phrase in the user's language.

2. Select a variation recipe.
   - Pick a category-specific recipe from `prompt-recipes.md` when useful.
   - Pick substyle, layout, anchor, typography, texture, mood, and accent.
   - For batches, avoid repeating the same substyle or layout unless the user asks for strict series consistency.
   - If the composition becomes dense, remove objects before reducing empty space.

3. Compile one final image prompt per output.
   - Use the four-paragraph Prompt Compiler.
   - Specify the exact in-image phrase only when useful.
   - Keep main readable text short because image models often distort long text.
   - State anchor location, approximate size, accent color, and paper treatment.
   - Explicitly say the image is flat and scanned, not a scene, mockup, or ad.

4. Generate images.
   - Use built-in image generation by default.
   - For each batch row, generate one image first.
   - Regenerate only when the output fails the Quality Gate or the user asks for variants.
   - Do not stop after prompt-only unless the user explicitly asks for prompt-only.

5. Record the run.
   - For one image, return image, final prompt, category, recipe, and a short interpretation note.
   - For batch work, maintain an index with one section per output.

## Series Rules

For a series, keep these consistent:

- aspect ratio
- paper tone
- general text scale
- overall negative-space discipline
- image treatment family
- one visual category per row, recorded in the output index
- one visual substyle per row, recorded in the output index

Vary these across images:

- layout position
- anchor metaphor
- visual substyle
- accent hue
- typography behavior
- texture mode

For a coherent 9-image batch, use no more than 3 paper tones and no more than 5 accent hues.

## Quality Gate

Before returning, check every generated image:

- Is it a tall vertical paper poster, preferably 3:5?
- Is 70%-90% of the image empty paper?
- Is there only one main visual anchor?
- Is the anchor small but still recognizable at thumbnail size?
- Does the category grammar match the theme?
- Does the visual substyle match the category and avoid repeating recent outputs?
- Is typography micro, delicate, and editorial rather than a large headline?
- Is there one restrained high-recognition accent color?
- Is the color anchor visible at thumbnail size, with enough area to read?
- Are the main anchor, photo-window edge, fruit/object contour, and primary short text crisp enough for mobile viewing?
- Does the image feel scanned, printed, aged, or low-fidelity instead of digitally clean?
- Does it avoid copying a specific creator's signature, watermark, title format, or existing image?
- Does it avoid full-bleed illustration, dense scrapbook, glossy ad, 3D, neon, anime, cute stickers, motivational quote cards, commercial cover design, and stock-photo realism?

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
- Category: [Fruit / Mood / People / Still Object]
- Substyle: [blue-signal / photo-window / fruit-specimen / person-obscured / text-field / object-archive / editorial-page]
- Recipe: [substyle / layout / anchor / typography / accent / texture / mood]
- [one short note about how the user's input was interpreted]
````

For batch output, return a compact index first, then image sections:

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

## Example Requests

- "用这个 skill 做一张关于周末的图"
- "主题：橘子汽水，文案：夏天慢慢醒来"
- "把这张照片做成安静情绪海报"
- "批量生成 9 张，主题分别是：周末、看星星、失眠、橘子、风筝、梨、夏天、向内生长、海边"
