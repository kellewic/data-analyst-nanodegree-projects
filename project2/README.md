# 🎬 Streaming vs Theatrical: A Data-Driven Analysis of Movie Distribution

[![Python](https://img.shields.io/badge/Python-3.14-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Status](https://img.shields.io/badge/Status-Complete-success.svg)]()

A comprehensive data wrangling and analysis project examining how streaming platforms curate theatrical movie content, revealing selective licensing strategies, quality-driven curation, and family-friendly content preferences.

## 📊 Project Overview

This project analyzes **27,000+ movies** across **65 years** (1960-2025) to answer a fundamental question about the streaming revolution:

> **How do streaming platforms compare to traditional theatrical releases in terms of financial performance, audience reception, and content characteristics?**

By integrating 6 different data sources including TMDb, IMDb, Netflix, Hulu, Disney+, Amazon Prime, and Federal Reserve economic data, this analysis reveals that streaming platforms don't simply digitize theatrical libraries—they employ curation strategies that prioritize premium, family-friendly content with proven commercial success.

### 🎯 Key Findings

| Metric             | Streaming-Available | Theatrical-Only | Difference           |
| ------------------ | ------------------- | --------------- | -------------------- |
| **Median Budget**  | $54.3M              | $39.4M          | **+38%**             |
| **Median Revenue** | $139.7M             | $72.3M          | **+93%**             |
| **Median ROI**     | 145.9%              | 94.9%           | **+54%**             |
| **Average Rating** | 6.25                | 6.09            | **+2.6%** (p<0.0001) |
| **Family Genre**   | 24.6%               | 9.3%            | **+15.3 pts**        |

**Bottom Line:** Streaming platforms cherry-pick financially successful, highly-rated, family-friendly content rather than acquiring comprehensive theatrical libraries.

---

## 📁 Repository Structure

```
/project2
├── data/
│   ├── raw/                                  # Original unmodified datasets
│   └── clean/                                # Processed analysis-ready datasets
├── data_wrangling_project_starter.ipynb      # Main analysis notebook
├── README.md                                 # This file
```

---

## 🔬 Methodology

### 1. Data Gathering

Integrated **6 diverse data sources** using multiple collection methods:

| Dataset                 | Source        | Method                | Purpose                                       |
| ----------------------- | ------------- | --------------------- | --------------------------------------------- |
| **TMDb Movies**         | Kaggle        | Manual Download       | Theatrical releases, financial data           |
| **IMDb Ratings**        | IMDb Datasets | Programmatic Download | Additional ratings, validation                |
| **Streaming Platforms** | Kaggle        | Manual Download       | Netflix, Hulu, Disney+, Amazon Prime catalogs |
| **CPI Inflation Data**  | FRED API      | API Access            | Inflation adjustment to 2024 dollars          |

### 2. Data Assessment

Identified and documented **4 critical quality and tidiness issues**:

**Quality Issues:**

- Missing IMDb IDs (8.6% of TMDb data)
- IMDb's non-standard null notation (`\N` instead of proper nulls)

**Tidiness Issues:**

- IMDb data split across two tables (title.basics + title.ratings)
- Pipe-delimited genres instead of structured format

### 3. Data Cleaning

Systematically addressed each issue with data-driven decisions:

- **Runtime reconciliation:** Validated median 0-minute difference before selecting TMDb values
- **Year validation:** Confirmed 96.8% exact match between TMDb and IMDb
- **Genre normalization:** Mapped IMDb to TMDb taxonomies, excluded TV-specific genres
- **Inflation adjustment:** Used Federal Reserve CPI data to convert all figures to 2024 dollars

**Key Transformation:**

```python
budget_2024 = budget_original × (CPI_2024 / CPI_release_year)
```

### 4. Analysis

Created 4 comprehensive multi-panel visualizations:

1. **Financial Performance Over Time** - Budget, revenue, and ROI trends by decade
2. **Audience Reception** - Rating distributions, box plots, TMDb vs IMDb correlation
3. **Genre Distribution** - Content characteristic comparison between channels
4. **Platform Strategy Matrix** - Heatmap revealing platform differentiation

### 5. Statistical Validation

Applied rigorous statistical testing:

- **T-test:** Confirmed statistically significant rating difference (t=6.459, p<0.0001)
- **Correlation:** Validated TMDb-IMDb rating agreement (r=0.845)
- **Distribution analysis:** Characterized patterns across decades

---

## 📈 Detailed Findings

### Financial Performance

Streaming platforms demonstrate clear premium content bias:

```
Streaming-Available (n=1,090):
├─ Median Budget:  $54.3M  (+38% vs theatrical-only)
├─ Median Revenue: $139.7M (+93% vs theatrical-only)
└─ Median ROI:     145.9%  (+54% vs theatrical-only)
```

**Insight:** Platforms license proven box office performers rather than acquiring comprehensive libraries. The 19% match rate (2,063 of 10,835 theatrical releases) confirms highly selective curation.

### Audience Reception

Quality-driven licensing strategy validated:

- Streaming-available movies average **6.25** rating
- Theatrical-only movies average **6.09** rating
- Difference is **highly significant** (p<0.0001, t=6.459)
- Strong rating agreement across platforms (r=0.845)

**Insight:** Platforms don't randomly select content—they actively curate for quality, licensing critically acclaimed films.

### Content Characteristics

**Family-friendly curation dominates:**

| Genre         | Streaming | Theatrical | Difference    |
| ------------- | --------- | ---------- | ------------- |
| **Family**    | 24.6%     | 9.3%       | **+15.3 pts** |
| **Adventure** | 27.6%     | 16.6%      | **+11.0 pts** |
| **Comedy**    | 43.6%     | 37.4%      | **+6.2 pts**  |
| **Animation** | 13.2%     | 7.2%       | **+6.0 pts**  |
| --------      | -----     | -----      | -----         |
| **Drama**     | 47.5%     | 53.1%      | **-5.6 pts**  |
| **Horror**    | 11.7%     | 17.3%      | **-5.6 pts**  |
| **Thriller**  | 27.0%     | 30.0%      | **-3.1 pts**  |

**Insight:** Household subscription model drives content toward broad, family-safe appeal. Platforms underrepresent darker genres (Horror, Thriller, Crime) that may deter family viewers.

### Platform Strategy Differentiation

Each platform employs **distinct competitive strategy**:

| Platform         | Size  | Strategy             | Median Age | Top Genres                   |
| ---------------- | ----- | -------------------- | ---------- | ---------------------------- |
| **Amazon Prime** | 7,814 | Volume/Breadth       | 9 years    | Drama, Comedy, Action        |
| **Netflix**      | 6,131 | International/Fresh  | 8 years    | International, Drama, Comedy |
| **Hulu**         | 1,484 | Adult/Documentary    | 7 years    | Drama, Comedy, Documentary   |
| **Disney+**      | 1,052 | Premium Family Vault | 16 years   | Family, Comedy, Animation    |

**Insight:** Platforms compete through specialization rather than duplication. Only 2.0% of streaming titles appear on multiple platforms.

---

## 🛠️ Technical Stack

### Core Technologies

- **Python 3.14** - Primary programming language
- **Jupyter Notebook** - Interactive development environment
- **pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Static visualizations
- **Seaborn** - Statistical data visualization
- **SciPy** - Statistical testing

### Data Sources

- **TMDb** - The Movie Database
- **IMDb** - Internet Movie Database (Non-Commercial Datasets)
- **FRED** - Federal Reserve Economic Data (CPI)
- **Kaggle** - Streaming platform datasets

---

## 📝 Key Insights Summary

### What This Analysis Reveals

1. **Selective Licensing, Not Wholesale Digitization**

   - Only 19% of theatrical releases (1960-2015) available on streaming
   - Platforms prioritize proven performers (38% higher budgets, 54% better ROI)

2. **Quality Curation Strategy**

   - Statistically significant rating advantage (p<0.0001)
   - Platforms actively license critically acclaimed content

3. **Family-Friendly Content Bias**

   - 15.3 percentage point increase in Family genre representation
   - Underrepresentation of Horror, Thriller, Crime genres

4. **Platform Differentiation**

   - Each service targets distinct audience segments
   - Minimal catalog overlap (2.0% multi-platform titles)

5. **Economic Validation**
   - Streaming-available content achieves 54% better ROI
   - Premium pricing justified by superior performance

### Business Implications

**For Content Creators:**

- Family-friendly content has higher streaming acquisition likelihood
- Proven box office success increases platform interest
- Quality (ratings) matters for licensing decisions

**For Streaming Platforms:**

- Current selective strategy appears economically rational
- Platform differentiation prevents direct competition
- Household subscription model drives family-safe curation

**For Investors:**

- Streaming platforms demonstrate sophisticated curation analytics
- Content acquisition costs justified by performance metrics
- Platform specialization creates sustainable competitive advantages

---

## 🎓 Methodology Highlights

### Data-Driven Decision Making

Every analytical choice was validated with empirical evidence:

**Example: Runtime Reconciliation**

```
Analysis: 80% exact matches, median difference = 0 minutes
Decision: Use TMDb runtime as primary source
Justification: Excellent agreement validates data quality
```

**Example: Year Validation**

```
Analysis: 96.8% exact matches between TMDb and IMDb
Decision: Use TMDb release_year exclusively
Justification: Theatrical focus aligns with financial analysis
```

### Statistical Rigor

- Sample sizes documented for all comparisons
- P-values reported with proper interpretation
- Correlation coefficients validated
- Distribution assumptions verified

### Professional Standards

- Raw data preserved separately from cleaned data
- All transformations documented and justified
- Reproducible workflow with clear dependencies
- Comprehensive validation after each transformation

---

## 🔮 Future Work

### Proposed Extensions

1. **Temporal Licensing Analysis**

   - Analyze `date_added` vs `release_year` lag patterns
   - Identify optimal licensing windows
   - Determine if older content faces acquisition barriers

2. **Fuzzy Matching Enhancement**

   - Implement Levenshtein distance algorithm
   - Recover 1,396 unmatched theatrical releases (12.9%)
   - Improve streaming catalog linkage accuracy

3. **Talent Analysis**

   - Integrate director and cast data
   - Determine if star power drives licensing independent of performance
   - Identify high-value talent for platform acquisition

4. **Predictive Modeling**

   - Build ML model to predict streaming acquisition likelihood
   - Features: budget, revenue, rating, genre, release year, cast
   - Use case: Guide content creators on streaming-friendly characteristics

5. **Temporal Extension**
   - Extend analysis beyond 2015 to capture streaming boom (2016-2024)
   - Examine theatrical strategy changes (shorter windows, streaming-first releases)
   - Quantify shift from licensing to original content production
