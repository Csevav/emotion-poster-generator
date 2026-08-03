# Prompt Recipes

Use these recipes to make output fast, varied, and closer to the target minimal zine emotion-poster language. Classify each theme first, then choose a visual substyle. The substyle is the main guardrail against flattening the whole account into one look.

Across all recipes, treat empty paper as the main emotional material. Route the density instead of forcing one ratio: use 78%-90% empty space for standard sparse layouts, 86%-94% for extreme-negative-space layouts, and 65%-82% for text-field, blue-signal, or editorial layouts. Select an explicit substrate preset instead of always using the same gray-white paper. Use one ambiguous image trace and very low total ink coverage. Do not reduce the style to a centered icon with a tidy caption. Prefer image fragments, exposure loss, ghost text, interrupted phrases, and directional type. Avoid explanatory diagrams unless the theme explicitly calls for analytical or archival language.

## Paper Substrate Matrix

| Preset | Color temperature | Surface | Default intensity | Best fit |
| --- | --- | --- | --- | --- |
| `sage-weave` | muted cool green-gray | fine woven crosshatch | tactile | plants, tools, quiet objects |
| `warm-fiber` | warm light beige | soft visible fibers | tactile | fruit, diary, domestic memory |
| `clean-cream` | warm ivory | nearly smooth matte | clean | bright fruit, delicate color studies |
| `ivory-mottle` | warm gray-white | faint cloudy absorption | tactile | people, memory, soft archival work |
| `honey-pulp` | honey beige | fine pulp and tonal variation | tactile | summer, citrus, tomato, warm objects |
| `warm-gray-matte` | light warm gray | even matte paper | clean | portraits, grayscale photos, body copy |
| `cool-linen` | cool white-blue | fine horizontal linen | tactile | air, sea, sour fruit, clarity |
| `stone-speckle` | pale stone gray | sparse mineral speckles | tactile | archive, waiting, quiet mood |
| `fog-taupe` | foggy gray-brown | low-contrast smooth grain | clean | cloudy mood, subdued people |

Use `clean` at 1%-3% visibility, `tactile` at 4%-8%, and `material-led` at 9%-15%. Never combine `material-led` paper with heavy image grain, dense body copy, and multiple distressed effects. For a nine-poster series, use at most three presets and two intensities.

## English Copy and Point-Line-Plane System

English is the default in-image language unless the user supplies exact copy in another language. For Fruit and Still Object, compile a complete text composition rather than a single caption:

| Geometry | Copy | Length | Tone value | Function |
| --- | --- | --- | --- | --- |
| Point | 2-4 isolated keywords | 1-3 words each | 35%-70% | anchors, pauses, color echoes |
| Line | primary line + supporting line | 4-9 words + 6-14 words | 85%-100% + 35%-60% | semantic hook and viewing direction |
| Plane | coherent body copy | 22-45 words, 3-7 lines | 6%-18% | rectangular gray mass and atmosphere |

All four copy layers must come from one semantic core. Never use lorem ipsum, random letters, generic archive metadata, or an unrelated inspirational quote. Keep the primary line exact and readable. The body block may be only partly legible in the rendered image, but it must retain plausible English word shapes, consistent line length, and a deliberate rectangular silhouette.

Composition rules:

- Give point, line, and plane different positions, widths, and tone values.
- Let one text form touch the image, one cross or sit behind it, and one remain detached in the surrounding paper.
- Create one dense zone, one loose interval, and one untouched quiet zone.
- Use no more than two font families and three levels of size/weight.
- Small text does not mean thin content: richness comes from layered density and gray value, not oversized type.

## Typography Behavior Matrix

Choose one primary behavior before compiling the prompt. The frequency column is a routing priority, not a measured statistic. Add a second behavior only when it clearly plays a different role. Never select a rare behavior merely to make the result feel more experimental.

