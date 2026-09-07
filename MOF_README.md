# MOFDB25 — MOF/MOF-Derived HER Electrocatalyst Database

<p align="center">
  <img src="assets/mofdb25_overview.png" alt="MOFDB25 overview" width="900">
</p>

<p align="center">
  <b>A manually curated, literature-derived database of MOF and MOF-derived electrocatalysts for the hydrogen evolution reaction (HER)</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Entries-566-2ea44f?style=flat-square">
  <img src="https://img.shields.io/badge/Features-26-0366d6?style=flat-square">
  <img src="https://img.shields.io/badge/Source-SCOPUS-6f42c1?style=flat-square">
  <img src="https://img.shields.io/badge/Application-HER%20%7C%20Machine%20Learning-f66a0a?style=flat-square">
</p>

---

## Citation

If you use MOFDB25, please cite the associated publication:

> **S. Nayak and S. Karuthapandi**, “Discerning the underlying trends in electrocatalytic hydrogen evolution activity of MOF/MOF-derived materials using data-driven approach,” *Energy and AI*, **24** (2026) 100708.  
> DOI: **10.1016/j.egyai.2026.100708**

### BibTeX

```bibtex
@article{Nayak2026MOFDB25,
  title   = {Discerning the underlying trends in electrocatalytic hydrogen evolution activity of MOF/MOF-derived materials using data-driven approach},
  author  = {Nayak, Sachidananda and Karuthapandi, Selvakumar},
  journal = {Energy and AI},
  volume  = {24},
  pages   = {100708},
  year    = {2026},
  doi     = {10.1016/j.egyai.2026.100708}
}
```
---

## Overview

**MOFDB25** is a manually curated literature-derived database developed for the systematic analysis of **MOF and MOF-derived electrocatalysts for the hydrogen evolution reaction (HER)**.

The database was constructed by systematically screening the SCOPUS literature, retrieving eligible research articles, manually extracting catalyst information from full-text articles and supplementary materials, and integrating structural, morphological, synthetic, and electrochemical descriptors into a unified dataset.

The associated study used statistical analysis and machine-learning approaches to investigate HER performance, mechanistic classification, catalyst grouping, and benchmarking against Pt/C.

> **Database status:** The present repository is intended to provide a reproducible home for the MOFDB25 dataset, documentation, and analysis resources.

---

## Key Statistics

| Parameter | MOFDB25 |
|---|---:|
| Catalyst entries | **566** |
| Curated features | **26** |
| Eligible publications after screening | **348** |
| Publications contributing catalyst entries | **144** |
| Entries after removal of missing Tafel-slope values | **517** |
| Entries used for subsequent unsupervised ML analysis | **340** |
| Promising entries identified through iterative clustering | **62** |
| High-performing entries identified against Pt/C benchmark | **10** |

The 26 features comprise **16 electrochemical**, **4 morphological**, and **6 synthetic** descriptors.

---

## Feature Categories

### 1. Electrochemical features — 16

- Current Density
- Overpotential (OP)
- Tafel Slope (TS)
- Kinetics Mechanism
- Exchange Current Density (ECD)
- Onset Potential
- Electrochemical Medium
- Acidic/Alkaline classification
- Encoded Medium
- Charge Transfer Resistance (Rct)
- Solution Resistance (Rs)
- Double-Layer Capacitance (Cdl)
- Electrochemical Surface Area (ECSA)
- Additives
- Nafion
- Mass Loading

### 2. Morphological / surface features — 4

- BET Surface Area
- Pore Size
- Pore Volume
- Graphitization Index (ID/IG)

### 3. Synthetic / compositional features — 6

- Synthesis Method
- Precursor Reagents
- Precursor Solvents
- MOF Used
- MOF Metal
- TM-O/S/N/C/P/Cl-related descriptor

---

## Literature Screening

The literature search and screening workflow followed a defined sequence:

1. SCOPUS advanced search
2. Initial retrieval of **417 publications**
3. Publication period restricted to **2015–2025**
4. Exclusion of **53 reviews, 9 book chapters, and 1 short survey**
5. Exclusion of **6 non-English articles**
6. **348 eligible publications** remained
7. Full-text articles and supplementary information were examined where accessible
8. Catalyst-level information was manually extracted
9. Data were integrated into the MOFDB25 database

### Publication screening workflow

<p align="center">
  <img src="assets/publication_screening.png" alt="MOFDB25 publication screening workflow" width="850">
</p>

---

## Database Construction

