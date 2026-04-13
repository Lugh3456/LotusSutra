# Architecture — Lotus Sutra Mini Site

## Stack

Static HTML + CSS + vanilla JS. No framework, no build tool, no dependencies beyond Google Fonts (loaded via CDN).

## File organisation

```
LotusSutra/
├── index.html          Entry point — 28-chapter grid
├── section1.html       One file per chapter
│   …
├── section28.html
├── css/
│   └── style.css       Single shared stylesheet
└── docs/
    └── *.md            Project documentation
```

## Design decisions

**One file per chapter.** Each `sectionN.html` is fully self-contained: no shared JS files, no includes, no template engine. The `toggleDetail()` and `speak()` functions are inlined in a `<script>` block at the bottom of every page. This is intentionally redundant — it means any page works in isolation, can be printed, can be opened as a standalone file, and has zero dependency on any other file except `css/style.css`.

**CSS shared, JS inlined.** Style is shared across all pages through a single stylesheet. JavaScript is intentionally duplicated per page because it is tiny (< 30 lines) and the isolation benefit outweighs the duplication cost.

**Explanation cards: Chinese visible, English toggled.** The default state assumes a Chinese-literate reader. English explanations are available but hidden, revealed by a toggle button. This keeps the reading experience clean for the primary use case.

**TTS targeting Ting-Ting.** The `speak()` function prefers the Ting-Ting zh-CN voice, which produces the most natural Classical Chinese reading on macOS/iOS. Falls back to any zh-CN voice if Ting-Ting is unavailable. Rate is set to 0.9 (slightly slower than default) for sutra reading.

**No prev link on section 1, no next link on section 28.** Navigation is linear and explicit. No circular navigation.

## Hub-and-spoke portal model

LotusSutra sits as a spoke off the DharmaGate hub:

```
DharmaGate (hub)
├── DiamondSutra (spoke)
├── LotusSutra (spoke)     ← this project
└── [future spokes]
```

Each spoke is an independent GitHub repo deployed to its own GitHub Pages URL. They share the same design system (CSS tokens, fonts, portal bar) but have no code dependency on each other.

## CSS design tokens (from DiamondSutra, shared verbatim)

```css
--red: #b83232        /* accent for headers */
--saffron: #c8820a    /* chapter numbers, highlights */
--ink: #1c0f0f        /* primary text */
--bg: #f7f0e6         /* page background */
--card-bg: #fdf8f2    /* explanation card background */
```
