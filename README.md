# Emotion Poster Generator

[中文文档](README.zh-CN.md)

An AI skill that turns a theme, photo, short line of copy, or a batch of
prompts into quiet, minimal zine-style emotion posters — tall aged-paper images
with huge negative space, one small symbolic anchor, micro typography, and a
single restrained accent color.

## What it does

Given a prompt like a mood, an object, a diary line, or a reference photo, the
skill:

1. Picks a **mode** — single image, text-driven, photo-driven, batch, or series.
2. Classifies the subject into a **category** — Fruit, Mood, People, or Still Object.
3. Chooses a **visual substyle** (`blue-signal`, `photo-window`, `fruit-specimen`,
   `person-obscured`, `text-field`, `object-archive`, `editorial-page`) that
   controls the image grammar.
4. Compiles a four-paragraph image prompt (canvas, subject/anchor, typography &
   accent, mood & negative constraints) following a strict set of composition
   and color rules.
5. Generates the image, runs it through a quality gate, and returns the image
   plus the final prompt and a short interpretation note.

Batch requests (a list, table, or CSV of themes) produce a full run with an
index table and one section per generated poster.

## Repo contents

| File | Purpose |
| --- | --- |
| [`SKILL.md`](SKILL.md) | The skill definition — mode/category/substyle routing, prompt compiler, recipe axes, quality gate, and output format. |
| [`prompt-recipes.md`](prompt-recipes.md) | Reference recipes per content category. |
| [`batch-input.example.csv`](batch-input.example.csv) | Example of the normalized batch input format (`id, theme, copy, mood, accent, reference_image, notes`). |
| [`batch-output.example.md`](batch-output.example.md) | Example of a rendered batch output. |

## Usage

This is an AI skill — drop `SKILL.md` (and the accompanying reference files)
into a skills directory for an AI agent/assistant platform that supports
skills (e.g. Claude Code, or any system that loads `SKILL.md`-based skills).
The assistant will invoke it automatically when a prompt asks for sparse,
minimal emotion-poster style imagery.

Example prompts:

- "用这个 skill 做一张关于周末的图"
- "主题：橘子汽水，文案：夏天慢慢醒来"
- "把这张照片做成安静情绪海报"
- "批量生成 9 张，主题分别是：周末、看星星、失眠、橘子、风筝、梨、夏天、向内生长、海边"

## License

[MIT](LICENSE)
