<div align="center">

# 🚀 StartupPulse India
### Startup Ecosystem Intelligence & Growth Analytics

**Explore a decade of India's startup growth through interactive analytics, geographic insights, sector intelligence, and data-driven forecasts.**

![Python](https://img.shields.io/badge/Python-Data%20Analytics-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-Interactive%20Dashboard-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-SQL%20Analytics-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-Visualizations-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-Clustering-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)

**[Overview](#-project-overview) · [Features](#-interactive-dashboard) · [Analytics](#-analytics-engine) · [Setup](#-run-locally) · [Insights](#-key-insights)**

</div>

---

## 📌 Project Overview

**StartupPulse India** is an end-to-end data analytics platform for exploring how India's startup ecosystem has evolved across states, industries, and years. It transforms government startup-recognition statistics into an interactive seven-page dashboard and an analytical pipeline covering trends, regional concentration, emerging industries, clustering, hotspot detection, and forecasting.

The dataset tracks **DPIIT-recognized startups**, not funding raised, revenue, or startup survival.

<div align="center">

| 🏢 Recognized startups | 🗺️ States & UTs | 🧩 Industries | 📅 Historical period |
|:---:|:---:|:---:|:---:|
| **207,134** | **36** | **56** | **2016–2025** |

</div>

> **Data context:** The repository's dataset covers recognition years 2016–2025 and is described as available as of 31 May 2026. It is a historical snapshot, not a live-updating feed.

## ✨ Interactive Dashboard

Explore the ecosystem through seven focused views:

| Module | What you can explore |
|---|---|
| 📊 **Overview** | National growth, annual recognitions, concentration trends, and headline insights |
| 🗺️ **State Explorer** | State-wise performance, growth, leading industries, and specialization |
| 🧪 **Sector Explorer** | Industry trends, sector share, and emerging technology categories |
| 📈 **Growth Map** | State segments based on ecosystem scale and growth momentum |
| 🎯 **Hotspot Finder** | Ranked state–sector opportunities with adjustable scoring weights |
| 🔮 **Forecast** | Backtested forecasting models and 2026–2027 projections |
| 🧾 **Data & Method** | Data definitions, analysis assumptions, and methodology |

### 📸 Dashboard Preview

> Replace the image paths below with screenshots captured from your running dashboard. The placeholders are intentionally not presented as real screenshots.

<details open>
<summary><b>📊 Overview — national startup growth</b></summary>

<!-- Add a screenshot at assets/screenshots/overview.png and uncomment the next line. -->
<!-- ![StartupPulse overview dashboard](assets/screenshots/overview.png) -->

**Screenshot to add:** Overview page showing KPI cards, yearly recognition trends, and concentration charts.

</details>

<details>
<summary><b>🗺️ State Explorer — regional performance</b></summary>

<!-- ![State explorer](assets/screenshots/state-explorer.png) -->

**Screenshot to add:** State comparison, growth metrics, and top industries.

</details>

<details>
<summary><b>🎯 Hotspot Finder — opportunity discovery</b></summary>

<!-- ![Hotspot finder](assets/screenshots/hotspot-finder.png) -->

**Screenshot to add:** Adjustable scale, momentum, and specialization weights with the ranked hotspot results.

</details>

<details>
<summary><b>🔮 Forecast — growth projections</b></summary>

<!-- ![Forecast dashboard](assets/screenshots/forecast.png) -->

**Screenshot to add:** Model comparison and 2026–2027 projection chart.

</details>

## 🧠 Analytics Engine

```mermaid
flowchart LR
    A[Government recognition data] --> B[Audit & clean]
    B --> C[Complete state-sector-year panel]
    C --> D[SQLite analysis]
    D --> E[Statistics & clustering]
    E --> F[Hotspot scoring & forecasts]
    F --> G[Streamlit dashboard & reports]
```

<details>
<summary><b>🔍 Data preparation & SQL</b></summary>

- Audit missing values, duplicate combinations, and category inconsistencies.
- Expand the sparse input into a complete state × industry × year panel, filling absent combinations with zero where appropriate.
- Analyze rankings, year-on-year change, cumulative counts, and industry share using SQLite window functions and common table expressions.

</details>

<details>
<summary><b>📐 Statistical & geographic analysis</b></summary>

- Compare absolute growth, compound annual growth rate (CAGR), and momentum.
- Measure geographic concentration with the Herfindahl–Hirschman Index (HHI) and top-state shares.
- Measure state-sector specialization using Location Quotient (LQ).
- Examine associations using Spearman correlation.

</details>

<details>
<summary><b>🤖 Clustering, hotspots & forecasting</b></summary>

- Segment states by industry mix using KMeans, with silhouette-based model selection.
- Rank state–sector hotspots using scale, momentum, and specialization; adjust their relative weights in the dashboard.
- Compare naive, linear, exponential, and average-growth forecasting methods on held-out years.
- Display 2026–2027 projections as model-dependent estimates, not guaranteed outcomes.

</details>

## 📊 Key Insights

The included historical analysis reports:

| Finding | Result |
|---|---|
| Startup recognition growth | **5,473 in 2017 → 49,430 in 2025** |
| Geographic diversification | Top-five-state share decreased from **63.6% to 53.1%** |
| AI sector expansion | **309 recognitions in 2022 → 2,360 in 2025** |
| Notable hotspot examples | Karnataka × AI; Telangana × AI; Rajasthan × Renewable Energy |
| Forecasting | Four methods compared; best reported holdout MAPE **15.3%** |

*These are findings from the included dataset and analysis, not live statistics. A recognized startup is not necessarily an active or funded startup.*

## 🛠️ Technology Stack

| Layer | Technologies |
|---|---|
| Data processing | Python, pandas, NumPy |
| SQL analytics | SQLite |
| Statistical analysis | SciPy |
| Machine learning | scikit-learn |
| Charts | Plotly, Matplotlib |
| Dashboard | Streamlit |

## 💻 Run Locally

### Prerequisites

- Windows, macOS, or Linux
- Python and `pip`
- Git (optional, if cloning a repository)

From the project root, create and activate a virtual environment:

**Windows PowerShell**

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

**macOS / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Run the complete analytical pipeline:

```bash
python startup_analysis.py
```

Launch the dashboard:

```bash
streamlit run dashboard.py
```

Open the local URL shown in the terminal (typically `http://localhost:8501`).

> If the dataset or processed outputs are missing, check the expected files under `data/` before running the dashboard.

## 📁 Project Structure

```text
.
├── dashboard.py                 # Seven-page Streamlit interface
├── startup_analysis.py          # Data preparation and analytical pipeline
├── render_dashboard_preview.py  # Static preview image generation
├── requirements.txt             # Python dependencies
├── data/
│   ├── raw/                     # Source data
│   └── processed/               # Cleaned data and SQLite outputs
├── outputs/
│   ├── findings.md              # Generated analytical findings
│   ├── figures/                 # Charts
│   ├── tables/                  # Analysis tables
│   └── dashboard/               # Dashboard previews
└── README.md
```

## 🎯 Project Objectives

1. Understand India's startup recognition growth over time.
2. Compare startup ecosystems across states and industries.
3. Identify emerging sectors and regional specializations.
4. Discover high-potential state–sector combinations using transparent scoring.
5. Evaluate forecast models and communicate uncertainty through interactive visualizations.

## ⚠️ Data & Model Limitations

- DPIIT recognitions are not measures of startup funding, revenue, survival, or employment.
- Sector classifications can change over time and may affect trend comparisons.
- Registration state does not always equal operational location.
- State clusters are exploratory rather than definitive categories.
- Forecasts rely on a short annual time series and should be interpreted cautiously.

---

<div align="center">

### 🚀 StartupPulse India
**From startup recognition data to actionable ecosystem insights.**

</div>
