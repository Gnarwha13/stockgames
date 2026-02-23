# Stock Roguelite 🏆

**A portfolio-building roguelite. Roll stocks, face opponents, survive 10 rounds.**

> ⚠️ Not investment advice — returns are simulated for entertainment only.

---

## Overview

Stock Roguelite is a turn-based strategy game where you build a stock portfolio from gacha rolls and compete against CPU opponents in a 10-year compounding simulation. The difficulty ladder starts with volatile penny stocks and moonshots, and ramps to consistent broad-market ETFs — which are intentionally the hardest opponents to beat. Win rounds to earn cash, spend it on upgrades between rounds, and try to reach the end.

---

## Core Loop

```
Roll 10 cards ($10) → Pick your portfolio slots → Simulate 10 years →
Compare final portfolio value → Earn reward → Visit shop → Next round
```

You start with **$100**. Each round costs **$10** to roll. Manage your bankroll carefully — go broke and the run ends immediately.

---

## Rounds & Economy

| Outcome | Cash Reward |
|---|---|
| Victory | +$40 |
| Draw (within $1.50) | +$25 |
| Defeat | +$15 |

You always earn something, but consistent losses will starve you of upgrade budget.

---

## Difficulty Ladder

Each of the 10 rounds pits you against an opponent portfolio drawn from a specific tier pool. Earlier rounds use volatile, high-variance stocks. Later rounds use consistent, low-variance ETFs — which are the true final boss.

| Round | Name | Opponent Pool | Why It's Hard |
|---|---|---|---|
| 1 | Penny Pit | Unique, Ultra Legendary | Chaos — anything can happen |
| 2 | Speculative Zone | Ultra Legendary, Legendary | Deep speculative names |
| 3 | Moonshot Alley | Legendary, Ultra Legendary | Pre-revenue and quantum plays |
| 4 | Disruptor Arena | Mega Rare, Legendary | High-growth disruptors |
| 5 | Growth Gauntlet | Ultra Rare, Mega Rare | Big tech and growth stocks |
| 6 | Blue Chip Bowl | Very Rare, Ultra Rare | Established growth companies |
| 7 | Steady State | Rare, Very Rare | Blue chips — consistent performers |
| 8 | Dividend Duel | Somewhat Rare, Rare | Factor ETFs and dividend plays |
| 9 | Sector Wars | Uncommon, Somewhat Rare | Sector ETFs — efficient markets |
| 10 | **ETF Final Boss** | **Common, Uncommon** | **Broad index funds — nearly unbeatable** |

Early rounds are easier because high-variance stocks can swing wildly in your favor. By round 10, you're up against VOO and BND — assets with tight, positive return distributions and almost no chance of catastrophic loss.

---

## The Simulation

When you hit **Simulate 10 Years**, the game runs **40 quarterly simulations** (Q1 2015-style through Q4, 10 years later). Returns compound each quarter. A live chart draws both portfolio value curves in real time, starting at $100.

### Return Distributions (Quarterly Mean ± Std Dev)

| Tier | Mean | Std Dev | Real-world analog |
|---|---|---|---|
| Common | +2.5% | ±4.0% | S&P 500 index funds |
| Uncommon | +2.8% | ±6.5% | Sector ETFs |
| Somewhat Rare | +3.5% | ±9.0% | Factor/thematic ETFs |
| Rare | +3.0% | ±8.0% | Blue chip stocks |
| Very Rare | +4.5% | ±12.0% | Growth blue chips |
| Ultra Rare | +6.0% | ±18.0% | High-growth individual stocks |
| Mega Rare | +8.0% | ±25.0% | Disruptors |
| Legendary | +10.0% | ±32.0% | Pre-revenue / momentum |
| Ultra Legendary | +12.0% | ±45.0% | Deep speculative |
| Unique | +15.0% | ±60.0% | Moonshot pre-revenue |

Returns follow a normal distribution (Box-Muller transform). The higher the tier, the higher the ceiling — and the deeper the potential crash.

---

## Health Score Multipliers

