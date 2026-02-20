# 🛒 Customer Behavior Analysis — End-to-End Data Analytics Project

> A full-stack data analytics project analyzing consumer shopping behavior to help a retail company improve sales, customer satisfaction, and long-term loyalty.

---

## 📌 Business Problem

A leading retail company noticed shifts in purchasing patterns across demographics, product categories, and sales channels. The goal of this project is to answer:

> **"How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?"**

---

## 🗂️ Project Structure

```
customer-behavior-analysis
│
|__Customer_Behavior_Dashboard.zip     # Power BI interactive dashboard
|
│── customer_behavior_analysis.ipynb   # Data cleaning & feature engineering
│
│── customer_behaviour_queries.sql     # Business queries & insights
│
|── project_report.pdf                  # Full project report & recommendations
│
├── bussiness problem.pdf              # Bussiness Requirements
│  
├──Customer_behavior_analysis.pptx    # Conclusion Presentation after Data Analysis
├──
└── README.md
```

---

## 🔧 Tech Stack

| Layer | Tool |
|---|---|
| Data Preparation | Python (Pandas, NumPy) |
| Database & Analysis | MySQL |
| Visualization | Power BI |
| Environment | Google Colab / Jupyter Notebook |

---

## 📊 Project Workflow

```
Raw CSV Dataset
      ↓
[Python] Data Cleaning & Feature Engineering
      ↓
[MySQL] Structured Analysis & Business Queries
      ↓
[Power BI] Interactive Dashboard
      ↓
Insights & Recommendations
```

---

## 🐍 Phase 1 — Data Preparation (Python)

**File:** `python/customer_behavior_analysis.ipynb`

Key steps performed:
- **Imported** the raw `customer_shopping_behavior.csv` dataset
- **Handled missing values** — imputed `review_rating` using the median per category (to preserve category-level accuracy)
- **Standardized column names** — applied snake_case formatting for SQL compatibility
- **Engineered new features:**
  - `age_group` — segmented customers into *Young Adult, Adult, Middle-aged, Senior* using quartile-based binning (`pd.qcut`)
  - `purchase_frequency_days` — converted text-based frequency labels (e.g., "Weekly", "Monthly") to numeric day values for quantitative analysis
- **Removed redundant columns** — dropped `promo_code_used` as it was identical to `discount_applied`
- **Exported** the cleaned dataset as `final_dataset.csv` for MySQL ingestion

---

## 🗄️ Phase 2 — Data Analysis (SQL)

**File:** `sql/customer_behaviour_queries.sql`

10 business questions answered with SQL:

| # | Question | Technique Used |
|---|---|---|
| Q1 | Total revenue by gender | `GROUP BY`, `SUM` |
| Q2 | Discount users who spent above average | Subquery, `WHERE` filter |
| Q3 | Top 5 products by average review rating | `GROUP BY`, `ORDER BY`, `LIMIT` |
| Q4 | Average purchase: Standard vs Express shipping | Conditional `WHERE`, `GROUP BY` |
| Q5 | Do subscribers spend more? | `COUNT`, `AVG`, `SUM` comparison |
| Q6 | Top 5 products with highest discount rate | `CASE WHEN`, percentage calculation |
| Q7 | Customer segmentation: New / Returning / Loyal | `CTE`, `CASE WHEN` |
| Q8 | Top 3 products per category | `CTE`, `ROW_NUMBER()`, window function |
| Q9 | Do repeat buyers subscribe more? | `WHERE` filter, `GROUP BY` |
| Q10 | Revenue contribution by age group | Feature from Python, `GROUP BY` |

---

## 📈 Phase 3 — Dashboard (Power BI)

**File:** `dashboard/Customer_Behavior_Dashboard.pbix`

The interactive dashboard includes:
- Revenue breakdown by **gender** and **age group**
- **Customer loyalty segmentation** (New / Returning / Loyal)
- **Top products** by sales and ratings
- **Discount impact** on purchase behavior
- **Subscription vs non-subscription** spend comparison
- Seasonal and shipping-type trends

> 💡 Open the `.pbix` file using [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free download).

---

## 💡 Key Findings & Business Recommendations

See the full report in `docs/project_report.md`. Summary highlights:

- **Loyal customers** (11+ previous purchases) are a small but high-value segment — targeted retention programs can maximize LTV
- **Subscribed customers** contribute significantly more revenue — expanding subscription perks is a high-ROI opportunity
- **Discounts drive volume but not always value** — some top-discounted products overlap with lower-margin items
- **Age group analysis** reveals which demographics to target for premium vs. budget product lines
- **Repeat buyers (5+ purchases)** show strong subscription affinity — loyalty-to-subscription conversion campaigns are worth testing

---

## 🚀 How to Run This Project

### Python (Notebook)
```bash
# Install dependencies
pip install -r requirements.txt

# Open notebook
jupyter notebook python/customer_behavior_analysis.ipynb
```

### MySQL
```sql
-- 1. Create the database
CREATE DATABASE customer_behaviour;
USE customer_behaviour;

-- 2. Import final_dataset.csv into a table called `final_dataset`
--    (Use MySQL Workbench Table Data Import Wizard or LOAD DATA INFILE)

-- 3. Run queries from:
source sql/customer_behaviour_queries.sql;
```

### Power BI
1. Download [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
2. Open `dashboard/Customer_Behavior_Dashboard.pbix`
3. Refresh data source if prompted

---

## 📦 Dataset

The dataset used is the **Consumer Behavior and Shopping Habits Dataset** — a retail dataset containing customer demographics, purchase history, product details, payment methods, and shipping preferences.

> If you want to replicate this project, you can find similar datasets on [Kaggle](https://www.kaggle.com/).

---

## 👤 Author

**[Sakshi Sharma]**  
📧 [sakshishr2703@gmail.com]  
🔗 [LinkedIn - www.linkedin.com/in/sakshi2703]  
🌐 [GitHub - https://github.com/SAKSHISHR2703]





