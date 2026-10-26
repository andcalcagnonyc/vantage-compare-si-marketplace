# Vantage Compare — SI Market Intelligence

**Know where you win before you spend a dollar on roadmap, messaging or go-to-market.**

Vantage Compare is a decision tool for product marketers, product managers and GTM leaders competing in Super Intelligence (SI) markets. It turns scattered analyst reports, funding data and vendor claims into one weighted, segment-aware view of every market — and tells you how stable your position really is when buyer priorities shift.

> **Live demo:** [andcalcagnonyc.github.io/vantage-compare-si-marketplace](https://andcalcagnonyc.github.io/vantage-compare-si-marketplace/)
> Version **3.1** · Data as of **October 25, 2026** · Refreshed monthly

---

## The problem

Competitive analysis in SI markets breaks down in three places:

1. **The landscape moves faster than the slide deck.** Rounds, ARR milestones and acquisitions land weekly; a quarterly battlecard is out of date before the QBR.
2. **"Who's ahead" depends on who's buying.** An enterprise CISO and a mid-market RevOps lead weight the same criteria very differently, yet most comparisons publish a single ranking.
3. **Nobody tests the ranking.** A leader that drops to fourth place after a small change in buyer weights is not a leader — and teams rarely find out until a deal is lost.

## What Vantage Compare does

| Decision | What you get |
|---|---|
| **Roadmap priorities** | A gap-to-best backlog ranked P0–P2 by the rank impact of closing each capability gap |
| **Messaging** | Ownable messaging pillars where you lead, and claims to avoid where competitors are stronger |
| **Go-to-market** | Segment fit, crowding analysis and a recommended GTM motion per buyer segment |

### Coverage

- **16 SI markets, 286 companies** — including LLMs, SI Employees, SI Coding, Agentic Networking, Security Operations, SI CRM, Sales & Revenue, Customer Service, PSA & MSP, Compliance & GRC, Data & Analytics and Physical SI (robots and humanoids)
- **Qualification bar:** at least $50M raised or publicly listed; companies above $100M revenue are prioritized; 15+ qualified companies per market
- **Every company sheet** covers funding and last round, valuation, revenue, headcount, LLM stack, architecture, focus, pricing, GTM motion and analyst recognition
- **Market view** with 2025 VC investment benchmarked to Crunchbase and PitchBook, deduplicated so mega-rounds are counted once

### Analytics engine

- **Weighted scoring by buyer segment** — 8 buyer criteria per market with segment weight presets, fully adjustable
- **Sensitivity analysis** — tornado chart on ±50% weight swings and Monte Carlo simulation on ±30% weight noise, reporting how often the leader keeps first place
- **Momentum & 2027 projection** — trend lines with a transparent drift rule, so you see who is gaining ground, not just who is ahead today
- **Funding & investor view** with stage filters

### Built for real use

- **Five languages:** English, 中文 (Simplified Chinese), Español, Français, Italiano — app and reports
- **Per-market PDF reports** ready for a board or QBR
- **⌘K search palette**, sortable comparison matrix, dark and light themes, works at phone width
- **Single-file web app** — no install, no login, opens in any modern browser

---

## How the data is built

Vantage Compare is produced by a coordinated team of specialized AI agents with human sign-off at every gate:

1. **Frame the job** — decision brief for PMMs, PMs and GTM leads
2. **Taxonomy & data contract** — markets, criteria and a shared schema
3. **Research sprint** — parallel market agents using Gartner, IDC and Forrester coverage plus filings and press
4. **Data QA** — automated checks on counts, thresholds, completeness, weight sums and source presence
5. **Independent fact-check** — a separate red-team agent re-verifies high-impact figures; every correction and open flag is logged in the app
6. **Scoring & sensitivity engine** — deterministic, reproducible results
7. **Release check** — every view × market × segment rendered headless with zero errors and zero label overlaps

Unverified figures are flagged in the app rather than hidden, so you always know how much weight a number can carry.

## Roadmap

- Market validation with PMM interviews in priority markets
- Two new markets queued: **Security for SI** and **SI Data & Identity Security**
- Licensed analyst and funding data feeds, monthly agent-driven refresh with change explanations
- Auto-drafted battlecards from the priorities view

## Using it

Open `index.html` in a browser, or visit the [live demo](https://andcalcagnonyc.github.io/vantage-compare-si-marketplace/). Pick a market, choose a buyer segment, and adjust weights to see rankings, sensitivity and priorities update instantly.

## Repository contents

```
index.html          The complete application (data, engine and UI in one file)
fonts/noto-sc.ttf   Font used for Simplified Chinese text in PDF reports
```

---

## Credits

**Designed by Andrea Calcagno, Super Intelligence Expert**
[LinkedIn](https://www.linkedin.com/in/andreacalcagno/) · [and.calcagno@gmail.com](mailto:and.calcagno@gmail.com)

Powered by Claude (Anthropic).

© 2026 Andrea Calcagno. All rights reserved. See [LICENSE](LICENSE).

*Terminology note: "SI" (Super Intelligence) is used throughout in place of "AI".*
