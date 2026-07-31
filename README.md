# Project Overview

This repository contains the code developed for an internship project at the EuroMov Digital Health in Motion laboratory, focused on analyzing movement smoothness during human reach-to-target tasks in post-stroke patients.

It provides data processing and quantitative analysis tools to extract kinematic parameters and evaluate motor control performance.

The full internship report is available [here](https://github.com/NolanPich/Code_Project_Internship.git).

---

## Project Overview

This project analyzes kinematic data from reach-to-target tasks performed by three participant groups:
- **Young Control** — healthy young adults
- **Aged Control** — Age-matched older adults  
- **Stroke Paretic** — individuals post-stroke

Movement smoothness is quantified using:
- **SPARC** (Spectral Arc Length) — measures spectral properties of velocity profiles

---

## Repository Contents

### Notebook 1: `01_pipeline_traitement.ipynb` (Data Processing Pipeline)

**Role:** Raw data ingestion, processing, and metric computation.

This Python notebook:
- Loads raw kinematic recordings (`.dat` files) from all three participant groups
- Parses filenames to extract metadata (subject ID, group, trial number)
- **Segments** data into individual reach-to-target trials
- Computes **kinematic variables**: velocity, acceleration
- Detects **submovements** via velocity threshold and local extrema
- Calculates **smoothness metrics**: SPARC score
- Exports two structured CSV files for downstream analysis:
  - `metrics_smoothness_export.csv` — one row per movement segment (aggregated metrics)
  - `trajectories_export.csv` — one row per time point (detailed kinematic profiles)


### Notebook 2: `02_statistical_analysis.Rmd` (Statistical Analysis & Visualization)

**Role:** Kinematic visualization, descriptive statistics, and inter-group comparison.

This R Markdown notebook:
- Reads the clean CSV exports produced by `01_pipeline_traitement.ipynb`
- Computes **descriptive statistics** at segment, subject, and group level (two-stage aggregation)
- Generates **visualization plots**:
  - Spatial trajectory plots (first 10 segments per group, cross-subject overlay)
  - Velocity profiles with a shared time axis (parameterized by subject and segment)
  - SPARC distribution by group (dedicated figure)
  - Multi-metric boxplots (SPARC, mean velocity, peak velocity, duration, submovements)
  - Summary statistics table (Median [Q1 – Q3] per group)
- Produces a comprehensive **HTML report** with folded code, floating table of contents, and integrated results


---

## Workflow

```
/data (raw .dat files)
       │
       ▼
00_test.ipynb          ← SPARC implementation test (single subject)
       │
       ▼
01_pipeline_traitement.ipynb
       │
       ├──→ exports/metrics_smoothness_export.csv
       └──→ exports/trajectories_export.csv
                │
                ▼
       02_statistical_analysis.Rmd
                │
                └──→ HTML report
```

---

## Author

**Pichenot Nolan**  
Laboratory: EuroMov Digital Health in Motion
