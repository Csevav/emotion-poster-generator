# Prompt Recipes

Use these recipes to make output fast, varied, and closer to the target minimal zine emotion-poster language. Classify each theme first, then choose a recipe inside that category.

## Fruit

### Translucent Fruit Slice

- Layout: `fruit-cutaway-study`
- Anchor: `translucent-fruit-slice`
- Typography: `date-weather-label`
- Texture: `aged-paper-fibers`
- Accent: `citrus-yellow`, `warm-orange`, `guava-pink`, or `soft-green`
- Best for: 橘子、柠檬、梨、芭乐、西瓜、苹果切片
- Notes: Make the fruit feel thin, printed, and slightly transparent. Keep the slice cluster small.

### Single Fruit Specimen

- Layout: `center-specimen`
- Anchor: `fruit-specimen`
- Typography: `specimen-label`
- Texture: `soft-scan-noise`
- Accent: `tomato-red`, `apple-red`, `pale-yellow`, or `warm-orange`
- Best for: 番茄、苹果、梨、樱桃、橘子
- Notes: Use one fruit or one cut fruit. Add tiny labels and one short phrase, not a food scene.

### Fruit Plus Paper Block

- Layout: `small-window-block`
- Anchor: `washed-paper-block`
- Typography: `archive-microtext`
- Texture: `washed-photo-print`
- Accent: `tomato-red`, `sky-blue`, or `soft-green`
- Best for: 夏天的配置、番茄、苹果、果味汽水
- Notes: Pair one fruit with a tiny sky/field/paper rectangle; the block must stay small.

## Mood

### Blue Dot Field

- Layout: `blue-dot-field`
- Anchor: `blue-dot-constellation`
- Typography: `almost-textless`
- Texture: `soft-scan-noise`
- Accent: `electric-blue` or `cobalt-blue`
- Best for: 留白、呼吸、慢一点、无所谓、发呆、空、孤独
- Notes: The blue dots are the emotional event. Use very few words.

### Sparse Star Mood

- Layout: `star-orbit`
- Anchor: `scattered-star-sign`
- Typography: `broken-english-fragments`
- Texture: `low-contrast-photocopy`
- Accent: `electric-blue`, `cobalt-blue`, or `charcoal-black`
- Best for: 看星星、夜晚、失眠、梦、微光、极夜
- Notes: Keep stars small and irregular. Avoid cute star stickers.

### Ghost Text Window

- Layout: `type-and-object`
- Anchor: `abstract-texture-window`
- Typography: `gray-ghost-text`
- Texture: `xerox-softness`
- Accent: `pale-cyan`, `charcoal-black`, or one tiny `tomato-red` mark
- Best for: 压力、允许脆弱、疗愈、心态、从容、等待
- Notes: Use faint text as texture. The poster can be nearly empty.

## People

### Quiet Silhouette

- Layout: `quiet-silhouette`
- Anchor: `quiet-person-silhouette`
- Typography: `archive-microtext`
- Texture: `aged-paper-fibers`
- Accent: `cobalt-blue`, `tomato-red`, or `charcoal-black`
- Best for: 自我、童年、女人、自由、别怕变老、愿她自由
- Notes: Use a tiny back view, shadow, or silhouette. Do not make a realistic portrait.

### Gesture Fragment

- Layout: `upper-right-note`
- Anchor: `partial-gesture-crop`
- Typography: `edge-phrase`
- Texture: `washed-photo-print`
- Accent: `sky-blue`, `guava-pink`, or `soft-green`
- Best for: 目光、关系、对话、取悦、倾听、脆弱
- Notes: A cropped hand, eye-line, or shoulder can stand for the person.

### Person As Trace

- Layout: `paper-fragment-stack`
- Anchor: `shadow-or-trace`
- Typography: `date-weather-label`
- Texture: `subtle-halftone`
- Accent: `charcoal-black`, `pale-cyan`, or one tiny `tomato-red` mark
- Best for: 自我救赎、放不下才沉重、候鸟、迷雾、爱的海洋
- Notes: Use absence: shadow, footprint, empty chair, window, or torn photo.

## Still Object

### Thin Branch Diagram

- Layout: `thin-diagram`
- Anchor: `thin-branch-diagram`
- Typography: `broken-english-fragments`
- Texture: `faint-pencil-annotation`
- Accent: `sky-blue`, `soft-green`, or `charcoal-black`
- Best for: 树、枯枝、小花、杜鹃、春、天晴
- Notes: The branch or flower should be graphic, thin, and scanned.

### Tiny Object Label

- Layout: `center-specimen`
- Anchor: `daily-object-specimen`
- Typography: `specimen-label`
- Texture: `light-ink-bleed`
- Accent: `electric-blue`, `tomato-red`, `pale-yellow`, or `charcoal-black`
- Best for: 风筝、时钟、瓷器、灯笼、海螺、咖啡、锥桶
- Notes: One object only. Treat it like a small museum label on paper.

### Small Photo Window

- Layout: `small-window-block`
- Anchor: `small-landscape-window`
- Typography: `archive-microtext`
- Texture: `washed-photo-print`
- Accent: `sky-blue`, `cobalt-blue`, or `soft-green`
- Best for: 海边、天空、云、日出、麦田、杭州·雪、看海
- Notes: Use a tiny rectangular landscape fragment, not a full-bleed scene.

## Batch Defaults

For a mixed 9-image batch:

1. Classify every row as Fruit, Mood, People, or Still Object.
2. Use no more than 3 paper tones across the batch.
3. Use no more than 5 accent hues across the batch.
4. Rotate layouts so adjacent images do not share the same composition.
5. Keep type scale, paper texture, and negative-space discipline consistent.
6. Prefer `electric-blue`, `tomato-red`, `sky-blue`, `pale-yellow`, and `soft-green` as the recurring accent system.

## Prompt Skeleton

```text
Tall vertical 3:5 minimal zine emotion poster on [paper tone] aged matte paper, with [empty-space]% quiet empty space. A small [layout position] cluster occupies about [cluster-size]% of the canvas, leaving the paper surface dominant.

The theme "[theme]" is translated into [category-specific anchor]. Use [anchor treatment] so it feels like a tiny scanned specimen, paper clipping, low-fidelity print, or abstract sign rather than a full scene.

Use tiny [typography style] text reading "[copy]", placed [text position], with optional microtext such as [date/weather/index/broken words]. Add one [accent color] accent as [accent form], visible at thumbnail size but restrained on the page, with [texture details].

Flat orthographic scanned-paper mood, quiet, private, poetic, airy, low-fidelity editorial print. Avoid full-bleed scene, commercial headline, logo, CTA, glossy mockup, hard shadow, cinematic lighting, 3D, neon, anime, cute stickers, dense collage, motivational quote card, and stock-photo realism.
```
