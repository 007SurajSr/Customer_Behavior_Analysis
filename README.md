# 📊 Data Analytics Project

> End-to-end data analysis pipeline — from raw data to interactive dashboard and executive presentation.

---

## 📌 Overview

This project demonstrates a complete data analytics workflow, covering data ingestion, exploratory data analysis (EDA), data cleaning, SQL-based querying, interactive dashboard development in Power BI, and a final business report and presentation.

The goal is to extract meaningful insights from raw data and communicate findings clearly to both technical and non-technical stakeholders.

---

## 📁 Dataset

| Attribute | Details |
|---|---|
| **Source** |  Kaggle  |
| **File Format** | CSV |
| **Size** | |(3900 rows × 18 columns)|
| **Domain** | Sales |
| **Key Columns** | customer_id', 'age', 'gender', 'item_purchased', 'category', 'purchase_amount', 'location', 'size', 'color', 'season', 'review_rating', 'subscription_status', 'shipping_type', 'discount_applied', 'previous_purchases', 'payment_method', 'frequency_of_purchases', 'age_group', 'purchase_frequency_days' |

> 📝 Place the raw dataset inside the `/data/raw/` folder before running any scripts.

---

## 🛠️ Tools & Technologies

| Category | Tools Used |
|---|---|
| **Language** | Python 3.x |
| **Data Analysis** | Pandas, NumPy |
| **Visualization (EDA)** | Matplotlib, Seaborn |
| **Database** | PostgreSQL / MySQL / SQL Server |
| **SQL Client** | pgAdmin / MySQL Workbench / Azure Data Studio |
| **Dashboard** | Microsoft Power BI |
| **Report** | Microsoft Word / PDF |
| **Presentation** | Gamma (AI-powered PPT) |
| **Notebook** | Jupyter Notebook |
| **Version Control** | Git & GitHub |

---

## 🔄 Project Workflow

```
Raw Data → Python EDA & Cleaning → SQL Database → Power BI Dashboard → Report & PPT
```

---

## 📋 Steps

### Step 1 — Load the Dataset
```python
import pandas as pd

df = pd.read_csv('data/raw/dataset.csv')
print(df.shape)
df.head()
```

### Step 2 — Exploratory Data Analysis (EDA)
- Checked dataset shape, data types, and column descriptions
- Identified distributions using histograms and boxplots
- Explored correlations via heatmaps
- Detected outliers and anomalies
- Visualized category-wise and time-series trends

```python
df.info()
df.describe()
df.isnull().sum()
```

### Step 3 — Data Cleaning
- Removed duplicate records
- Handled missing values (imputation / removal)
- Standardized column names and data types
- Filtered out irrelevant or erroneous rows
- Exported cleaned data to `/data/cleaned/`

```python
df.drop_duplicates(inplace=True)
df['column'].fillna(df['column'].median(), inplace=True)
df.to_csv('data/cleaned/cleaned_dataset.csv', index=False)
```

### Step 4 — SQL Queries (PostgreSQL / MySQL / SQL Server)
- Imported cleaned data into the database
- Ran analytical queries to extract business insights

**Sample Queries:**
```sql
-- Total revenue by region
SELECT region, SUM(revenue) AS total_revenue
FROM sales
GROUP BY region
ORDER BY total_revenue DESC;

-- Monthly trend
SELECT DATE_TRUNC('month', order_date) AS month, COUNT(*) AS orders
FROM sales
GROUP BY month
ORDER BY month;

-- Top 10 customers
SELECT customer_id, SUM(revenue) AS total_spent
FROM sales
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 10;
```

> All SQL scripts are stored in the `/sql/` folder.

### Step 5 — Power BI Dashboard
- Connected Power BI to the cleaned CSV / SQL database
- Built interactive visuals: KPI cards, bar charts, line graphs, slicers, maps
- Added filters for Region, Date Range, and Category
- Published the dashboard for stakeholder access

> 📂 The `.pbix` file is available in the `/dashboard/` folder.

### Step 6 — Report Creation
- Summarized methodology, key findings, and recommendations
- Included screenshots of charts and dashboard visuals
- Exported as a structured PDF/Word report

> 📂 Report available in the `/report/` folder.

### Step 7 — Presentation (Gamma)
- Created a clean, visual presentation using [Gamma](https://gamma.app)
- Covered: Problem Statement → Approach → Key Insights → Recommendations
- Exported as PDF/PPT

> 📂 Presentation file available in the `/presentation/` folder.

---

## 📊 Dashboard Preview

> *(Add a screenshot of your Power BI dashboard here)*

![Dashboard Preview](assets/dashboard_preview.png)

**Dashboard Highlights:**
- 📈 Revenue trends over time
- 🗺️ Regional sales performance map
- 🏆 Top-performing products/categories
- 👥 Customer segmentation breakdown
- 🎯 KPI cards: Total Revenue, Orders, Avg. Order Value, Growth %

---

## 💡 Key Results & Insights

- 🔍 **Finding 1:** *(e.g., Region X contributed 42% of total revenue)*
- 🔍 **Finding 2:** *(e.g., Sales peak in Q4, driven by festive demand)*
- 🔍 **Finding 3:** *(e.g., 18% of customers account for 65% of revenue)*
- 🔍 **Finding 4:** *(e.g., Category Y shows declining trend over 6 months)*
- ✅ **Recommendation:** *(e.g., Focus retention efforts on top-tier customers)*

---

## 📂 Folder Structure

```
📦 project-root/
├── 📁 data/
│   ├── raw/                  # Original dataset
│   └── cleaned/              # Processed dataset
├── 📁 notebooks/
│   └── eda_cleaning.ipynb    # Jupyter Notebook
├── 📁 sql/
│   └── queries.sql           # All SQL scripts
├── 📁 dashboard/
│   └── dashboard.pbix        # Power BI file
├── 📁 report/
│   └── project_report.pdf    # Final report
├── 📁 presentation/
│   └── project_ppt.pdf       # Gamma presentation
├── 📁 assets/
│   └── dashboard_preview.png # Dashboard screenshot
├── requirements.txt
└── README.md
```

---

## ▶️ How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name
```

### 2. Install Python Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Jupyter Notebook
```bash
jupyter notebook notebooks/eda_cleaning.ipynb
```

### 4. Set Up the Database
- Install PostgreSQL / MySQL / SQL Server
- Create a new database
- Import the cleaned CSV into your database table
- Run the scripts from `/sql/queries.sql`

### 5. Open Power BI Dashboard
- Open `dashboard/dashboard.pbix` in Power BI Desktop
- Refresh the data source if needed

---

## 📦 Requirements

```
pandas
numpy
matplotlib
seaborn
jupyter
sqlalchemy
psycopg2-binary       # For PostgreSQL
# OR
pymysql               # For MySQL
```

Install all at once:
```bash
pip install -r requirements.txt
```

---

## 👤 Author

**Your Name**
- 🔗 [LinkedIn](https://www.linkedin.com/in/surajdgsr/)
- 💻 [GitHub](https://github.com/007SurajSr))
- 📧 8700suraj@gmail.com

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

> ⭐ *If you found this project useful, consider giving it a star on GitHub!*
