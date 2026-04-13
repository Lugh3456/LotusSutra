# Build Plan — Lotus Sutra Mini Site

*Original plan, recorded 2026-04-13*

## Goal

Build a 28-chapter interactive reading site for the Lotus Sutra (妙法莲华经), matching the structure and design of the existing DiamondSutra mini site, to be deployed under the DharmaGate portal.

## Structure to match (DiamondSutra pattern)

Each chapter page:
1. Portal bar (← DharmaGate link)
2. Header: chapter number + Chinese title + 妙法莲华经 subtitle + prev/contents/next nav
3. Full text section: Chinese sutra excerpt + TTS button
4. Line-by-line explanation: 4 cards, each with Chinese explanation (visible) + English toggle (hidden)
5. Summary: Chinese paragraph + English toggle
6. Footer: DharmaGate link + copyright

Index page:
- 28-chapter grid, same `.chapter-grid` layout as DiamondSutra index
- Each card: chapter number (saffron) + Chinese title

## Chapters

| # | Chinese title | Key content |
|---|---------------|-------------|
| 1 | 序品 | Assembly, Manjushri explains the light |
| 2 | 方便品 | One Vehicle (一乘法), ten suchnesses |
| 3 | 譬喻品 | Burning house parable |
| 4 | 信解品 | Prodigal son parable |
| 5 | 药草喻品 | Three herbs / one rain |
| 6 | 授记品 | Kashyapa et al. receive prophecy |
| 7 | 化城喻品 | Conjured city parable |
| 8 | 五百弟子受记品 | Jewel in the robe parable |
| 9 | 授学无学人记品 | Ananda and Rahula |
| 10 | 法师品 | Three chambers of the Tathagata |
| 11 | 见宝塔品 | Treasure stupa, two Buddhas seated together |
| 12 | 提婆达多品 | Dragon girl's enlightenment |
| 13 | 劝持品 | Vow to uphold in the degenerate age |
| 14 | 安乐行品 | Four practices of ease; topknot jewel parable |
| 15 | 从地涌出品 | Bodhisattvas emerge from the earth |
| 16 | 如来寿量品 | Eternal Buddha (核心章) |
| 17 | 分别功德品 | Merit of the assembly hearing Ch. 16 |
| 18 | 随喜功德品 | Merit of rejoicing in others' merit |
| 19 | 法师功德品 | Six sense purifications |
| 20 | 常不轻菩萨品 | Never Disparaging Bodhisattva |
| 21 | 如来神力品 | Cosmic confirmation, finger-snap |
| 22 | 嘱累品 | Formal entrustment, three crown-touchings |
| 23 | 药王菩萨本事品 | Self-immolation offering |
| 24 | 妙音菩萨品 | Wonderful Sound, 34 transformation bodies |
| 25 | 观世音菩萨普门品 | Guanyin, 33 bodies, seven dangers |
| 26 | 陀罗尼品 | Dharani protections |
| 27 | 妙庄严王本事品 | King Wonderful Adornment converted |
| 28 | 普贤菩萨劝发品 | Samantabhadra's vow, closing |

## Build process

Write one section file per Write tool call (learned from DiamondSutra: batching causes API 400 errors). Full content, no shortcuts.

## CSS

Copy `css/style.css` verbatim from DiamondSutra — do not modify. Same design system.

## After all 28 sections

1. Write `docs/` folder
2. Update DharmaGate `index.html`: activate Lotus Sutra card
3. Update DharmaGate `docs/ai-context.md` and `docs/roadmap.md`
