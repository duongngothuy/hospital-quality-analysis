# Hospital Quality & Patient Outcomes Analysis

An independent data analysis project examining what drives hospital quality ratings across the United States, using publicly available data from the Centers for Medicare & Medicaid Services (CMS).

**Note**: Raw data files are not included in this repository. All datasets can be downloaded directly from the CMS Provider Data Catalog under Hospital General Information, Complications & Deaths, and Unplanned Hospital Visits (Hospital-level CSVs).

---

## Project Overview

**Business Question:** What hospital characteristics — including ownership type, location, and clinical performance — are most strongly associated with higher overall star ratings?

**Role:** Independent Data Analyst  
**Tools:** Python, pandas, matplotlib, seaborn  
**Data Source:** [CMS Provider Data Catalog](https://data.cms.gov/provider-data/topics/hospitals)  
**Date:** February 2026

---

## Datasets Used

| Dataset | Rows | Description |
|---|---|---|
| Hospital General Information | 5,422 | Star ratings, ownership type, location |
| Complications & Deaths | 95,821 | Hospital-level complication and mortality scores |
| Unplanned Hospital Visits | 67,075 | Readmission and unplanned visit scores |

All datasets are hospital-level CSVs downloaded from the CMS Provider Data Catalog.

---

## Key Findings

### 1. Most Hospitals Are Average
The majority of rated hospitals (~950) score 3 stars. Truly top-performing (5-star) and critically underperforming (1-star) hospitals are rare, with ~300 and ~230 hospitals respectively.

### 2. Ownership Type Strongly Predicts Quality
- **Veterans Health Administration** hospitals lead at **4.2 avg stars**
- **For-profit (Proprietary)** hospitals score lowest at **2.6 avg stars**
- Non-profit hospitals consistently outperform government and for-profit counterparts

### 3. Geography Matters
- **Top states:** Utah, South Dakota, Colorado (~4.0+ stars)
- **Bottom states:** Mississippi, Alabama, Arkansas (~2.5 stars)
- California scores near the national average (~3.0) despite being the largest healthcare market

### 4. Mortality Is the Strongest Differentiator
5-star hospitals average ~1.0 mortality measures rated "Better than National" vs. just 0.1 for 1-star hospitals — the clearest signal separating top and bottom performers.

### 5. Readmissions Drive Overall Ratings
1-star hospitals average 1.4 readmission measures rated "Worse than National" vs. 0.25 for 5-star hospitals — a 5x difference.

---

## Methodology

```python
# Tools & Libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Steps
1. Data loading & initial exploration
2. Data cleaning (null handling, type conversion, footnote removal)
3. Dataset merging on Facility ID
4. Exploratory Data Analysis (EDA)
5. Visualization & insight generation
6. Stakeholder report writing
```

**Key cleaning decisions:**
- Replaced `"Not Available"` and `"Not Applicable"` with `NaN`
- Dropped 2,553 hospitals without an overall star rating for rating-based analysis
- Removed duplicate location columns produced by the merge

---

## Limitations

- 47% of hospitals lack an overall star rating and were excluded from rating analysis
- High rates of missing scores in complications (46%) and unplanned visits (47%) reflect non-reporting hospitals
- Cross-sectional analysis — does not capture year-over-year trends

---

## Recommendations

1. **Target for-profit hospitals** for quality improvement audits — they consistently underperform
2. **Invest in readmission reduction programs** for 1-2 star hospitals (discharge planning, care coordination)
3. **Address Southern state disparities** through regional funding and workforce initiatives
4. **Expand CMS star rating coverage** to the 47% of hospitals currently unrated

---

## Full Report

The complete stakeholder report (including all charts and executive summary) is available in the `/report` folder.

---

## About

This project was completed as part of an independent data analysis portfolio focused on healthcare analytics. Built to demonstrate end-to-end data analyst skills: data sourcing, cleaning, EDA, visualization, and stakeholder communication.

**Connect:** [LinkedIn](#) | [Portfolio](#)