| Behavior | Frequency | Primary role | Best fit | Movement | Key constraint |
| --- | --- | --- | --- | --- | --- |
| `micro-anchor-caption` | default | `primary-hook` | Fruit, Still Object, quiet Photo Window | local/edge | Small, fine, offset from the image; never a centered caption card. |
| `horizontal-thread` | default | `directional-thread` | Heat, sea, summer, distance, relationship | horizontal | Use a light thread, not a bold band; cross or bypass one image edge. |
| `ghost-body-layer` | default | `atmospheric-field` | Memory, choice, long emotion, archive | broad field | Keep it at 5%-20% visual clarity, below the hook. |
| `letter-field` | occasional | `directional-thread` | Blue Signal, breath, night, blankness | loose horizontal or gentle diagonal | Uneven density; fragments need a semantic source and stay small. |
| `image-interruption` | occasional | `primary-hook` + image | People, identity, conflict, vulnerability | horizontal or diagonal | The obscuration must add meaning and remain visually quiet. |
| `edge-orbit` | occasional | `directional-thread` | Fruit slices, sun, gaze, flower, round objects | partial orbit | Use an open, fine arc, not a decorative full ring. |
| `vertical-spine` | rare | `primary-hook` | Explicit text-led manifesto | vertical | User must ask for text-led design; keep weight fine and secondary matter tiny. |
| `scale-collision` | rare | `primary-hook` | Explicit experimental large-type request | vertical or horizontal | Never auto-select; no bold black display type or oversized English. |

Role hierarchy is normally `primary-hook` at 100% clarity, `directional-thread` at 45%-70%, and `atmospheric-field` at 5%-20%. Use natural Chinese word groups rather than equal character spacing. Derive fragments from the theme, the exact copy, pinyin, or a related English root.

## Visual Substyles

### Blue Signal

- Categories: Mood, People, Still Object
- Layout: `blue-dot-field`, `blue-brush-mask`, `star-orbit`, `horizontal-letter-drift`, or `type-and-object`
- Anchor: `blue-dot-constellation`, `blue-brush-obscuration`, `scattered-star-sign`, or blue broken type
- Typography: `almost-textless`, `broken-english-fragments`, `scattered-letters`, or `letter-drift`
- Texture: `soft-scan-noise`, `low-contrast-photocopy`, or `clean-paper-haze`
- Accent: `electric-blue` or `cobalt-blue`
- Best for: 蓝点、一抹蓝色、留白、定义、呼吸、看星星、极夜、情绪感
- Notes: Blue is an emotional trace, not a data-visualization system. It can be dots, drifting letters, a brush, mask, or cutout, but it must not become a complete chart, scale, or interface.

### Photo Window

- Categories: Mood, People, Still Object
- Layout: `small-window-block`, `vertical-photo-strip`, `dual-photo-panel`, `horizontal-letter-drift`, or `off-center-image-thread`
- Anchor: `tiny-faded-photo`, `overexposed-photo-fragment`, `faded-light-spot`, `small-landscape-window`, or `paper-clipping`
- Typography: `archive-microtext`, `edge-phrase`, `letter-drift`, or `interrupted-phrase`
- Texture: `washed-photo-print`, `exposure-leak`, `xerox-softness`, or `clean-paper-haze`
- Accent: `sky-blue`, `cobalt-blue`, `violet-blue`, `soft-green`, or `charcoal-black`
- Best for: 海、云、日出、雪、麦田、背影、候鸟、爱的海洋、海的对话
- Notes: The photo should feel found, cropped, overexposed, or partially lost. Let a few letters drift across or around it. Never turn it into a full travel photo or a tidy photo card with a caption directly below.

### Fruit Specimen

- Categories: Fruit
- Layout: `fruit-cutaway-study`, `center-specimen`, or `small-window-block`
- Anchor: `fruit-specimen`, `translucent-fruit-slice`, or `washed-paper-block`
- Typography: `specimen-label`, `tiny-caption`, or `archive-microtext`
- Texture: `aged-paper-fibers`, `soft-scan-noise`, or `washed-photo-print`
- Accent: `tomato-red`, `apple-red`, `guava-pink`, `citrus-yellow`, `pale-yellow`, `warm-orange`, or `soft-green`
- Best for: 苹果、番茄、梨、芭乐、柠檬、橘子、西瓜、果味汽水
- Notes: The fruit should feel printed, cut, translucent, indexed, or studied, not photographed as food.

