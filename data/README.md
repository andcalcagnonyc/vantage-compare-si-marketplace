# Vantage Compare — SI Market Intelligence Dataset

An open, monthly-refreshed dataset of **286 company profiles across 16 Super Intelligence (SI) markets**: funding, valuation, revenue, headcount, LLM stack, architecture, pricing, GTM motion, analyst recognition, plus buyer-criteria scores, momentum and segment weights.

It is the data behind the [Vantage Compare app](https://andcalcagnonyc.github.io/vantage-compare-si-marketplace/), released under **CC BY 4.0** so you can analyze it, chart it, build on it and cite it.

| | |
|---|---|
| **Version** | 3.1 |
| **Data as of** | 2026-10-25 |
| **Markets** | 16 |
| **Company profiles** | 286 (275 unique companies; some appear in more than one market) |
| **Refresh** | Monthly |
| **License** | [CC BY 4.0](LICENSE) |

---

## Files

| File | Rows | What it contains |
|---|---|---|
| `json/vantage-compare-si-dataset.json` | — | Everything in one nested file: markets → summary, criteria, weights, trends, sources, exclusions → companies |
| `csv/markets.csv` | 16 | One row per market: definition, 2026 market size, growth, 2025 VC investment, maturity, criteria, trends |
| `csv/companies.csv` | 286 | One row per company per market: facts, positioning, investors, sources, qualification flags |
| `csv/scores.csv` | 2,288 | Long format: company × buyer criterion score (1–10) |
| `csv/momentum.csv` | 858 | Long format: company momentum (1–10) for 2024, 2025, 2026 |
| `csv/segment_weights.csv` | 384 | Buyer-criterion weights per market for SMB, Mid-Market and Enterprise (each segment sums to 1.0) |
| `csv/funding_rounds.csv` | 358 | Disclosed rounds: date, type, amount, valuation, lead investors |
| `csv/analyst_views.csv` | 70 | Paraphrased Gartner, IDC and Forrester positions per market, with source links |
| `csv/excluded.csv` | 101 | Commonly cited companies left out, with the reason |
| `csv/factcheck_log.csv` | 47 | Independent fact-check log: what was corrected, confirmed or flagged |
| `stats.json` | — | Row counts, version and changelog |
| `datapackage.json` | — | [Frictionless Data](https://frictionlessdata.io/) descriptor for tooling |

Join keys: `market_id` (e.g. `llm`, `code`, `crm`) and `company_id` (a URL-safe slug of the company name). The same `company_id` in two markets is the same company profiled for that market.

### Markets

| `market_id` | Market |
|---|---|
| `llm` | Foundation Models (LLM) |
| `aiemp` | SI Employees & Agent Platforms |
| `code` | SI Coding Agents & Dev Platforms |
| `cx` | SI Customer Service & CX Agents |
| `crm` | SI CRM |
| `rev` | SI Sales & Revenue Intelligence |
| `fin` | SI Finance & Accounting |
| `legal` | SI Legal |
| `comp` | SI Compliance & GRC Platforms |
| `psa` | SI-driven PSA & MSP Platforms |
| `hw` | SI Compute Hardware & Networking |
| `dc` | SI Data Centers & Neoclouds |
| `data` | SI Data & Analytics Platforms |
| `sec` | SI-driven Security Operations |
| `net` | SI Agentic Networking |
| `phys` | Physical SI · Robots & Humanoids |

### Key company fields (`companies.csv`)

| Field | Meaning |
|---|---|
| `total_funding_usd_m` | Total equity raised, USD millions; empty for public companies and divisions |
| `last_round`, `valuation_usd_b` | Latest disclosed round and valuation (USD billions) |
| `revenue_range`, `revenue_est_usd_m`, `revenue_basis` | Revenue as reported or estimated; the estimate is the range midpoint; the basis says whether it is reported, press or analyst estimate |
| `llm_stack`, `architecture` | Models used and deployment / agent architecture |
| `target_segment`, `gtm_motion`, `pricing_model` | Who they sell to and how |
| `positioning`, `key_message`, `differentiators`, `weaknesses` | Paraphrased market positioning |
| `analyst_recognition` | Gartner, IDC, Forrester placements where public |
| `is_public`, `raised_50m_plus`, `revenue_100m_plus` | Qualification flags (see below) |
| `sources` | 2–4 source URLs per profile |

List values in CSV cells are separated by `; `. The JSON keeps them as arrays.

---

## Methodology

1. **Qualification.** A company is included only if it has raised at least $50M in equity, or is public, or is a division of a public or large private company. Companies above $100M revenue in the category are prioritized. Each market keeps at least 15 qualified companies; notable exclusions are listed with reasons.
2. **Research.** Market agents compile each profile from analyst coverage (Gartner, IDC, Forrester — often via vendor or press summaries, since reports are paywalled), company filings and investor relations, and reputable press. Text is paraphrased.
3. **Scores.** Each market has 8 buyer criteria. Scores (1–10) and momentum (1–10 per year) are **evidence-informed editorial estimates**, not survey results.
4. **Weighted score.** In the app, a company's score for a segment is `Σ (weight × criterion score) × 10`, giving 0–100. Weights come from `segment_weights.csv` and can be changed by the user.
5. **Sensitivity.** The app tests ranking stability with a tornado analysis (each weight moved ±50%) and a Monte Carlo simulation (±30% random noise on all weights).
6. **2027 projection.** Momentum for 2027 extends each company's 2025→2026 change at 70% strength, clamped to 1–10.
7. **QA and fact-check.** Automated checks cover counts, thresholds, completeness, weight sums and source presence. A separate agent re-verifies high-impact figures; every correction and open flag is in `factcheck_log.csv`.

## Known limitations

- Private-company revenue is often a press or analyst estimate; check `revenue_basis` before relying on a figure.
- Items marked `flagged` in the fact-check log are unverified.
- Some market-size growth figures are one-year growth, not multi-year CAGR; see `growth_period` and `growth_basis` in `markets.csv`.
- Scores reflect a point-in-time editorial view and should be validated against your own buyer research.
- "SI" (Super Intelligence) is used in place of "AI" throughout, following the app's terminology.

Found an error? Open an issue with the company, field and a source.

---

## How to cite

> Calcagno, A. (2026). *Vantage Compare — SI Market Intelligence Dataset* (Version 3.1, data as of 2026-10-25) [Data set]. https://github.com/andcalcagnonyc/vantage-compare-si-marketplace

Attribution required by CC BY 4.0: **"Vantage Compare by Andrea Calcagno"**, with a link to this repository and an indication of any changes you made.

## License

The contents of this `data/` folder are licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). The Vantage Compare application, its code and design outside this folder remain proprietary; see the repository [LICENSE](../LICENSE).

Company names and trademarks belong to their owners. Source links point to third-party content that keeps its own terms.
