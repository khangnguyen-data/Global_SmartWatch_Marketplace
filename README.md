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
---

### 🛠 Phase 3: Predictive Modeling (Machine Learning)

In this final phase, I implemented several regression models to predict the market price of smartwatches. The goal was to establish a robust baseline and optimize performance using advanced boosting techniques.

#### **1. Models Implemented**
* **Linear Regression:** Established as the baseline model to understand basic linear relationships.
* **Random Forest Regressor:** A robust ensemble method to capture non-linear patterns and feature interactions.
* **XGBoost (Extreme Gradient Boosting):** The champion model, optimized for high performance and handling complex tabular data.

#### **2. Key Optimization Techniques**
* **Hyperparameter Tuning:** Utilized `GridSearchCV` to find the optimal configuration (e.g., `learning_rate: 0.05`, `max_depth: 6`).
* **5-Fold Cross-Validation:** Ensured model stability and generalizability across different data subsets, preventing overfitting.
* **Evaluation Metrics:** Used **MAE** (Mean Absolute Error) for real-world cost interpretation and **$R^2$ Score** to measure explained variance.

#### **3. Performance Comparison**

| Model | MAE ($) | $R^2$ Score | Status |
| :--- | :---: | :---: | :--- |
| **Linear Regression** | ~$119.90$ | $0.1878$ | Underperforming |
| **Random Forest** | ~$98.25$ | $0.4131$ | Good |
| **XGBoost (Tuned)** | **~$96.44$** | **$0.4462$** | **Best Performance** |

#### **4. Critical Insights & Lessons Learned**
* **The Data Ceiling:** Even with advanced tuning, the $R^2$ peaked at **0.4462**. This highlights the high variance in marketplace data (e.g., subjective pricing, hidden conditions not captured in the dataset).
* **Preprocessing Impact:** The **Log Transformation ($log1p$)** applied in Phase 2 was crucial for handling price skewness, significantly improving model convergence.
* **Technical Troubleshooting:** Successfully integrated **OpenMP (`libomp`)** to enable parallel computing for XGBoost on macOS (Apple Silicon), a vital skill for local development.

> **Final Takeaway:** While the model captures nearly 45% of pricing dynamics, the next leap in accuracy would come from deeper Feature Engineering (e.g., extracting battery health or warranty status from titles).

> **Status:** Project completed with a functional Predictive Pipeline.
---
**Author**: Tuan Khang  
**Level**: 1st Year Data Science Student  
*Learning by doing, one dataset at a time.* 🚀