### Person Obscured

- Categories: People
- Layout: `blue-brush-mask`, `quiet-silhouette`, `small-window-block`, or `paper-fragment-stack`
- Anchor: `obscured-face-fragment`, `quiet-person-silhouette`, `partial-gesture-crop`, or `shadow-or-trace`
- Typography: `archive-microtext`, `edge-phrase`, or `gray-ghost-text`
- Texture: `low-contrast-photocopy`, `washed-photo-print`, or `aged-paper-fibers`
- Accent: `electric-blue`, `cobalt-blue`, `tomato-red`, or `charcoal-black`
- Best for: 定义、自我、目光、女人、童年、愿她自由、允许脆弱、别怕变老
- Notes: Avoid a conventional portrait. Obscure, crop, shrink, or translate the person into a trace.

### Text Field

- Categories: Mood, People
- Layout: `type-as-object`, `ghost-text-page`, `type-and-object`, or `blue-dot-field`
- Anchor: `ghost-body-text`, `abstract-texture-window`, or broken type
- Typography: `large-quiet-type`, `body-copy-texture`, `broken-english-fragments`, or `gray-ghost-text`
- Texture: `xerox-softness`, `risograph-grain`, or `light-ink-bleed`
- Accent: `electric-blue`, `charcoal-black`, `pale-cyan`, or one tiny `tomato-red` mark
- Best for: 灰、心态、疗愈、从容、慢一点、无所谓、交换一张排版可以吗
- Notes: Text becomes the image. Use large type only as experimental editorial matter, not as a commercial headline.

### Object Archive

- Categories: Still Object
- Layout: `center-specimen`, `thin-diagram`, `paper-fragment-stack`, or `upper-right-note`
- Anchor: `daily-object-specimen`, `thin-branch-diagram`, `paper-clipping`, or `abstract-texture-window`
- Typography: `specimen-label`, `edge-phrase`, or `broken-english-fragments`
- Texture: `faint-pencil-annotation`, `light-ink-bleed`, `subtle-halftone`, or `aged-paper-fibers`
- Accent: `electric-blue`, `sky-blue`, `tomato-red`, `pale-yellow`, `soft-green`, or `charcoal-black`
- Best for: 风筝、时钟、瓷器、灯笼、海螺、咖啡、锥桶、树枝、花
- Notes: One object becomes an archive specimen. Avoid tabletop, lifestyle, product, or cozy scene logic.

### Editorial Page

- Categories: Mood, People, Still Object
- Layout: `ghost-text-page`, `type-as-object`, `dual-photo-panel`, or `paper-fragment-stack`
- Anchor: `ghost-body-text`, `small-landscape-window`, `tiny-faded-photo`, or `shadow-or-trace`
- Typography: `body-copy-texture`, `large-quiet-type`, `archive-microtext`, or `gray-ghost-text`
- Texture: `low-contrast-photocopy`, `xerox-softness`, or `aged-paper-fibers`
- Accent: `charcoal-black`, `electric-blue`, or `pale-cyan`
- Best for: hi 我是叶麦、灰、疗愈、长文情绪、装订感、杂志页感
- Notes: This is the controlled exception for larger text or longer body copy. Keep it editorial and quiet, not promotional.

## Fruit

### Translucent Fruit Slice

