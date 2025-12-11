# 📊 Data Analyst Nanodegree Projects

[![Python](https://img.shields.io/badge/Python-3.14-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Status](https://img.shields.io/badge/Status-Complete-success.svg)]()

A collection of comprehensive data analysis projects exploring movie industry dynamics, financial performance, and distribution strategies. These projects demonstrate proficiency in data wrangling, exploratory data analysis, statistical testing, and data visualization.

## 🎯 Repository Overview

This repository contains three major data analysis projects that examine different aspects of the film industry:

1. **Project 1: Investigate a Dataset** - Analyzes factors associated with movie financial success and audience reception
2. **Project 2: Data Wrangling** - Examines how streaming platforms curate theatrical movie content
3. **Project 3: Data Visualization** - Transforms streaming curation findings into polished explanatory visualizations

All projects follow rigorous data science methodologies, including systematic data assessment, cleaning, exploratory analysis, and statistical validation.

---

## 📁 Projects

### 🎬 [Project 1: Investigate a Dataset - TMDb Movie Data Analysis](./project1/)

**Focus:** Understanding what factors drive commercial success in the film industry

**Dataset:** 10,866 movies from TMDb (1960-2015)

**Key Questions:**

- How does budget relate to revenue?
- Is there a relationship between critical reception and commercial success?
- Do certain genres perform better financially or critically?
- What are the characteristics of the most successful movies?

**Key Findings:**

- Budget-revenue correlation: **r = 0.567** (moderate positive relationship)
- Rating-revenue correlation: **r = 0.240** (weak relationship)
- Top revenue genres: Animation ($256M), Adventure ($251M), Fantasy ($227M)
- Successful movies have **3.5x higher budgets** ($103M vs $29M)

**Bottom Line:** The film industry operates on a "spend money to make money" principle, where budget investment and genre selection drive commercial performance far more than critical acclaim.

📖 **[Read Full Project Details →](./project1/README.md)**

---

### 🎬 [Project 2: Streaming vs Theatrical - A Data-Driven Analysis](./project2/)

**Focus:** Understanding how streaming platforms curate theatrical movie content

**Dataset:** 27,000+ movies across 6 data sources (TMDb, IMDb, Netflix, Hulu, Disney+, Amazon Prime)

**Key Questions:**

- How do streaming platforms compare to theatrical releases?
- What content characteristics do platforms prioritize?
- Do platforms employ selective licensing strategies?

**Key Findings:**

- Only **19% of theatrical releases** available on streaming
- Streaming-available movies have **+38% higher budgets** and **+93% higher revenue**
- Streaming platforms show **+15.3 percentage points** in Family genre representation
- Each platform employs **distinct competitive strategy** (minimal catalog overlap)

**Bottom Line:** Streaming platforms cherry-pick financially successful, highly-rated, family-friendly content rather than acquiring comprehensive theatrical libraries.

📖 **[Read Full Project Details →](./project2/README.md)**

---

### 📊 [Project 3: The Streaming Era Divide - Data Visualization](./project3/)

**Focus:** Transforming data insights into polished exploratory and explanatory visualizations

**Dataset:** 10,835 theatrical movies + 16,481 streaming titles from Project 2

**Key Questions:**

- Which decades and genres dominate streaming catalogs?
- Do streaming movies differ financially from theatrical-only releases?
- How do platforms differentiate through genre curation?

**Key Visualizations:**

1. **Recency Bias Histogram:** 72% of streaming content from 2000s-2010s
2. **ROI Box Plot:** 51-point median ROI advantage for streaming movies
3. **Genre Heatmap:** Disney+ 24.5% Family content (10x competitors)

**Bottom Line:** Streaming platforms are strategic curators, not passive distributors. They cherry-pick proven theatrical winners, focus on recent releases, and differentiate through genre specialization.

📖 **[Read Full Project Details →](./project3/README.md)**

---

## 📊 Project Comparison

| Aspect                  | Project 1                 | Project 2                         | Project 3                           |
| ----------------------- | ------------------------- | --------------------------------- | ----------------------------------- |
| **Primary Focus**       | Factors of movie success  | Streaming platform curation       | Data visualization & communication  |
| **Dataset Size**        | 10,866 movies             | 27,000+ movies                    | 10,835 theatrical + 16,481 streaming|
| **Time Period**         | 1960-2015                 | 1960-2025                         | 1960-2015                           |
| **Data Sources**        | TMDb                      | TMDb, IMDb, 4 streaming platforms | Cleaned data from Project 2         |
| **Analysis Type**       | Exploratory Data Analysis | Data Wrangling + Analysis         | EDA + Explanatory Visualization     |
| **Key Insight**         | Budget drives success     | Platforms selectively license     | Strategic curation revealed visually|
| **Statistical Testing** | Correlation analysis      | T-tests, correlation analysis     | Visual distribution comparison      |

---

## 🛠️ Technical Stack

### Core Technologies

- **Python 3.14** - Primary programming language
- **Jupyter Notebook** - Interactive development environment
- **pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Static visualizations
- **Seaborn** - Statistical data visualization
- **SciPy** - Statistical testing (Project 2)

### Data Sources

- **TMDb** - The Movie Database
- **IMDb** - Internet Movie Database (Project 2)
- **FRED** - Federal Reserve Economic Data (Project 2)
- **Kaggle** - Streaming platform datasets (Project 2)

---

## 📈 Key Insights Across Projects

### Common Themes

1. **Financial Performance Matters**

   - Both projects reveal that budget investment strongly correlates with commercial success
   - Higher-budget films tend to generate higher revenues

2. **Genre Selection is Critical**

   - Family-friendly spectacle genres (Animation, Adventure, Fantasy) dominate box office
   - Prestige genres (Documentary, History) earn critical acclaim but modest revenues

3. **Critical Reception Has Limited Impact**

   - Ratings show weak correlation with commercial success
   - Factors beyond critical acclaim (marketing, star power, timing) play larger roles

4. **Content Curation is Strategic**
   - Streaming platforms don't randomly select content
   - Selective licensing prioritizes proven performers and family-friendly content

### Complementary Findings

- **Project 1** establishes what makes movies successful (budget, genre, engagement)
- **Project 2** reveals how streaming platforms apply these insights (selective licensing of successful content)
- **Project 3** communicates these findings through polished visualizations that demonstrate strategic curation patterns

---

## 📁 Repository Structure

```
data-analyst-nanodegree-projects/
├── project1/
│   ├── Database_TMDb_movie_data/
│   │   └── tmdb-movies.csv
│   ├── Investigate_a_Dataset.ipynb
│   ├── Investigate_a_Dataset.html
│   └── README.md
├── project2/
│   ├── data/
│   │   ├── raw/
│   │   └── clean/
│   ├── data_wrangling_project_starter.ipynb
│   ├── datasets_info.md
│   └── README.md
├── project3/
│   ├── data/
│   │   ├── imdb_tmdb_theatrical_movies_merged_clean.csv
│   │   └── streaming_movies_merged_clean.csv
│   ├── Part_I_exploration_template.ipynb
│   ├── Part_II_explanatory_template.ipynb
│   └── README.md
└── README.md
```

---

## 🎓 Methodology Highlights

All projects follow rigorous data science best practices:

### Data Assessment

- Systematic identification of quality and tidiness issues
- Documentation of missing values, duplicates, and data inconsistencies
- Validation of data sources and cross-referencing

### Data Cleaning

- Data-driven decision making with empirical justification
- Preservation of raw data separately from cleaned data
- Comprehensive validation after each transformation

### Analysis

- Exploratory data analysis with multiple visualization types
- Statistical testing (correlation, t-tests)
- Clear documentation of findings and limitations

### Professional Standards

- Reproducible workflows with clear dependencies
- Comprehensive documentation and justification
- Acknowledgment of limitations and future work
