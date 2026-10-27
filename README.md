# Calibrating self-reported BMI in national surveillance — analysis code

Code for the paper *Calibrating self-reported BMI in national surveillance: impact on obesity misclassification, socioeconomic inequalities and associations with health in Portugal* (IAN-AF 2015–2016).

## Contents

- `analysis.qmd` — Quarto document with all analyses: data preparation, misreporting determinants, calibration equations and their internal validation, obesity prevalence and agreement, socioeconomic inequalities, associations with health indicators, multiple imputation and sensitivity analyses.

## Data

The IAN-AF 2015–2016 individual data are not included. They can be requested from the IAN-AF consortium: https://www.ian-af.up.pt/en/

Place the adult analytic file at `data/ianaf_adults.csv` (or set the environment variable `PAPER5_DATA` to its path).

## Running

Requires R (≥ 4.4) and Quarto. Packages: dplyr, tidyr, survey, svyVGAM, mice, ggplot2, patchwork, flextable, officer (installed automatically if missing).

```bash
quarto render analysis.qmd
# sensitivity analysis with education in the calibration equations
PAPER5_EDU=1 PAPER5_OUT=outputs_with_edu quarto render analysis.qmd
```

Results are written to `outputs/`. The rendered HTML shows the code and all outputs.