- Substyle: `fruit-specimen`
- Layout: `fruit-cutaway-study`
- Anchor: `translucent-fruit-slice`
- Typography: `specimen-label` or `tiny-caption`
- Typography behavior: `edge-orbit` or `micro-anchor-caption`
- Copy composition: English point + line + plane; one exact primary line, one supporting line, one 3-7 line gray body block, and 2-4 point words
- Texture: `aged-paper-fibers`
- Accent: `citrus-yellow`, `warm-orange`, `guava-pink`, or `soft-green`
- Best for: 橘子、柠檬、梨、芭乐、西瓜、苹果切片
- Notes: Make the fruit feel thin, printed, and slightly transparent. Keep the slice cluster small.
- Lemon sample copy:
  - Primary line: `A LITTLE SOUR, STILL FULL OF LIGHT.`
  - Supporting line: `Some brightness arrives with a sharper edge.`
  - Body block: `Lemon keeps the memory of sunlight in every thin section. Its brightness is not soft or sweet; it wakes the tongue, clears the air, and leaves a clean yellow trace behind.`
  - Point words: `LEMON`, `LIGHT`, `TART`, `TRACE`

### Single Fruit Specimen

- Substyle: `fruit-specimen`
- Layout: `center-specimen`
- Anchor: `fruit-specimen`
- Typography: `specimen-label`
- Typography behavior: `micro-anchor-caption`
- Copy composition: English point + line + plane
- Texture: `soft-scan-noise`
- Accent: `tomato-red`, `apple-red`, `pale-yellow`, or `warm-orange`
- Best for: 番茄、苹果、梨、樱桃、橘子
- Notes: Use one fruit or one cut fruit. Add tiny labels and one short phrase, not a food scene.

### Fruit Plus Paper Block

- Substyle: `fruit-specimen` or `photo-window`
- Layout: `small-window-block`
- Anchor: `washed-paper-block`
- Typography: `archive-microtext`
- Typography behavior: `horizontal-thread` or `micro-anchor-caption`
- Copy composition: English point + line + plane
- Texture: `washed-photo-print`
- Accent: `tomato-red`, `sky-blue`, or `soft-green`
- Best for: 夏天的配置、番茄、苹果、果味汽水
- Notes: Pair one fruit with a tiny sky/field/paper rectangle; the block must stay small.

## Mood

### Blue Dot Field

- Substyle: `blue-signal`
- Layout: `blue-dot-field`
- Anchor: `blue-dot-constellation`
- Typography: `almost-textless`
- Typography behavior: `letter-field`
- Texture: `soft-scan-noise`
- Accent: `electric-blue` or `cobalt-blue`
- Best for: 留白、呼吸、慢一点、无所谓、发呆、空、孤独
- Notes: The blue dots are the emotional event. Use very few words.

### Sparse Star Mood

- Substyle: `blue-signal`
- Layout: `star-orbit`
- Anchor: `scattered-star-sign`
- Typography: `broken-english-fragments`
- Typography behavior: `letter-field` or `edge-orbit`
- Texture: `low-contrast-photocopy`
- Accent: `electric-blue`, `cobalt-blue`, or `charcoal-black`
- Best for: 看星星、夜晚、失眠、梦、微光、极夜
- Notes: Keep stars small and irregular. Avoid cute star stickers.

### Ghost Text Window

- Substyle: `text-field`
- Layout: `type-and-object`
- Anchor: `abstract-texture-window`
- Typography: `gray-ghost-text`
- Typography behavior: `ghost-body-layer`
- Texture: `xerox-softness`
- Accent: `pale-cyan`, `charcoal-black`, or one tiny `tomato-red` mark
- Best for: 压力、允许脆弱、疗愈、心态、从容、等待
- Notes: Use faint text as atmosphere rather than readable content. Interrupt it with one small image trace or color mark. The poster can be nearly empty.

### Bleached Heat Trace