Your portfolio's health score applies a cumulative bonus (or penalty) to your returns each quarter. These bonuses are **additive on top of raw simulated returns** and stack with the Health Bonus Amplifier upgrade.

| Dimension | Max Effect | How to Earn It |
|---|---|---|
| Asset Class Mix | **+8%** total | Hold equities + bonds + alternatives + international exposure |
| Geographic Spread | **+5%** total | Cover US + developed markets + emerging markets |
| Core Foundation | **+7%** total | Hold broad-market anchor ETFs (VOO, BND, VT, TLT, etc.) |
| Concentration Risk | **−15%** penalty | Avoid heavy weighting in speculative tiers |

The total bonus (up to **+20%** or as low as **−15%**) is spread across all 40 quarters. With the Health Bonus Amplifier II upgrade, these effects are doubled.

**Example:** A portfolio scoring +15% total health bonus gets +0.375% added to its return each quarter — which compounds to a meaningful edge over 10 years.

---

## Upgrades Shop

The shop opens between rounds. Upgrades persist for the rest of the run.

| Upgrade | Cost | Effect |
|---|---|---|
| 4th Portfolio Slot | $50 | Hold 4 stocks instead of 3 |
| 5th Portfolio Slot | $80 | Hold 5 stocks (requires 4th slot) |
| 6th Portfolio Slot | $120 | Hold 6 stocks (requires 5th slot) |
| +5 Roll Cards | $40 | See 15 cards per roll instead of 10 |
| +5 More Roll Cards | $70 | See 20 cards per roll (requires first upgrade) |
| Reroll Token | $30 | Swap one unselected card once per round |
| Card Lock | $35 | Carry one card over to the next round |
| Health Bonus Amplifier | $60 | Health bonuses are 1.5× stronger |
| Health Bonus Amplifier II | $90 | Health bonuses are 2.0× stronger (requires Amplifier I) |

**Strategy tip:** The Card Lock pairs well with a high-tier pull — keeping a NVDA or MSFT through multiple rounds gives you a reliable anchor while you build around it.

---

## Roll Weighting

Cards are not drawn purely at random — the pool is weighted to give each tier a realistic chance of appearing. Common tiers are always more likely. The weighting shifts slightly by round (later rounds weight Common slightly heavier, making it easier to find core ETFs for your health bonuses).

---

## Stock Universe

~130 tickers across 10 tiers, all active between 2015 and present:

- **Common** — VOO, VTI, VT, BND, TLT, LQD, AOR and other core index/bond ETFs
- **Uncommon** — QQQ, SCHD, GLD, sector ETFs (VGT, XLE, VHT…), RSP, NOBL
- **Somewhat Rare** — SOXX, CIBR, CLOU, BOTZ, factor ETFs, international strategies, commodity sub-sectors
- **Rare** — BRK.B, JPM, V, KO, WMT, MCD, LMT, XOM and other steady blue chips
- **Very Rare** — MSFT, AAPL, GOOGL, MA, BAC, GS and growth-oriented blue chips
- **Ultra Rare** — NVDA, META, AMZN, TSLA, NFLX, CRWD, NET and high-growth names
- **Mega Rare** — PLTR, RKLB, ASTS, SMCI, MSTR and disruptors
- **Legendary** — IONQ, CRSP, BEAM, LUNR and pre-revenue science plays
- **Ultra Legendary** — ARKK, ARKG, SE, MELI and volatile thematic names
- **Unique** — BABA, PDD, NKLA, EVGO and high-risk outliers

---

## Win Condition

Complete all 10 rounds. If you win 6 or more, the run ends as **RUN COMPLETE**. Fewer than 6 wins ends as **RUN ENDED**. Going bankrupt at any point ends the run immediately with **BANKRUPT**.

---

## Technical Notes

- **Single file** — all HTML, CSS, and JS in one `.html` file, no dependencies
- **Canvas chart** — 10-year simulation draws live on an HTML5 `<canvas>` element with DPR scaling
- **Normal distribution** — Box-Muller transform generates realistic quarterly returns per tier
- **Fonts** — Orbitron (headings/tickers) + Rajdhani (body) via Google Fonts
- **No data fetching** — fully offline, all returns are simulated
