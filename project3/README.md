# 📊 Project 3: The Streaming Era Divide - Data Visualization

[![Python](https://img.shields.io/badge/Python-3.14-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Status](https://img.shields.io/badge/Status-Complete-success.svg)]()

A comprehensive data visualization project examining how streaming platforms strategically curate theatrical movie content. This project transforms the data wrangling findings from Project 2 into polished exploratory and explanatory visualizations that reveal the business strategies behind streaming catalog curation.

## 🎯 Project Overview

**Research Question:** Do streaming platforms license random theatrical releases, or do they strategically curate specific types of content?

**Answer:** Streaming platforms operate with deliberate, sophisticated curation strategies that maximize profitability while minimizing risk. They don't rescue theatrical failures—they license proven winners and specialize by content type to reduce subscriber churn.

---

## 📁 Repository Structure

```
project3/
├── Part_I_exploration_template.ipynb    # Exploratory data analysis (EDA)
├── Part_I_exploration_template.html     # EDA notebook export
├── Part_II_explanatory_template.ipynb   # Explanatory presentation
├── Part_II_explanatory_template.html    # Presentation export
├── data/
│   ├── imdb_tmdb_theatrical_movies_merged_clean.csv
│   └── streaming_movies_merged_clean.csv
└── README.md
```

---

## 📊 Dataset Overview

| Dataset               | Records       | Description                                                            |
| --------------------- | ------------- | ---------------------------------------------------------------------- |
| **Theatrical Movies** | 10,835 films  | TMDb + IMDb merged data (1960-2015) with inflation-adjusted financials |
| **Streaming Catalog** | 16,481 titles | Netflix, Hulu, Disney+, and Amazon Prime catalogs                      |

**Key Variables:**

- Financial metrics: `budget_adj_2024`, `revenue_adj_2024`, `roi`
- Ratings: `tmdb_rating`, `imdb_rating`, `rating_combined`
- Platform flags: `on_netflix`, `on_hulu`, `on_disney`, `on_amazon`, `on_streaming`
- Metadata: `genres`, `runtime`, `release_year`

---

## 🔍 Part I: Exploratory Analysis

The exploratory analysis investigates distributions and relationships to understand patterns in streaming curation.

### Univariate Exploration

- **Release Year Distribution:** Identified extreme recency bias in streaming catalogs
- **Platform Catalog Sizes:** Compared Netflix, Amazon Prime, Hulu, and Disney+ offerings
- **Multi-Platform Availability:** Analyzed exclusivity patterns (93.5% single-platform)

### Bivariate Exploration

- **Financial Performance:** Compared ROI, budget, and revenue between streaming and theatrical-only releases
- **Ratings Comparison:** Analyzed quality differences using TMDb and IMDb ratings
- **Genre Analysis:** Examined genre representation across streaming platforms

### Multivariate Exploration

- **Budget-Revenue-Streaming:** Explored how financial performance relates to streaming availability
- **Temporal-Financial Patterns:** Investigated decade-by-decade profitability trends
- **Platform Genre Specialization:** Mapped genre preferences across platforms

---

## 🎨 Part II: Explanatory Analysis

The explanatory analysis presents three polished visualizations that communicate key findings to a non-technical audience.

### Visualization 1: The Recency Bias

**Stacked Histogram: Streaming vs Theatrical-Only by Release Year**

**Key Insight:** Streaming catalogs overwhelmingly favor recent releases:

- **72%** of streaming content comes from the 2000s-2010s
- Only **12%** of pre-1990 films appear on streaming
- Streaming penetration doubled from ~12% (1980s) to 22% (2010-2015)

### Visualization 2: The Winner's Circle

**Box Plot: ROI Distribution Comparison**

**Key Insight:** Streaming platforms systematically select profitable movies:

- **51-point** higher median ROI (145.9% vs 94.9%)
- **42% lower** failure rate (18.2% vs 31.6% losing money)
- 75% of streaming movies are profitable (25th percentile = +30.5%)

### Visualization 3: Platform Personalities

**Heatmap: Genre Specialization Across Platforms**

**Key Insight:** Platforms differentiate through genre curation:

- **Disney+:** 24.5% Family content (10x competitors)
- **Netflix:** Volume leader with 40-52% market share across genres
- **Hulu:** Thriller/Action niche (14.5% thriller focus)
- **Amazon Prime:** Drama aggregator mimicking Netflix at smaller scale

---

## 📈 Key Findings

### 1. Extreme Recency Bias (Temporal Strategy)

| Decade  | Streaming % | Films on Streaming |
| ------- | ----------- | ------------------ |
| 1960s   | 11.9%       | 43                 |
| 1970s   | 14.4%       | 73                 |
| 1980s   | 12.3%       | 131                |
| 1990s   | 18.0%       | 318                |
| 2000s   | 19.6%       | 696                |
| 2010-15 | 22.3%       | 802                |

**Implication:** Streaming has not democratized access to cinema history—it concentrates viewing around contemporary releases.

### 2. Financial Cherry-Picking (Risk Management Strategy)

| Metric              | Streaming | Theatrical-Only | Advantage |
| ------------------- | --------- | --------------- | --------- |
| Median ROI          | 145.9%    | 94.9%           | +51 pts   |
| Loss Rate           | 18.2%     | 31.6%           | -13.4 pts |
| 25th Percentile ROI | +30.5%    | -24.2%          | +54.7 pts |

**Implication:** Studios bear 100% of production risk while streaming platforms cherry-pick winners at known prices.

### 3. Strategic Genre Specialization (Competitive Differentiation)

| Platform     | Top Genre      | % of Catalog | Strategy                    |
| ------------ | -------------- | ------------ | --------------------------- |
| Disney+      | Family         | 24.5%        | Vertical integration moat   |
| Netflix      | Drama          | 19.2%        | Horizontal volume dominance |
| Hulu         | Drama/Thriller | 17.6%/14.5%  | Adult-focused niche         |
| Amazon Prime | Drama          | 19.9%        | Fast-follower strategy      |

**Implication:** Platforms compete through specialization, not imitation.

---

## 🎓 Visualization Design Principles

This project demonstrates professional data visualization techniques:

### Design Choices

1. **Color Consistency:** Netflix red (#E50914), theatrical gray (#808080), platform-specific colors
2. **Annotation Strategy:** Key statistics highlighted with text boxes and arrows
3. **Clean Formatting:** Whitegrid style, bold titles, clear axis labels
4. **Statistical Context:** Verification statistics printed alongside visualizations

### Visualization Types Used

- **Histograms:** Temporal distributions
- **Box Plots:** Distribution comparisons with outlier handling
- **Heatmaps:** Multi-dimensional categorical relationships
- **Stacked Bar Charts:** Composition analysis
- **Scatter Plots:** Bivariate relationships

---

## 💡 Industry Implications

### For Consumers

- **Fragmented access:** 93.5% exclusivity rate requires multiple subscriptions
- **Recency bias:** Classic cinema (pre-1990) is dramatically under-represented
- **Predictable curation:** Catalogs favor commercially successful mid-budget films

### For Content Creators

- **Hindsight disadvantage:** Streaming licenses after theatrical risk-taking
- **Genre pressure:** Platform specialization influences greenlight decisions
- **Winner-take-all dynamics:** Netflix and Disney dominate their niches

### For the Industry

- **Theatrical as proving ground:** Box office determines streaming value
- **Licensing concentration:** Fierce competition for differentiated content
- **Risk calculus shift:** Theatrical ROI must factor in streaming potential

---

## ⚠️ Limitations

1. **Temporal cutoff:** Dataset ends in 2015; streaming strategies have evolved significantly
2. **Missing variables:** Licensing costs and viewership data unavailable
3. **Survivor bias:** Older decades' streaming catalogs over-represent classics
4. **Platform evolution:** COVID-19 dramatically altered streaming dynamics post-2020

---

## 🛠️ Technical Stack

- **Python 3.14** - Primary programming language
- **pandas** - Data manipulation
- **NumPy** - Numerical computing
- **Matplotlib** - Base visualization library
- **Seaborn** - Statistical visualization
- **Jupyter Notebook** - Interactive development

---

## 🔗 Related Projects

- **[Project 2: Data Wrangling](../project2/)** - Data preparation and cleaning that produced the datasets used in this analysis
- **[Project 1: Investigate a Dataset](../project1/)** - Initial exploration of movie success factors

---

## 📝 Conclusions

**Streaming platforms are not passive distributors—they are strategic curators.**

By concentrating on recent releases (72% from 2000s-2010s), licensing profitable winners (51-point ROI advantage), and differentiating through genre specialization (Disney's family monopoly, Netflix's volume dominance), platforms minimize risk while maximizing subscriber retention.

The romantic notion that streaming "rescues" underappreciated films is fiction—these platforms systematically select proven theatrical successes, leaving failures and classics behind.

**The algorithm doesn't just learn what you like—it learns what platforms can profitably license.**
