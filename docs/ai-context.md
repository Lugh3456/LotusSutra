# AI Context — Lotus Sutra Mini Site

**Project:** Lotus Sutra (妙法莲华经) interactive reading site
**Status:** Active — all 28 chapters complete, full annotation coverage verified
**Last updated:** 2026-05-01
**Part of:** DharmaGate portal (https://lugh3456.github.io/DharmaGate/)
**Live URL:** https://lugh3456.github.io/LotusSutra/

---

## Purpose

This site makes the Lotus Sutra accessible for CK's personal study. Each chapter has:
- Chinese sutra text with TTS playback
- Chinese explanations (always visible)
- English explanations (toggled, hidden by default)
- Bilingual summary

---

## Design system

All styling comes from `css/style.css`, copied verbatim from DiamondSutra. Key tokens:

```css
--red: #b83232
--saffron: #c8820a
--ink: #1c0f0f
--bg: #f7f0e6
--card-bg: #fdf8f2
```

Fonts: Noto Serif SC (headings, body Chinese), Noto Sans SC (UI labels), loaded from Google Fonts.

---

## Page structure (all section pages)

Every `sectionN.html` follows this exact pattern:

```
portal-bar → header (h1 + nav) → main:
  full-text section (Chinese text + TTS button)
  line-explanation section (variable number of explanation-cards — now fully covering all source-text lines)
  summary section (Chinese + English toggle)
footer
```

JavaScript: `toggleDetail()` for show/hide English, `speak()` for TTS.

---

## Chapter list

| File | Chapter | Title |
|------|---------|-------|
| section1.html | Ch 1 | 序品 |
| section2.html | Ch 2 | 方便品 |
| section3.html | Ch 3 | 譬喻品 (火宅喻) |
| section4.html | Ch 4 | 信解品 (穷子喻) |
| section5.html | Ch 5 | 药草喻品 |
| section6.html | Ch 6 | 授记品 |
| section7.html | Ch 7 | 化城喻品 |
| section8.html | Ch 8 | 五百弟子受记品 (衣珠喻) |
| section9.html | Ch 9 | 授学无学人记品 |
| section10.html | Ch 10 | 法师品 |
| section11.html | Ch 11 | 见宝塔品 |
| section12.html | Ch 12 | 提婆达多品 (龙女成佛) |
| section13.html | Ch 13 | 劝持品 |
| section14.html | Ch 14 | 安乐行品 (髻珠喻) |
| section15.html | Ch 15 | 从地涌出品 |
| section16.html | Ch 16 | 如来寿量品 (如来常住) |
| section17.html | Ch 17 | 分别功德品 |
| section18.html | Ch 18 | 随喜功德品 |
| section19.html | Ch 19 | 法师功德品 (六根清净) |
| section20.html | Ch 20 | 常不轻菩萨品 |
| section21.html | Ch 21 | 如来神力品 |
| section22.html | Ch 22 | 嘱累品 |
| section23.html | Ch 23 | 药王菩萨本事品 |
| section24.html | Ch 24 | 妙音菩萨品 |
| section25.html | Ch 25 | 观世音菩萨普门品 |
| section26.html | Ch 26 | 陀罗尼品 |
| section27.html | Ch 27 | 妙庄严王本事品 |
| section28.html | Ch 28 | 普贤菩萨劝发品 |

---

## Things NOT to change without asking CK

- CSS design tokens (matches DiamondSutra exactly)
- English toggle pattern (hidden by default, JS-driven)
- TTS voice preference (Ting-Ting, zh-CN, rate 0.9)
- Portal bar link (always points to DharmaGate)
- Footer copyright line

---

## Common tasks

**Add content to a chapter:** Edit the relevant `sectionN.html`. The `chineseText` paragraph and explanation cards are plain HTML — no build step needed.

**Fix a navigation link:** Each section has `← prev`, `目录 Contents`, `next →` links in the `<nav class="section-nav">`. Section 1 has no prev; section 28 has no next.

**Deploy:** Push to GitHub. Pages auto-deploys from the repo root.