The database integrates information from three major descriptor groups:

**Synthetic descriptors → Surface/morphological descriptors → Electrochemical descriptors**

The information was manually extracted from research articles and supplementary materials and subsequently cleaned, standardized, reviewed, and integrated into a unified database.

<p align="center">
  <img src="assets/database_workflow.png" alt="MOFDB25 database construction workflow" width="950">
</p>

---

## Data Curation and Pre-processing

The reported workflow included:

- Manual extraction from published literature and supplementary information
- Removal of unnecessary spreadsheet columns
- Removal of extraneous characters introduced during data extraction
- Multiple rounds of cross-checking
- Standardization of numerical variables and units
- Identification of numerical and categorical variables
- Categorical encoding for machine-learning analysis
- Removal of entries with missing Tafel-slope values for analyses requiring complete TS data

The original study reports that the curated entries were inspected and cross-verified multiple times, typically over three rounds.

---

## Machine-Learning Framework

MOFDB25 was designed to support both statistical and machine-learning analysis.

### Supervised learning

The study evaluated:

- Decision Tree (DT)
- Support Vector Machine (SVM)
- Naive Bayes (NB)

These models were used for classification of:

- HER mechanistic categories
- Low- vs high-overpotential categories
- Overall catalyst performance categories

### Semi-supervised analysis

- Principal Component Analysis (PCA)
- Structural classification using 0D, 1D, 2D and 3D categories

### Unsupervised learning

- PCA for dimensionality reduction and feature interpretation
- K-Means clustering for catalyst grouping and performance-oriented filtering

The K-Means analysis identified a **62-entry cluster** characterized by comparatively favorable OP and TS values. A subsequent clustering analysis was performed on these entries to further identify high-performing catalyst groups.

---

## Machine-Learning Workflow

```text
Literature Retrieval
        │
        ▼
Publication Screening
        │
        ▼
Full-Text & SI Extraction
        │
        ▼
Catalyst-Level Database
        │
        ▼
Data Cleaning & Standardization
        │
        ▼
Exploratory / Inferential Statistics
        │
        ├───────────────┐
        ▼               ▼
 Supervised ML       PCA
        │               │
        │               ▼
        │            K-Means
        │               │
        └───────┬───────┘
                ▼
      Catalyst Benchmarking
                │
                ▼
       High-Performance HER
            Candidates
```

---

## Graphical Abstract

The original study summarizes the database and data-driven workflow as follows:

<p align="center">
  <img src="assets/graphical_abstract.png" alt="MOFDB25 graphical abstract" width="1000">
</p>

---

## Intended Applications

MOFDB25 can serve as a starting point for:

- Exploratory data analysis of MOF-based HER catalysis
- Statistical analysis of reported HER performance
- Structure–performance relationship studies
- Mechanistic classification
- Catalyst benchmarking
- Unsupervised clustering
- Feature-selection studies
- Supervised machine-learning classification
- Development of future predictive models
- Integration with computational/DFT descriptors
- Expansion into larger literature-derived catalyst databases

---

## Recommended Data Organization

For reproducible research, a future expanded version of the repository can be organized as:

```text
MOFDB25/
│
├── README.md
├── LICENSE
├── CITATION.cff
│
├── data/
│   ├── MOFDB25.csv
│   ├── MOFDB25.xlsx
│   └── data_dictionary.csv
│
├── analysis/
│   ├── EDA/
│   ├── PCA/
│   ├── clustering/
│   └── supervised_ML/
│
├── figures/
│   ├── graphical_abstract.png
│   ├── publication_screening.png
│   ├── database_workflow.png
│   └── ...
│
└── docs/
    ├── data_dictionary.md
    ├── methodology.md
    └── changelog.md
```

### Important recommendation

Each catalyst should ideally have a **unique Catalyst_ID**, and every catalyst should be linked to a **Paper_ID/Publication_ID**.

This is especially important for machine-learning validation because multiple catalyst entries can originate from the same publication.

---

## Data Dictionary

A detailed data dictionary should accompany the database and define:

- Feature name
- Description
- Data type
- Unit
- Allowed categories
- Original reported value
- Standardized value
- Missing-value convention
- Source publication
- DOI
- Figure/Table/Supplementary-information location where applicable

Example:

