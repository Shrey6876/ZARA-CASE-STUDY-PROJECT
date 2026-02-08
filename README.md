

```markdown
# ZARA STRATEGIC ANALYSIS  
### Fast Fashion, Global Expansion, and Value Creation (2000–2024)

> A consulting-grade, data-driven analysis of Inditex/Zara’s business model, financial performance, and global strategy, built for MBA and executive audiences.

![Status](https://img.shields.io/badge/status-complete-success)
![Focus](https://img.shields.io/badge/focus-strategy%20%7C%20finance%20%7C%20operations-blue)
![Period](https://img.shields.io/badge/period-2000--2024-royalblue)
![Tech](https://img.shields.io/badge/tools-Excel%20%7C%20Python%20%7C%20Jupyter%20%7C%20DCF-lightgrey)

---

## 1. Executive Snapshot

This repo is a **full strategic case** on Zara/Inditex, not just a spreadsheet:

- Rebuilds 24 years of Inditex financials, competitive benchmarks, and key KPIs.
- Deconstructs Zara’s fast fashion engine: vertical integration, JIT, store economics, and expansion.
- Values Inditex with a **10-year DCF + scenarios + sensitivities**, linked directly to assumptions.
- Produces board-ready materials: an **Executive Summary**, dashboards, and supporting exhibits.

Use this as:
- A portfolio project to demonstrate MBA-level strategic and financial thinking.
- A teaching case backbone for classroom/ workshop discussion.
- A starting point for further work (ESG, digital, private label disruption, Shein, etc.).

---

## 2. Repository Map

```text
ZARA-CASE-STUDY-PROJECT/
├── README.md                     ← You are here
├── environment.yml               ← Conda environment (optional)
├── requirements.txt              ← Python dependencies
├── .gitignore                    ← Professional ignore rules
│
├── data/
│   ├── raw/                      ← Source data (Inditex ARs, market data, etc.)
│   ├── processed/                ← Cleaned, analysis-ready datasets
│   └── README_data.md            ← Data dictionary and governance
│
├── model/
│   ├── Z-MODEL-Final.xlsx        ← Main Excel valuation model (10-year DCF)
│   └── assumptions_log.md        ← Assumption-by-assumption documentation
│
├── notebooks/
│   ├── 01_descriptive_diagnostics.ipynb
│   ├── 02_peer_benchmarking.ipynb
│   ├── 03_store_economics.ipynb
│   ├── 04_international_expansion.ipynb
│   ├── 05_valuation_dashboard.ipynb
│   └── 06_sensitivity_scenarios.ipynb
│
├── reports/
│   ├── executive_summary_template.md  ← Board-ready memo template
│   └── slides/                        ← Optional: deck exports
│
├── scripts/
│   ├── data_pipeline.py           ← Raw → processed ETL
│   ├── compute_kpis.py           ← Margin, ROE, ROIC, turns, etc.
│   └── generate_charts.py        ← Plotly figures for notebooks/reports
│
├── tests/
│   ├── test_data_integrity.py    ← Data sanity checks
│   └── test_model_linkages.py    ← Model consistency checks
│
└── CONTRIBUTING.md               ← How to extend this like a real project
```

---

## 3. What This Project Actually Does

### 3.1 Strategy Questions Answered

The analysis is built around three CEO/Board-level questions:

```text
1. Is Zara’s fast fashion model structurally defensible, or a temporary arbitrage?
2. How should Inditex sequence global expansion (Europe vs. USA vs. Asia) from 2003 onward?
3. What growth and margin trajectory is required to justify its valuation, and where is the risk?
```

The repo addresses these through:

- **Competitive positioning**: Zara vs. H&M, Gap, Benetton, Fast Retailing, plus more recent players using extended data [file:1][file:21].
- **Value chain analysis**: How design, sourcing, manufacturing, logistics, and retail integrate.
- **International strategy**: Country-by-country attractiveness and entry mode choices using market data and case exhibits [file:21].
- **Capital markets lens**: How ROIC, cash conversion, and growth interplay in valuation [file:1][file:4].

### 3.2 Financial Engine Rebuild

From 2000–2024, the project reconstructs:

- Full **P&L, balance sheet, cash flow** for Inditex from annual reports [file:4][file:23][file:24].
- Key ratios:
  - Gross, EBIT, and net margins, by year.
  - ROE and ROIC by concept (Zara, Pull&Bear, Bershka, etc.) [file:23][file:24].
  - Inventory turns and cash conversion cycle.
  - Capex intensity and FCF profile.

Using these, we:

- Classify Zara’s evolution into four phases (European expansion, global diversification, digital transformation, COVID recovery) [file:1].
- Quantify the margin expansion (roughly 860 bps from 2000 to 2024) and its drivers [file:1][file:4].
- Attribute value creation to operating improvements vs. multiple expansion.

### 3.3 DCF and Scenario Suite

The Excel model (`Z-MODEL-Final.xlsx`) and Python notebooks jointly support:

- 10-year forecast of:
  - Revenue by geography and concept.
  - Store count, sqm, and productivity [file:1][file:23][file:24].
  - EBIT margins with explicit bridges (markdowns, sourcing mix, logistics efficiency).
- Valuation tools:
  - Base, Bear, Bull cases with explicit assumptions.
  - WACC and terminal growth sensitivities.
  - Tornado charts of key drivers.

Each assumption that matters is documented in `model/assumptions_log.md`, including its impact on valuation.

---

## 4. How to Run and Explore

### 4.1 Quickstart

You can use either Conda or plain `pip`.

```bash
git clone https://github.com/yourusername/ZARA-CASE-STUDY-PROJECT.git
cd ZARA-CASE-STUDY-PROJECT
```

Using Conda:

```bash
conda env create -f environment.yml
conda activate zara-case
```

Or with `pip`:

```bash
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Then:

