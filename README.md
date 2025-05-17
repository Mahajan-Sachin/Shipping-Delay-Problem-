# 📦 Shipping Delay Analysis – EDA Project

This project dives deep into the **Exploratory Data Analysis (EDA)** of a Superstore dataset to analyze **shipping delays**. The goal was to identify issues in delivery timelines, clean and engineer meaningful features, and extract actionable business insights.

---

## 🔍 Project Objective

To explore and understand the **factors affecting shipping delays** in customer orders, clean corrupted/missing datetime values, and visualize delay trends across different product categories and regions.

---

## 📂 Dataset

- Source: [Superstore Dataset](#) *(https://www.kaggle.com/datasets/vivek468/superstore-dataset-final )*
- Format: Excel (XLSX/CSV)
- Size: ~10,000 rows x 22 columns
- Key Columns: `order_date`, `ship_date`, `category`, `region`, `sales`, `quantity`, `shipping_delay`, etc.

---

## 🛠️ Key Steps & Techniques Used

### 1. 📌 Data Cleaning
- Identified and removed hidden missing values (e.g., `#####` in Excel)
- Parsed date columns (`order_date`, `ship_date`) into proper datetime format
- Removed corrupted date rows using `.notnull()` and `pd.to_datetime()`

### 2. 🧪 Feature Engineering
- Created `shipping_delay` column:
  ```python
  df['shipping_delay'] = (df['ship_date'] - df['order_date']).dt.days
  3. 🚨 Outlier Detection & Removal
### 3. 🚨 Outlier Detection & Removal
Applied IQR method to clean outliers in shipping_delay

Ensured business sense was preserved (e.g., didn't drop legitimate delays)

Verified visually using seaborn boxplots

### 4. 📊 Data Analysis & Visualization
Used groupby() and pivot_table() to analyze:

Average shipping delay by category

Delay trends across region and segment

Visualized using:

Boxplots

Histograms

Heatmaps (missingno)

Grouped bar charts (Seaborn)

📈 Key Insights
All three product categories had a similar average delay (~4 days)

No lower-end outliers were present in shipping_delay

High shipping delays were rare but significant

Proper datetime parsing is critical in business datasets

🧰 Tools & Libraries
Python 3.11+

Pandas

NumPy

Seaborn

Matplotlib

Missingno

🚀 Future Improvements
🧠 Build a predictive model for delivery time based on other features

📊 Streamlit dashboard for business teams

📦 Model deployment and alert system for delayed shipments



"Data speaks louder when you clean it right." – Me (after fixing ##### in Excel 😅)
