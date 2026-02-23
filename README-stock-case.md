# Stock Case 🎰

**A gacha-style portfolio simulator. Open cases, pull stocks, build a collection.**

> ⚠️ Not investment advice — purely for entertainment purposes.

---

## Overview

Stock Case is a CS2-inspired loot case simulator where every pull rewards a real stock or ETF instead of a cosmetic skin. It uses synthesized Web Audio for sound, a CSS slot machine animation, and a portfolio health scoring system. Zero dependencies beyond Google Fonts — single self-contained HTML file.

---

## How to Play

1. Click **Open Case** to spend a pull and spin the slot machine
2. The reel decelerates over ~6 seconds before landing on your result
3. A result card reveals the ticker, rarity tier, alternative tickers, and external info links
4. Click **Collect** to add the stock to your portfolio
5. Repeat to build out your collection and track your portfolio health score

---

## Rarity Tiers

Tiers are ordered from most to least common. Each has a fixed drop probability:

| Tier | Odds | Color | Contents |
|---|---|---|---|
| Common | 1 in 2 | Gray | Broad index ETFs, core bonds, balanced funds |
| Uncommon | 1 in 4 | Blue | Sector ETFs, REITs, commodities, dividend plays |
| Somewhat Rare | 1 in 8 | Cyan | Factor ETFs, thematic ETFs, commodity sub-sectors |
| Rare | 1 in 16 | Purple | Steady blue-chip stocks (KO, WMT, BRK.B, JPM…) |
| Very Rare | 1 in 32 | Orange | Growth-oriented blue chips (MSFT, AAPL, GOOGL…) |
| Ultra Rare | 1 in 64 | Red | High-growth individual stocks (NVDA, META, TSLA…) |
| Mega Rare | 1 in 128 | Pink | Disruptors and momentum names |
| Legendary | 1 in 256 | Cyan | Pre-revenue and speculative growth |
| Ultra Legendary | 1 in 512 | Gold | Deep speculative names |
| Unique | 1 in 1024 | White | Moonshot pre-revenue plays |
| ✨ Shiny | Remainder | Rainbow | Any stock from the full list, with rainbow animation |

The **✨ Shiny** tier is special — it can produce a shiny version of any stock in the game, from a Common ETF to a Unique moonshot. The card plays a 4-second sparkle fanfare and animates with a rainbow ticker gradient.

---

## Portfolio Health Score

After your first pull, the **Portfolio Health** panel appears and scores your collection from 0–100 across four dimensions:

| Dimension | Max Bonus | How to Score It |
|---|---|---|
| Asset Class Mix | 25 pts | Hold equities + bonds + alternatives + international |
| Geographic Spread | 25 pts | Cover US + developed markets + emerging markets |
| Concentration Risk | 25 pts | Penalized for holding too many speculative tiers |
| Core Foundation | 25 pts | Reward for broad-market index anchors (VOO, BND, etc.) |

**Grades:** S (90+) · A (75–89) · B (60–74) · C (45–59) · D (30–44) · F (<30)

---

## Sound Engine

All audio is synthesized via the Web Audio API — no external files. Each tier has a unique riff:

- **Common** — two-note ding
- **Uncommon** — bright three-note rise
- **Somewhat Rare** — four-note shimmer
- **Rare** — warm arpeggio with sustain
- **Very Rare** — power chord into melody
- **Ultra Rare** — dramatic cinematic sting
- **Mega Rare** — cyberpunk synth + sparkle cascade
- **Legendary** — full brass fanfare with bass foundation
- **Ultra Legendary** — eerie chime waterfall
- **Unique** — magical chime cascade
- **✨ Shiny** — 4-second reveal: bass shimmer → sparkle cascades → choir swell → soaring finale

---

## Import / Export

The portfolio panel includes three actions:

- **⬇ Export .txt** — saves a formatted plaintext file with your full holdings, health score breakdown, and timestamp
- **⬆ Import .txt** — parses a previously exported file and restores your collection
- **✕ Clear** — resets everything after a confirmation prompt

---

## Stock Universe

225+ tickers spanning:

- Broad market & factor ETFs
- Sector ETFs (all 11 GICS sectors)
- US & international bonds (short, intermediate, long-term, corporate, high-yield)
- Commodities (gold, silver, oil, agriculture, base metals)
- Blue-chip individual stocks
- Growth and momentum stocks
- Speculative and pre-revenue names

All tickers existed between 2015 and the present day. No cryptocurrency.

---

## Technical Notes

- **Single file** — all HTML, CSS, and JS in one `.html` file
- **No build step** — open directly in any modern browser
- **Web Audio API** — all sound synthesized at runtime; first interaction initializes the audio context
- **Slot animation** — CSS `cubic-bezier(0.03, 1, 0.15, 1)` deceleration over 6 seconds, landing on a pre-positioned winner at index 16
- **Fonts** — Orbitron (headings/tickers) + Rajdhani (body) via Google Fonts
