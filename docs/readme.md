# Lotus Sutra Mini Site · 妙法莲华经

A 28-chapter interactive reading site for the Lotus Sutra (妙法莲华经), built as a standalone static HTML site under the DharmaGate portal.

## What it is

Each chapter gets its own page (`section1.html` through `section28.html`) with:
- Full sutra text excerpt in Chinese (id="chineseText")
- Text-to-speech button (🔊 聆听经文) using Web Speech API, targeting zh-CN Ting-Ting voice
- 4 explanation cards per chapter, each with a visible Chinese explanation and a toggled English section
- A bilingual summary section at the bottom

## Structure

```
LotusSutra/
├── index.html          28-chapter grid (2-col mobile, auto-fill desktop)
├── section1.html       序品
├── section2.html       方便品
│   …
├── section28.html      普贤菩萨劝发品
├── css/
│   └── style.css       Shared design system (copied from DiamondSutra)
└── docs/
    ├── readme.md       This file
    ├── ai-context.md   Context for AI assistants
    ├── architecture.md Technical decisions
    ├── roadmap.md      What's done / what's next
    └── plan.md         Original build plan
```

## How to preview locally

Open `index.html` in a browser. All pages are self-contained static HTML — no build step, no server required. TTS requires a browser with Web Speech API support (Chrome, Edge, Safari).

## Deployment

Deployed to GitHub Pages at `https://lugh3456.github.io/LotusSutra/` as part of the DharmaGate network.
