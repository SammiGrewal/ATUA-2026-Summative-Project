# ATUA-2026-Summative-Project

# Climate Risk & Housing Valuations in London

**Advanced Topics for Urban Analytics — MSc Urban Analytics, University of Glasgow**
**Submitted: May 2026**

---

## Project Overview

This project investigates whether climate change risks — specifically surface water flood exposure and heat — are reflected in residential property price appreciation across London's Lower Layer Super Output Areas (LSOAs) between 1995 and 2024.

Using a repeat-sales methodology, the median log price change per LSOA is modelled against climate risk indicators, socio-economic characteristics, and property features. The analysis progresses from standard Ordinary Least Squares (OLS) regression through global spatial models, and local spatial models (GWR and mGWR).

---

## Research Questions

1. Do flood-prone and heat-exposed LSOAs in London experience systematically lower rates of residential property price appreciation between 1995 and 2024?
2. Does this relationship vary spatially across the city, and if so, how?

---

## Data

Three datasets are used in this analysis:

| Dataset | Source | Description |
|---|---|---|
| House Price Per Square Metre | Land Registry / Bin et al. (2025) | Residential property transactions across Greater London, 1995–2024 |
| London Climate Risk Maps | Greater London Authority (GLA, 2024) | LSOA-level climate risk indicators including surface water flood risk, summer temperature, air quality, and socio-economic deprivation |
| Postcode to LSOA Lookup | ONS (2025) | Links transaction postcodes to 2021 LSOA boundaries |

A DuckDB spatial database is used to manage the large transactions dataset.

> **Note on data availability:** The Land Registry transactions dataset exceeds 21 GB and cannot be uploaded to GitHub. The GLA climate risk GeoJSON and postcode lookup CSV are similarly excluded due to file size constraints. The processed project database (`project.db`) is also excluded. To replicate this analysis, these files must be sourced independently and placed in the `Data/raw_data/` directory.

---

## Key Findings

**mGWR is the preferred model**, achieving the lowest AICc (−12,297), a higher adjusted R² (0.263) than GWR, and residuals showing minimised spatial autocorrelation (Moran's I = −0.002, p = 0.456).

- **Flood risk is partially capitalised into housing markets.** mGWR identifies a significant negative relationship between surface water flood risk and property price appreciation in specific parts of London. This effect is absent in global models (OLS, SEM), underscoring the importance of spatially varying specifications.
- **Heat risk is not yet capitalised.** Neither GWR nor MGWR find significant coefficients for heat risk across London LSOAs. Heat risk does not currently appear to be reflected in residential property price dynamics in London.

---

## Repository Structure

```
ATUA-2026-Summative-Project/
├── summative_proj.ipynb
├── WordCount.ipynb 
├── Data/
│   └── raw_data/
├── project.db
└── README.md
└── requirements.txt
└── URBAN5160_3028045G.html
```