- Substyle: `photo-window` or `blue-signal`
- Layout: `horizontal-letter-drift` or `off-center-image-thread`
- Anchor: `overexposed-photo-fragment` or `faded-light-spot`
- Typography: `letter-drift` or `interrupted-phrase`
- Typography behavior: `horizontal-thread`
- Texture: `exposure-leak` and `clean-paper-haze`
- Accent: one tiny `warm-orange` light spot plus sparse `violet-blue` or `cobalt-blue` letters
- Best for: 炎热、烈日、盛夏、午后、晒白的天空、空气发烫
- Notes: Do not draw a complete sun icon, thermometer, chart, or temperature scale. Use a nearly lost sky fragment, one faded orange light leak, and a broken horizontal trail of letters. Split the Chinese hook into 1-3 natural word groups; let the thread cross, touch, or disappear behind the image instead of centering an equal-spaced phrase beneath it. Let the viewer feel heat before understanding it.

## People

### Blue Brush Obscured Portrait

- Substyle: `person-obscured`
- Layout: `blue-brush-mask`
- Anchor: `obscured-face-fragment`
- Typography: `archive-microtext`
- Typography behavior: `image-interruption`
- Texture: `low-contrast-photocopy`
- Accent: `electric-blue` or `cobalt-blue`
- Best for: 定义、自我、目光、取悦、允许脆弱
- Notes: Use a small grayscale bust, face crop, or ID-photo fragment partly covered by one saturated blue brush or paper strip.

### Quiet Silhouette

- Substyle: `person-obscured`
- Layout: `quiet-silhouette`
- Anchor: `quiet-person-silhouette`
- Typography: `archive-microtext`
- Typography behavior: `micro-anchor-caption`; use `vertical-spine` only when the user explicitly asks for text-led design
- Texture: `aged-paper-fibers`
- Accent: `cobalt-blue`, `tomato-red`, or `charcoal-black`
- Best for: 自我、童年、女人、自由、别怕变老、愿她自由
- Notes: Use a tiny back view, shadow, or silhouette. Do not make a realistic portrait.

### Gesture Fragment

- Substyle: `person-obscured`
- Layout: `upper-right-note`
- Anchor: `partial-gesture-crop`
- Typography: `edge-phrase`
- Typography behavior: `image-interruption` or `horizontal-thread`
- Texture: `washed-photo-print`
- Accent: `sky-blue`, `guava-pink`, or `soft-green`
- Best for: 目光、关系、对话、取悦、倾听、脆弱
- Notes: A cropped hand, eye-line, or shoulder can stand for the person.

### Person As Trace

- Substyle: `person-obscured` or `photo-window`
- Layout: `paper-fragment-stack`
- Anchor: `shadow-or-trace`
- Typography: `edge-phrase` or `gray-ghost-text`
- Typography behavior: `ghost-body-layer` or `micro-anchor-caption`
- Texture: `subtle-halftone`
- Accent: `charcoal-black`, `pale-cyan`, or one tiny `tomato-red` mark
- Best for: 自我救赎、放不下才沉重、候鸟、迷雾、爱的海洋
- Notes: Use absence: shadow, footprint, empty chair, window, or torn photo.

## Still Object

### Sunlit Coffee Trace

- Substyle: `photo-window` or `object-archive`
- Layout: `small-window-block` or `off-center-image-thread`
- Anchor: a small translucent coffee surface or partial cup rim plus one tiny overexposed window-light fragment
- Typography: `tiny-caption` or `edge-phrase`
- Typography behavior: `micro-anchor-caption` with an optional very light `horizontal-thread`
- Copy composition: English point + line + plane; the body block stays small and pale, never a fake data label
- Texture: `washed-photo-print` and `clean-paper-haze`
- Accent: coffee brown plus one pale warm-orange exposure area; optional thin pale-cyan outline text
- Best for: 咖啡、周一、午后、烈日、困倦、晒醒
- Notes: Keep the entire visual cluster around 10%-16% of the page and close to the central area. Use small fine type. Never use a giant coffee stain, bold COFFEE lettering, corner-to-corner diagonal text, grunge tearing, or a complete product-style cup.

### Thin Branch Diagram

