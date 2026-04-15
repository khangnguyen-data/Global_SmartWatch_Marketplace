# Global Smartwatch Price Prediction & Analysis ⌚🚀

This repository contains an **Exploratory Data Analysis (EDA)** of a global smartwatch marketplace dataset. The project focuses on understanding pricing dynamics, geographic distribution, and the impact of shipping logistics on market value.

## 🚀 Project Overview
As a freshman Data Science student, I conducted this analysis to practice data cleaning, visualization, and insight generation. The goal is to identify patterns that influence smartwatch pricing across different international markets.

## 🛠️ Tech Stack
* **Language**: Python 3.x
* **Libraries**: `Pandas` (Data Manipulation & Cleaning)
  * `Matplotlib` & `Seaborn` (Data Visualization)
  * `Regex` (Text Extraction)
* Environment: Jupyter Notebook / VS Code

## 📁 Project Structure
- `Data/`: Contains raw datasets and processed feature sets (`.csv`).
- `Notebooks/`:
    - `01_Global_Smartwatch_EDA.ipynb`: Exploratory data analysis and insights.
    - `02_Feature_Engineering.ipynb`: Data preprocessing, Regex extraction, and encoding.

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



---

## 🛠️ Phase 2: Feature Engineering (Latest Progress)

In this phase, the raw dataset was transformed into a machine-learning-ready format through several advanced engineering techniques:

- **Advanced Information Extraction (Regex):** - Developed complex Regular Expression patterns to extract hidden attributes from product titles, including **Apple Series (Series 1-11, Ultra 3)**, **Case Materials (Titanium, Stainless Steel, Gold)**, and **Case Sizes**.
- **Addressing the "Cellular Paradox":** - Discovered a pricing anomaly where Cellular models had lower median prices than GPS-only models. Resolved this by identifying the underlying "Model Tier" and "Series Age" distribution.
- **Statistical Transformation:**
    - Applied **Log Transformation** ($log1p$) to the target variable `price` to mitigate skewness and handle outliers, ensuring a more normal distribution for model stability.
- **Strategic Encoding:**
    - **Ordinal Encoding:** Ranked categorical features with inherent order such as `condition` (New > Refurbished > Used) and `model_tier`.
    - **One-Hot Encoding:** Converted nominal features like `brand`, `material`, and `Country` into binary vectors while avoiding the dummy variable trap.
- **Project Restructuring:**
    - Organized the repository into a modular structure (`Data/` and `Notebooks/` folders) for better scalability and maintainability.

> **Status:** Dataset is now 100% clean with zero null values, fully encoded, and ready for the Predictive Modeling phase.

---
**Author**: Tuan Khang  
**Level**: 1st Year Data Science Student  
*Learning by doing, one dataset at a time.* 🚀