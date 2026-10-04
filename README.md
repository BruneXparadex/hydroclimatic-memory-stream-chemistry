# Hydroclimatic memory in stream chemistry

Reproducibility package for the manuscript **“Hydroclimatic memory in stream chemistry persists beyond discharge and varies with catchment organization.”**

## Overview

This repository contains the frozen analysis-ready data, a portable Jupyter notebook, and the manuscript-facing inferential products used to evaluate whether antecedent hydroclimate retains predictive information about stream chemistry beyond contemporaneous discharge and whether that signal varies with catchment organization.

The study uses repeated sampling across a tropical Andean headwater drainage network in Huanta, Peru. The analysis evaluates 29 pre-specified antecedent hydroclimate windows across 10 response variables using Bayesian hierarchical models and leave-one-campaign-out (LOCO) validation.

## Repository structure

```text
.
├── data/
│   └── processed/        Frozen analysis inputs
├── results/
│   ├── main/             Main manuscript result tables
│   └── supplementary/    LOCO and computational-QA tables
├── figures/              Final manuscript-facing figures
├── hydroclimatic_memory_reproducibility.ipynb
├── requirements.txt
├── CITATION.cff
└── LICENSE
```

## Reproducibility entry point

Open `hydroclimatic_memory_reproducibility.ipynb` from the repository root. The notebook uses only repository-relative paths and does not require Google Drive, Colab-specific directories, or private raw workbooks.

Install the lightweight public environment with:

```bash
python -m pip install -r requirements.txt
```

The notebook audits the frozen inputs, monitoring architecture, response panel, antecedent-window design, hydrometry and censoring policy; then loads the exact frozen inferential/LOCO products used for manuscript closure and displays the final result tables and figures.

## Analysis design

The hydroclimatic-memory analysis considered 29 pre-specified windows:

- precipitation: 1, 3, 7, 14, 30, 60 and 90 d;
- surface soil moisture: 1, 7, 14, 30, 60 and 90 d;
- root-zone soil moisture: 1, 7, 14, 30, 60 and 90 d;
- air temperature: 7, 14, 30, 60 and 90 d;
- potential evaporation: 7, 14, 30, 60 and 90 d.

LOCO validation withholds entire sampling campaigns to avoid event-scale temporal/hydroclimatic leakage.

Strict hydrochemical memory requires a longer-than-1-d antecedent window to show both directional posterior support and predictive improvement relative to the 1-d reference under the frozen decision rule.

## Interpretation boundaries

The preferred antecedent window is a predictive memory scale, not a direct residence-time estimate. Hydroclimatic forcing is defined at the shared event-date reference-domain scale rather than as station-specific upstream forcing. Contributing area is a structural proxy and should not be interpreted as direct proof of a causal connectivity or mixing mechanism.

## Data provenance

The files under `data/processed/` are frozen analysis-ready products derived from field monitoring, laboratory analyses, hydrometry, CHIRPS precipitation, ERA5-Land hydroclimate and terrain/network attributes. Raw laboratory workbooks, internal restart/checkpoint files and development-only audit artifacts are intentionally excluded from the public repository.

## Citation

Citation metadata are provided in `CITATION.cff`. After the first GitHub release is archived, the archival DOI can be added to this README and to the manuscript's Code Availability statement.

## License

Code is released under the MIT License.
