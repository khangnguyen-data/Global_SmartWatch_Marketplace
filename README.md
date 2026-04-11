# Global Smartwatch Marketplace Analysis (EDA) 📊

This repository contains an **Exploratory Data Analysis (EDA)** of a global smartwatch marketplace dataset. The project focuses on understanding pricing dynamics, geographic distribution, and the impact of shipping logistics on market value.

## 🚀 Project Overview
As a freshman Data Science student, I conducted this analysis to practice data cleaning, visualization, and insight generation. The goal is to identify patterns that influence smartwatch pricing across different international markets.

## 🛠️ Tech Stack
* **Language**: Python 3.x
* **Libraries**: `Pandas` (Data Manipulation & Cleaning)
  * `Matplotlib` & `Seaborn` (Data Visualization)
  * `Regex` (Text Extraction)
* Environment: Jupyter Notebook / VS Code

## 💡 Key Insights (EDA Phase)

### 1. International Shipping vs. Price
* Only **27.4%** of listings support worldwide shipping.
* **Insight:** Products offering international shipping tend to have a significantly higher median price, suggesting that high-value sellers are more willing to handle global logistics.

### 2. Geographic Market Dynamics
* **United Kingdom (UK)**: Shows the highest price volatility. The wide IQR and numerous outliers (up to $1400) indicate a highly diverse market ranging from budget to luxury segments.
* **Italy**: Exhibits the most consistent pricing with a narrow range, focusing primarily on the mid-to-high tier segment.
* **United States**: Despite being a major market, it has a surprisingly low percentage of international shipping, indicating a strong focus on domestic trade.

### 3. Data Cleaning & Imputation
* Standardized country names using a dictionary (e.g., merging "Estados Unidos" into "United States").
* Addressed missing values in `case_size` and `price` using brand-specific median imputation to maintain data distribution integrity.



## 🔮 Future Work (Phase 2)
* **Feature Engineering:** Implement advanced **Regular Expressions (Regex)** to extract model series (e.g., Series 7, 8, Ultra) and case sizes directly from the `title` column.
* **Predictive Modeling:** Build a Machine Learning model to predict smartwatch prices based on brand, origin, and technical specifications.

---
**Author**: Tuan Khang  
**Level**: 1st Year Data Science Student  
*Learning by doing, one dataset at a time.* 🚀