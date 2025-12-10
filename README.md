# Hospital Billing Variation: Understanding What Drives Differences in Inpatient Charges

This repository contains the final project for DATA 512 A (Human Centered Data Science, Autumn 2025). The project uses de-identified inpatient discharge data from New York State to explore why hospital charges vary so much, even for patients who appear similar on paper.

## Overview

The analysis focuses on how total hospital charges relate to:

- Length of stay  
- Severity of illness  
- Type of admission (e.g., emergency vs. elective)  
- Primary payer (insurance category)

The goal is descriptive, not predictive: to understand patterns in billing and reflect on who pays more and why, from a human-centered perspective.

## Data

- **Source:** New York State Department of Health, SPARCS (Statewide Planning and Research Cooperative System)  
- **Dataset:** *Hospital Inpatient Discharges (SPARCS De-Identified), 2021* (via Health Data NY portal)  
- **License/Terms:** Public open data under the Open NY Terms of Use, used here for non-commercial, educational purposes only.

Required attribution statement:  
> The New York State Department of Health makes no representation, warranty or guarantee relating to the data or analyses derived from these data.

All analyses and any errors are my own, not the Department’s.

## Research Question

> How do length of stay, severity of illness, type of admission, and primary payer relate to total hospital charges, and which of these factors appear to drive the largest differences in cost?

## Methods & Key Findings

Methods (in the notebook):

- Load and clean SPARCS inpatient data (e.g., convert “Total Charges” and “Length of Stay” to numeric).
- Descriptive analysis of average charges by length of stay.
- Multiple regression of total charges on length of stay, age group, severity, and admission type.
- ANOVA to compare charges across severity-of-illness categories.
- Visualizations (e.g., boxplots) to compare charges by payer type for clinically similar patients.

Key findings:

- Charges increase sharply with length of stay, especially in the first few days.  
- Higher severity is strongly associated with higher charges.  
- Even after accounting for severity and length of stay, large differences remain across payer types and hospitals, suggesting a strong role for administrative and financial factors.

## How to Run

1. Use Python 3 and install: `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`.  
2. Download the SPARCS dataset and place it in the same folder as the notebook (or a `data/` subfolder).  
3. Update the `pd.read_csv(...)` path in the notebook if needed.  
4. Open the notebook in Jupyter and run cells from top to bottom. Each code cell is preceded by a Markdown explanation.

## Human-Centered & Ethical Perspective

The notebook includes reflections on:

- Fairness implications of cost differences that remain after controlling for clinical factors.  
- Limited control patients have over factors like insurance contracts or emergency admissions.  
- Limits of administrative data (charges ≠ necessarily quality or quantity of care).

The analysis is intentionally descriptive and cautious about overinterpreting differences between hospitals or clinicians.

## References (Brief)

- New York State SPARCS documentation (Health Data NY).  
- Kaiser Family Foundation (KFF) work on hospital pricing and surprise billing.  
- Investigative reporting (e.g., The New York Times) on hospital price variation.  
- Health policy research (e.g., in *Health Affairs*) on drivers of hospital prices.