- Substyle: `object-archive`
- Layout: `thin-diagram`
- Anchor: `thin-branch-diagram`
- Typography: `broken-english-fragments`
- Typography behavior: `edge-orbit`
- Texture: `faint-pencil-annotation`
- Accent: `sky-blue`, `soft-green`, or `charcoal-black`
- Best for: 树、枯枝、小花、杜鹃、春、天晴
- Notes: The branch or flower should be graphic, thin, and scanned.

### Tiny Object Label

- Substyle: `object-archive`
- Layout: `center-specimen`
- Anchor: `daily-object-specimen`
- Typography: `specimen-label`
- Typography behavior: `micro-anchor-caption`
- Texture: `light-ink-bleed`
- Accent: `electric-blue`, `tomato-red`, `pale-yellow`, or `charcoal-black`
- Best for: 风筝、时钟、瓷器、灯笼、海螺、咖啡、锥桶
- Notes: One object only. Treat it like a small museum label on paper.

### Small Photo Window

- Substyle: `photo-window`
- Layout: `small-window-block`
- Anchor: `small-landscape-window`
- Typography: `archive-microtext`
- Typography behavior: `horizontal-thread`
- Texture: `washed-photo-print`
- Accent: `sky-blue`, `cobalt-blue`, or `soft-green`
- Best for: 海边、天空、云、日出、麦田、杭州·雪、看海
- Notes: Use a tiny rectangular landscape fragment, not a full-bleed scene.

## Batch Defaults

For a mixed 9-image batch:

1. Classify every row as Fruit, Mood, People, or Still Object.
2. Choose a visual substyle for every row and record it.
3. Use at least 4 substyles in a 9-image mixed batch unless the user asks for a narrow series.
4. Use no more than 3 substrate presets and 2 substrate intensities across the batch.
5. Use no more than 5 accent hues across the batch.
6. Rotate layouts so adjacent images do not share the same composition.
7. Keep type scale and negative-space discipline consistent; vary paper presets within one coherent temperature family.
8. Prefer `electric-blue`, `tomato-red`, `sky-blue`, `pale-yellow`, and `soft-green` as the recurring accent system.

## Prompt Skeleton

```text
Tall vertical 3:5 high-resolution minimal zine emotion poster on the [substrate preset] paper substrate: [color temperature], [surface pattern], at [clean / tactile / material-led] intensity. Use the [visual substyle] substyle with [density routed by layout]% quiet empty space. A small off-center cluster, image trace, or text event occupies about [8-26]% of the canvas, leaving the paper material dominant.

The theme "[theme]" is classified as [category] and compressed into one partially ambiguous metaphor: [category-specific anchor]. Use [anchor treatment] so it feels like a found image fragment, exposure loss, scanned trace, paper clipping, obscured remnant, or abstract sign rather than a complete icon, scene, or explanatory diagram.

Default to English copy unless the user supplied exact text in another language. Construct typography as point, line, and plane: isolated point words "[2-4 keywords]" at [positions] and 35%-70% tone; an exact readable primary line "[4-9 words]" at 85%-100% tone; a supporting line "[6-14 words]" at 35%-60% tone; and a coherent 22-45 word body block set in 3-7 stable lines at 6%-18% tone, forming a deliberate gray rectangle. Use [typography behavior] on one [local / horizontal / vertical / diagonal / orbital] movement axis. Let one text form touch the image, one cross or sit behind it, and one remain detached. All copy derives from [single semantic core]; no random fragments. Add one [accent color] accent as [accent form], visible at thumbnail size but restrained on the page, with [barely visible texture details]. Keep the primary line and intentional image edges crisp.

Flat orthographic scanned-paper mood, quiet, private, poetic, airy, slightly unresolved, low-fidelity editorial print with high-resolution source clarity. Avoid full-bleed scene, complete icon, explanatory chart, thermometer, interface-like scale, tidy centered caption, commercial headline, logo, CTA, glossy mockup, hard shadow, cinematic lighting, 3D, neon, anime, cute stickers, dense collage, motivational quote card, stock-photo realism, obvious yellowed vintage paper, blurry output, pixelation, and heavy degradation.
```
