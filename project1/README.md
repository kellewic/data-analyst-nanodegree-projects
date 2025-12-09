# 🎬 Investigate a Dataset: TMDb Movie Data Analysis

[![Python](https://img.shields.io/badge/Python-3.14-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Status](https://img.shields.io/badge/Status-Complete-success.svg)]()

A comprehensive exploratory data analysis project examining the TMDb (The Movie Database) movie dataset to identify factors associated with a movie's financial success and audience reception. This analysis reveals that budget investment and genre selection drive commercial performance far more than critical acclaim.

## 📊 Project Overview

This project analyzes **10,866 movies** spanning **55 years** (1960-2015) to answer a fundamental question about the film industry:

> **What factors are associated with a movie's financial success and audience reception?**

Through systematic data wrangling and exploratory analysis of 4,667 movies with revenue data, this project demonstrates that commercial success in filmmaking is primarily driven by financial investment and genre selection, not critical acclaim.

### 🎯 Key Findings

| Metric                         | Finding                                               | Insight                                                                        |
| ------------------------------ | ----------------------------------------------------- | ------------------------------------------------------------------------------ |
| **Budget-Revenue Correlation** | r = 0.567                                             | Moderate positive relationship—higher budgets tend to generate higher revenues |
| **Rating-Revenue Correlation** | r = 0.240                                             | Weak relationship—critical reception poorly predicts commercial success        |
| **Top Revenue Genres**         | Animation ($256M), Adventure ($251M), Fantasy ($227M) | Family-friendly spectacle dominates box office                                 |
| **Top Rated Genres**           | Documentary (6.92), History (6.56), War (6.55)        | Prestige genres earn critical acclaim but modest revenues                      |
| **Successful Movie Budget**    | $103M mean vs $29M for others                         | Budget is the strongest predictor of commercial success                        |
| **Successful Movie Ratings**   | 6.64 vs 6.11 (0.5 point difference)                   | Quality matters, but only modestly                                             |

**Bottom Line:** The film industry operates on a "spend money to make money" principle, where large investments in production, marketing, and star power create self-fulfilling prophecies of commercial success.

---

## 📁 Repository Structure

```
/project1
├── Database_TMDb_movie_data/
│   └── tmdb-movies.csv              # Original dataset
├── Investigate_a_Dataset.ipynb      # Main analysis notebook
├── Investigate_a_Dataset.html       # Exported HTML report
└── README.md                        # This file
```

---

## 🔬 Methodology

### 1. Data Assessment

The TMDb dataset contains **10,866 movies** with **21 attributes** covering:

- **Financial metrics:** Budget, revenue (both original and inflation-adjusted to 2010 dollars)
- **Audience reception:** Popularity, vote count, vote average
- **Content details:** Cast, director, genres, keywords, overview, tagline
- **Production info:** Production companies, runtime, release date/year, homepage

**Initial Data Quality Issues Identified:**

- 1 duplicate row
- Missing values in non-essential columns (homepage: 72.98%, keywords: 13.74%, tagline: 25.99%)
- Missing values in critical columns (genres: 0.21%, cast: 0.7%, director: 0.4%)
- Zero values in budget/revenue (5,696 movies with $0 budget, 6,016 with $0 revenue)
- Zero runtime values (31 movies)
- Suspicious runtime values (max 900 minutes, min 2 minutes)

### 2. Data Cleaning

Systematically addressed each issue with data-driven decisions:

**Step 1: Remove Duplicates**

- Dropped 1 duplicate row (index 2090)

**Step 2: Remove Non-Critical Columns**

- Dropped: `id`, `imdb_id`, `homepage`, `keywords`, `tagline`, `overview`, `production_companies`
- Retained: `cast` and `director` for Question 4 analysis

**Step 3: Handle Missing Values**

- Removed rows with missing `cast`, `director`, or `genres` (essential for analysis)
- Result: 10,466 movies remaining

**Step 4: Filter Runtime**

- Removed movies with runtime < 45 minutes or > 240 minutes
- Rationale: Focus on theatrical releases, exclude shorts and mini-series
- Result: 10,466 movies (runtime filter removed 0-minute entries)

**Step 5: Filter Financial Data**

- Removed 4,355 movies (41.6%) with zero values for both `budget_adj` and `revenue_adj`
- Result: 6,111 movies with some financial data
- Created analysis-specific subsets:
  - **Budget-Revenue Analysis:** 3,760 movies with both budget ≥ $50K and revenue > 0
  - **Revenue-Based Analysis:** 4,667 movies with revenue > $50K

**Step 6: Budget Threshold Filter**

- Identified 33 movies with unrealistically low budgets (< $50K) due to data errors
- Example: "The Hunt for Red October" listed as $50K (actual budget: $30M)
- Applied $50K minimum threshold for budget-revenue analysis

**Final Clean Dataset:** 6,111 movies with financial data, ready for analysis

### 3. Exploratory Data Analysis

Conducted comprehensive analysis across **4 primary research questions:**

#### Question 1: How does budget relate to revenue?

**Analysis:** Examined 3,760 movies with complete financial data

**Findings:**

- Moderate positive correlation (r = 0.567)
- Both budget and revenue are highly right-skewed
- Median budget: $30.7M, Mean: $45.1M (outliers pull mean up)
- Median revenue: $64.4M, Mean: $140.1M (blockbusters dominate)
- Substantial scatter suggests budget alone doesn't guarantee success

**Visualization:** Scatter plot showing budget vs revenue with correlation coefficient

#### Question 2: Is there a relationship between critical reception and commercial success?

**Analysis:** Examined 4,667 movies with revenue data

**Findings:**

- Weak positive correlation (r = 0.240)
- Ratings follow roughly normal distribution (mean: 6.16, median: 6.20)
- Massive revenue variation at every rating level
- Movies rated 6-8 can earn anywhere from <$1M to >$2.5B
- Mean revenue by rating category:
  - Excellent (8-10): $323.9M
  - Good (7-8): $211.1M
  - Average (6-7): $121.7M
  - Below Average (4-6): $77.2M
  - Poor (0-4): $22.7M

**Key Insight:** Critical reception is a poor predictor of box office performance. Factors beyond critical acclaim (marketing, star power, genre appeal, release timing) play much larger roles.

**Visualizations:**

- Scatter plot: ratings vs revenue
- Box plot: revenue distribution by rating category

#### Question 3: Do certain genres perform better financially or critically than others?

**Analysis:** Examined 4,667 movies, exploded pipe-separated genres (average 2.62 genres per movie)

**Findings:**

**Commercial Performance:**

- **Top earners:** Animation ($256M), Adventure ($251M), Fantasy ($227M), Family ($216M)
- **Moderate performers:** Science Fiction ($187M), Action ($177M)
- **Lower performers:** Documentary ($12M), Foreign ($11M), Horror ($75M)

**Critical Reception:**

- **Highest rated:** Documentary (6.92), History (6.56), War (6.55), Western (6.41)
- **Moderate ratings:** Drama (6.37), Animation (6.35), Crime (6.28)
- **Lowest rated:** Horror (5.71), TV Movie (5.60)

**Genre Frequency:**

- Most common: Drama (2,191), Comedy (1,712), Thriller (1,372)
- Least common: TV Movie (1), Foreign (29), Western (64)

**Key Insight - The Prestige-Profit Divide:**
Documentary films receive the highest ratings (6.92) but earn modest revenues ($12M), while Animation receives moderate ratings (6.35) but dominates the box office ($256M). This suggests audiences pay to be entertained rather than critically challenged.

**Visualizations:**

- Bar chart: genre frequency
- Box plots: revenue and rating distributions by genre
- Side-by-side bar charts: mean revenue and ratings by genre

#### Question 4: What are the characteristics of the most successful movies?

**Analysis:** Defined "highly successful" as top 10% by revenue (467 movies, threshold: $314.5M)

**Findings:**

**Budget - The Primary Differentiator:**

- Highly successful: $103M mean, $96M median
- Other movies: $29M mean, $18M median
- 3.5x difference in mean budget

**Critical Reception - Modest Impact:**

- Highly successful: 6.64 mean rating
- Other movies: 6.11 mean rating
- Only 0.5-point difference

**Audience Engagement - The Hidden Factor:**

- Highly successful: 1,817 votes mean
- Other movies: 298 votes mean
- 6x difference in engagement

**Runtime - Slightly Longer:**

- Highly successful: 121 minutes mean
- Other movies: 107 minutes mean

**Genre Patterns:**

- Top genres in highly successful movies: Adventure (224), Action (215), Comedy (146), Drama (136), Thriller (131)
- Family-friendly spectacle genres dominate

**Temporal Trends:**

- Success rates stabilized around 10% from 1980 onward
- Total movie production increased from ~10/year (1960s) to ~200/year (2010s)
- More competition makes it harder to stand out

**The Success Formula:**

1. Invest heavily in production ($100M+ budget)
2. Choose high-spectacle genres (Adventure, Action, Sci-Fi, Fantasy)
3. Generate pre-release buzz (high audience engagement/votes)
4. Maintain reasonable quality (6.5+ rating is sufficient)
5. Allow adequate runtime (110-130 minutes)

**Visualizations:**

- Bar chart: top genres in highly successful movies
- Box plots: budget, ratings, vote count comparisons
- Histogram: runtime distribution comparison
- Line charts: success rate and movie count by year

### 4. Statistical Analysis

Applied correlation analysis and descriptive statistics:

- **Budget-Revenue Correlation:** r = 0.567 (moderate positive)
- **Rating-Revenue Correlation:** r = 0.240 (weak positive)
- **Distribution Analysis:** Right-skewed distributions for financial metrics, normal distribution for ratings

---

## 📈 Detailed Findings

### Financial Performance

**Budget-Revenue Relationship:**

- Moderate correlation (r = 0.567) indicates higher budgets tend to generate higher revenues
- However, substantial scatter suggests budget alone doesn't guarantee success
- Median theatrical film budget: $30.4M
- Median revenue: $64.4M
- Both show highly right-skewed distributions dominated by expensive blockbusters

**Key Insight:** The film industry operates on a "spend money to make money" principle, but many factors beyond budget influence outcomes.

### Critical Reception vs Commercial Success

**The Rating-Revenue Disconnect:**

- Weak correlation (r = 0.240) between ratings and revenue
- Movies rated 6.0 can earn anywhere from <$1M to >$2.5B
- Highly-rated movies don't necessarily earn more revenue
- Some lower-rated movies achieve significant commercial success

**Key Insight:** Critical reception appears to be a poor predictor of box office performance. Factors like marketing, star power, genre appeal, and release timing play much larger roles.

### Genre Performance

**Commercial Leaders:**

- Animation: $256M mean revenue
- Adventure: $251M mean revenue
- Fantasy: $227M mean revenue
- Family: $216M mean revenue

**Critical Favorites:**

- Documentary: 6.92 mean rating
- History: 6.56 mean rating
- War: 6.55 mean rating

**The Prestige-Profit Divide:**
There's a striking disconnect between critical acclaim and commercial success. Documentary films receive the highest ratings but earn relatively modest revenues, while Animation receives moderate ratings but dominates the box office.

**Key Insight:** Family-friendly spectacle drives revenue more effectively than artistic merit.

### Characteristics of Successful Movies

**Top 10% by Revenue ($314.5M+ threshold):**

| Characteristic | Highly Successful | Other Movies | Difference  |
| -------------- | ----------------- | ------------ | ----------- |
| **Budget**     | $103M mean        | $29M mean    | **3.5x**    |
| **Rating**     | 6.64 mean         | 6.11 mean    | +0.5 points |
| **Vote Count** | 1,817 mean        | 298 mean     | **6x**      |
| **Runtime**    | 121 min           | 107 min      | +14 min     |

**Top Genres:**

- Adventure (224 movies)
- Action (215 movies)
- Comedy (146 movies)
- Drama (136 movies)

**Key Insight:** Budget is the strongest predictor of success, followed by audience engagement (vote counts), with critical reception being a relatively weak factor.

---

## 🛠️ Technical Stack

### Core Technologies

- **Python 3.14** - Primary programming language
- **Jupyter Notebook** - Interactive development environment
- **pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Static visualizations
- **Seaborn** - Statistical data visualization

### Data Source

- **TMDb** - The Movie Database (10,866 movies, 1960-2015)

---

## 📝 Key Insights Summary

### What This Analysis Reveals

1. **Budget is Strongly Associated with Revenue**

   - Moderate positive correlation (r = 0.567)
   - Higher budgets tend to generate higher revenues
   - However, substantial variation exists at every budget level

2. **Critical Reception Weakly Predicts Commercial Success**

   - Weak correlation (r = 0.240)
   - High ratings don't guarantee high revenue
   - Many factors beyond critical acclaim influence box office performance

3. **Genre Matters Significantly**

   - Family-friendly spectacle genres (Animation, Adventure, Fantasy) dominate box office
   - Prestige genres (Documentary, History, War) earn critical acclaim but modest revenues
   - The "prestige-profit divide" is real and significant

4. **Successful Movies Share Distinct Characteristics**

   - Dramatically higher budgets ($103M vs $29M)
   - Slightly higher ratings (6.64 vs 6.11)
   - Much higher audience engagement (1,817 vs 298 votes)
   - Favor spectacle genres (Adventure, Action)

5. **The Film Industry Favors Spectacle Over Substance**
   - Family-friendly blockbusters outperform critically acclaimed dramas commercially
   - Money talks—budget is the strongest predictor of success

### Business Implications

**For Filmmakers:**

- Budget investment is crucial for commercial success
- Genre selection significantly impacts revenue potential
- Quality (ratings) matters but only modestly
- Audience engagement (buzz, marketing) is a key differentiator

**For Studios:**

- The "spend money to make money" approach dominates
- Family-friendly spectacle genres offer best ROI
- Critical acclaim doesn't guarantee commercial success
- Marketing and star power likely play larger roles than ratings

**For Audiences:**

- The films that earn the most aren't necessarily the best-rated
- The highest-rated films often earn relatively modest revenues
- Commercial success and artistic merit are often disconnected

---

## 🎓 Methodology Highlights

### Data-Driven Decision Making

Every analytical choice was validated with empirical evidence:

**Example: Runtime Filtering**

```
Analysis: Violin plot showed most runtimes fall in 45-240 minute range
Decision: Filter to 45-240 minutes to focus on theatrical releases
Justification: Excludes shorts, mini-series, and data errors
```

**Example: Budget Threshold**

```
Analysis: Identified 33 movies with budgets < $50K (clear data errors)
Decision: Apply $50K minimum threshold for budget-revenue analysis
Justification: Major films like "The Hunt for Red October" had wrong units
```

### Statistical Rigor

- Correlation coefficients calculated and interpreted
- Descriptive statistics for all key variables
- Distribution analysis (histograms, box plots, violin plots)
- Sample sizes documented for all comparisons

### Professional Standards

- Raw data preserved separately
- All transformations documented and justified
- Reproducible workflow with clear dependencies
- Comprehensive validation after each transformation
- Limitations and future work clearly stated

---

## ⚠️ Limitations

This analysis has several important limitations:

### 1. Data Quality Issues

- Budget data had inconsistent units (some entries with wrong units)
- 5,035 movies (41.6%) had zero values for both budget columns
- Data comes from crowd-sourced TMDb entries, which may contain errors
- Some movies with suspicious runtime values (0 minutes, 900 minutes)

### 2. Missing Variables

Critical factors that likely influence success were not available:

- **Marketing budgets:** Often equal to or exceed production budgets
- **Star power:** A-list actors command premium salaries and drive ticket sales
- **Studio backing:** Major studio releases receive better distribution
- **Release strategy:** Summer blockbusters vs Oscar-season releases
- **International markets:** Revenue data may not fully capture global performance
- **Streaming/home video:** Analysis focused on theatrical revenue only

### 3. Correlation vs Causation

All findings represent associations, not causal relationships:

- Higher budgets correlate with higher revenues, but this doesn't mean spending more guarantees success
- The relationship likely reflects that studios invest heavily in projects they believe will succeed (reverse causation)
- Confounding variables (marketing, stars, timing) weren't controlled for

### 4. Survivorship Bias

The dataset may over-represent successful films and under-represent failures, particularly for older movies that haven't been extensively documented on TMDb.

### 5. Genre Overlap

Movies with multiple genres (averaging 2.62 genres per film) were counted in each genre category, meaning genre statistics don't represent mutually exclusive groups.

### 6. Time Period Limitations

The dataset spans 1960-2015 but with uneven representation. Earlier decades have fewer entries and higher data quality issues, limiting our ability to draw conclusions about historical trends.

---

## 🔮 Future Work

### Proposed Extensions

1. **Include Marketing Budgets**

   - Better understand total investment vs return
   - Analyze marketing-to-production budget ratios

2. **Analyze Profitability Ratios**

   - Calculate revenue/budget ratios to identify most efficient investments
   - Compare ROI across genres and time periods

3. **Incorporate Star Power Metrics**

   - Actor salaries, social media following, previous box office performance
   - Determine if star power drives success independent of other factors

4. **Study Release Timing Effects**

   - Seasonal patterns (summer blockbusters, Oscar season)
   - Competition analysis
   - Day-of-week impacts

5. **Compare Theatrical vs Streaming Performance**

   - Extend analysis to post-2015 era as distribution models evolve
   - Analyze streaming-first releases

6. **Genre-Specific Deep Dives**

   - Understand what makes successful Horror films vs successful Comedies
   - Identify genre-specific success factors

7. **Analyze Franchise Impact**

   - Compare franchises and sequels vs original content
   - Determine if established IP drives success

8. **International vs Domestic Revenue**

   - Understand global market dynamics
   - Analyze cultural preferences by region

9. **Critical Review Sources**

   - Integrate Metacritic, Rotten Tomatoes data
   - Compare professional critics vs audience ratings

10. **Temporal Budget-Revenue Relationship**
    - Examine if the relationship has changed over time
    - Account for production cost and ticket price evolution