| Field | Description | Type | Unit |
|---|---|---|---|
| Catalyst_ID | Unique catalyst identifier | ID | — |
| Paper_ID | Source publication identifier | ID | — |
| Overpotential | Reported HER overpotential | Numerical | mV |
| Tafel_Slope | Reported Tafel slope | Numerical | mV dec⁻¹ |
| Current_Density | Current density at which OP is reported | Numerical | mA cm⁻² |
| Rct | Charge-transfer resistance | Numerical | Ω |
| BET | BET surface area | Numerical | m² g⁻¹ |
| Pore_Size | Reported pore size | Numerical | article-reported/standardized |
| Synthesis_Method | Catalyst synthesis route | Categorical | — |
| MOF_Metal | Metal associated with MOF | Categorical | — |
| Electrochemical_Medium | HER electrolyte/medium | Categorical | — |

---

## Missing Data

Missing values in the literature-derived database should **not automatically be interpreted as zero**.

Recommended conventions:

- `NR` — Not Reported
- `NA` — Not Applicable
- `ND` — Not Determined

For machine-learning workflows, missing-value handling should be performed during preprocessing and documented separately from the raw curated database.

---

## Reproducibility

When using MOFDB25 for machine learning, users are encouraged to document:

1. Dataset version
2. Feature-selection procedure
3. Missing-value treatment
4. Encoding method
5. Scaling/standardization procedure
6. Train/test splitting strategy
7. Cross-validation strategy
8. Model hyperparameters
9. Random seed
10. Evaluation metrics
11. Excluded entries
12. Any newly added literature records

For literature-derived catalyst data, **grouped validation by publication** should be considered when appropriate, because multiple catalyst entries can originate from the same article.

---

## Limitations

MOFDB25 is a literature-derived dataset and therefore inherits limitations associated with published experimental data.

The original study identifies several important limitations:

- Restriction to the SCOPUS database
- Defined publication period of 2015–2025
- Limited access to some paywalled articles
- Uneven reporting of electrochemical descriptors
- Missing Rct, Cdl, ECSA and ECD values for many entries
- Potential selection bias
- Limited electronic and topological structural information
- Some catalyst entries may represent the same catalyst under different experimental conditions

These limitations should be considered when interpreting statistical or machine-learning results.

---

## Dataset Versioning

Suggested versioning:

```text
MOFDB25 v1.0
```

Future releases can use:

```text
v1.1  → corrections / additional records
v1.2  → additional descriptors
v2.0  → major database expansion or schema change
```

A `CHANGELOG.md` should document every modification.

---

## Citation

If you use MOFDB25, please cite the associated publication:

> **S. Nayak and S. Karuthapandi**, “Discerning the underlying trends in electrocatalytic hydrogen evolution activity of MOF/MOF-derived materials using data-driven approach,” *Energy and AI*, **24** (2026) 100708.  
> DOI: **10.1016/j.egyai.2026.100708**

### BibTeX

```bibtex
@article{Nayak2026MOFDB25,
  title   = {Discerning the underlying trends in electrocatalytic hydrogen evolution activity of MOF/MOF-derived materials using data-driven approach},
  author  = {Nayak, Sachidananda and Karuthapandi, Selvakumar},
  journal = {Energy and AI},
  volume  = {24},
  pages   = {100708},
  year    = {2026},
  doi     = {10.1016/j.egyai.2026.100708}
}
```

---

## Authors

**Sachidananda Nayak**  
Department of Chemistry, School of Advanced Sciences  
VIT-AP University, Amaravati, Andhra Pradesh, India

Author: `sachidanandanitr@gmail.com`

**Selvakumar Karuthapandi**  
Department of Chemistry, School of Advanced Sciences  
VIT-AP University, Amaravati, Andhra Pradesh, India

Corresponding author: `selvakumar.k@vitap.ac.in`

---

## License and Reuse

The associated article is published under a **CC BY-NC-ND** license.

The license of the **database files released in this repository should be explicitly specified by the repository authors**. Do not assume that the article's license automatically defines the license of newly released dataset files.

For article-derived figures included in this repository, retain the original attribution and licensing information.

---

## Disclaimer

MOFDB25 is a literature-derived research database. Reported experimental values reflect the conditions and characterization methods used by the original authors. Differences in electrolyte, reference electrode, catalyst loading, substrate, measurement protocol, iR correction, scan rate, and other experimental conditions can affect apparent HER performance.

The database should therefore be used as a **research and data-analysis resource**, not as a direct replacement for experimental validation.

---
---

<p align="center">
  <b>MOFDB25</b><br>
  Data-driven exploration of MOF/MOF-derived electrocatalysts for hydrogen evolution
</p>
