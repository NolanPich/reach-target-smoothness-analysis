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