```bash
# Check everything is wired correctly
pytest tests/ -v

# Launch notebooks
jupyter lab
```

Suggested notebook order:

1. `01_descriptive_diagnostics.ipynb` – understand Inditex’s trajectory.
2. `02_peer_benchmarking.ipynb` – see how Zara stacks up.
3. `03_store_economics.ipynb` – dive into store productivity, rents, and labor.
4. `04_international_expansion.ipynb` – country scoring and rollout logic.
5. `05_valuation_dashboard.ipynb` – visual DCF and scenario outputs.
6. `06_sensitivity_scenarios.ipynb` – stress test key assumptions.

### 4.2 Working With the Excel Model

- Open `model/Z-MODEL-Final.xlsx`.
- Core sheets:
  - `HISTORICALS`: 2000–2024 actuals and derived ratios [file:1][file:4][file:23][file:24].
  - `FORECAST`: 10-year projections by scenario.
  - `DCF`: Free cash flow, WACC, terminal value, equity bridge.
  - `DASHBOARD`: Visual summary (for printing or slides).

Input cells are visually separated from formulas (e.g., different fill colors), and each major input is linked back to `assumptions_log.md` for transparency.

---

## 5. Methodology Overview

### 5.1 Data Sources (High-Level)

All underlying data are derived from:

- Inditex annual reports (2000–2024) for financials, store counts, and KPIs [file:4][file:23][file:24].
- The Harvard Business School case “Zara: Fast Fashion” for early-2000s operating metrics and competitor snapshot [file:21].
- Public market and industry statistics for apparel market sizing and macro context [file:1][file:4].

Sensitive or copyrighted documents (e.g., full HBS case PDF) are explicitly excluded from version control; only derived factual data are used.

### 5.2 Key Analytical Lenses

The project integrates:

- **Porter and value chain**: where Zara’s economic rents come from in the chain.
- **VRIO / resource-based view**: organization-level capabilities that are hard to copy.
- **International expansion logic**: market attractiveness vs. distance/complexity.
- **Capital markets framing**: growth, margin, and capital efficiency required to justify valuation.

Each notebook and report makes explicit which framework is used, and why.

---

## 6. How to Use This as a Portfolio Piece

You can position this project as:

- Evidence of:
  - Quantitative comfort (DCF, ROIC, multi-year modeling).
  - Strategic thinking (sequencing of markets, business model defense).
  - Communication skill (board-ready Executive Summary).

Ideas for showcasing:

- Link this GitHub repo in:
  - CV, under “Selected Projects”.
  - MBA essays (e.g., “I built a full strategic and valuation model for Zara/Inditex …”).
  - LinkedIn “Featured” section.
- Turn `reports/executive_summary_template.md` into a polished PDF and attach it alongside.

---


If you paste this into `README.md` and swap in your details and actual file names, your repo will look like a serious, consulting-grade Zara case study rather than a basic class assignment.
