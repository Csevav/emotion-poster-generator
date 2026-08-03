# Emotion Poster Generator

[中文文档](README.zh-CN.md)

An AI skill that turns a theme, photo, short line of copy, or a batch of
prompts into quiet, minimal zine-style emotion posters — clean scanned-paper
surfaces, large negative space, one symbolic anchor, directional experimental
typography, and a single restrained accent color.

## What it does

Given a prompt like a mood, an object, a diary line, or a reference photo, the
skill:

1. Picks a **mode** — single image, text-driven, photo-driven, batch, or series.
2. Classifies the subject into a **category** — Fruit, Mood, People, or Still Object.
3. Chooses a **visual substyle** (`blue-signal`, `photo-window`, `fruit-specimen`,
   `person-obscured`, `text-field`, `object-archive`, `editorial-page`) that
   controls the image grammar.
4. Builds a semantically coherent English copy package by default, organizing keywords, single lines, and body copy as point, line, and plane with three tonal levels.
5. Routes each theme through one of nine paper substrates, selecting color temperature, surface pattern, and texture intensity instead of repeating one background.
6. Compiles a four-paragraph image prompt (canvas, subject/anchor, typography &
   accent, mood & negative constraints) following a strict set of composition
   and color rules.
7. Generates the image, runs it through a quality gate, and returns the image
   plus the final prompt and a short interpretation note.

Batch requests (a list, table, or CSV of themes) produce a full run with an
index table and one section per generated poster.

## Requirements

The image-generation step depends on the host AI agent's built-in text-to-image
capability. This has been verified to work end-to-end in image-capable **Codex**
environments. **Claude Code CLI does not include built-in image generation**, so
in a plain Claude Code CLI environment this skill can only run the
Mode/Category/Prompt Compiler steps and produce the final prompt text — it
cannot generate the actual image file.

## Examples

| Lemon | Rainy Day |
| --- | --- |
| ![Lemon](examples/lemon.png) | ![Rainy Day](examples/rainy-day.png) |

## Repo contents

| File | Purpose |
| --- | --- |
| [`SKILL.md`](SKILL.md) | The skill definition — mode/category/substyle routing, prompt compiler, recipe axes, quality gate, and output format. |
| [`prompt-recipes.md`](prompt-recipes.md) | Reference recipes per content category. |
| [`references/style-study.md`](references/style-study.md) | A comprehensive study of 163 public note covers, including the typography engine, layout archetypes, and failure modes. |
| [`references/cases/`](references/cases/) | Twelve low-volume representative cases for internal visual validation only, not image-to-image references. |
| [`batch-input.example.csv`](batch-input.example.csv) | Example of the normalized batch input format (`id, theme, copy, mood, accent, reference_image, notes`). |
| [`batch-output.example.md`](batch-output.example.md) | Example of a rendered batch output. |

## Usage

This is an AI skill — drop `SKILL.md` (and the accompanying reference files)
into a skills directory for an AI agent/assistant platform that supports
skills (e.g. Claude Code, or any system that loads `SKILL.md`-based skills).
The assistant will invoke it automatically when a prompt asks for sparse,
minimal emotion-poster style imagery.

Example prompts:

- "Use this skill to make an image about the weekend"
- "Theme: orange soda, copy: summer slowly waking up"
- "Turn this photo into a quiet emotion poster"
- "Batch-generate 9 posters with the themes: weekend, stargazing, insomnia, orange, kite, pear, summer, growing inward, seaside"

## License

[MIT](LICENSE)
