# Project Overview

This repository contains the code implementation for analyzing movement smoothness during human reach-to-target tasks. It includes data processing and quantitative analysis tools designed to measure kinematic parameters and evaluate motor control performance.

## Workflow

```
/data (raw .dat files)
       │
       ▼
00_test.ipynb          ← optional single-subject validation
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
## Workflow

| Step | File | Description | Output |
|------|------|-------------|--------|
| 00 *(optional)* | `00_test.ipynb` | Single-subject validation | — |
| 01 | `01_pipeline_traitement.ipynb` | Batch processing of all subjects | `exports/*.csv` |
| 02 | `02_statistical_analysis.Rmd` | Statistical analysis & visualization | HTML report |

> Place raw `.dat` files in `/data` before running step 01.
