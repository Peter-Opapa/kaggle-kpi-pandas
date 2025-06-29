# 🛒 Walmart Data ETL Pipeline (Python + MySQL)

## 🚀 Project Overview

![ETL Pipeline](images/etl_pipeline.png)  
*(Custom infographic showing Extract → Transform → Load flow)*

This project demonstrates a **real-world end-to-end ETL (Extract, Transform, Load) pipeline** using **Kaggle API, Python (Pandas), and MySQL**. I extracted Walmart sales data from Kaggle, cleaned and transformed it using Python, and loaded the final dataset into a MySQL database for analysis.

This project is ideal for showcasing data engineering skills including API integration, data cleaning, SQL database interaction, and structured pipeline development.

---

## 🧱 Project Steps

### 1. ✅ Environment Setup
- **Tools Used**: VS Code, Python 3.10+, Jupyter Notebook, MySQL
- **Python Libraries**: `pandas`, `sqlalchemy`, `pymysql`, `kaggle`

---

### 2. 🔐 Kaggle API Setup
- Download `kaggle.json` from [Kaggle API Settings](https://www.kaggle.com/account).
- Place it in `~/.kaggle/` or the project root.
- Download dataset using:
  ```bash
  kaggle datasets download -d najir0123/walmart-10k-sales-datasets --unzip
  ```

---

### 3. 📥 Extract: Get Walmart Sales Data
- Dataset Source: [Kaggle - Walmart Sales Dataset](https://www.kaggle.com/datasets/najir0123/walmart-10k-sales-datasets)
- Downloaded and unzipped using Kaggle CLI.

---

### 4. 🧹 Transform: Clean with Pandas
- Handled:
  - Duplicates & missing values
  - Currency format (`$`) and data type conversions
  - Column renaming for consistency
- Added new column:
  ```python
  df['Total_Amount'] = df['unit_price'] * df['quantity']
  ```

---

### 5. 🗃️ Load: Push to MySQL
- Used SQLAlchemy and PyMySQL to connect:
  ```python
  engine = create_engine('mysql+pymysql://root:password@localhost:3306/walmart_db')
  df.to_sql('walmart_sales', con=engine, if_exists='replace', index=False)
  ```
- Verified data was loaded with:
  ```sql
  SELECT * FROM walmart_sales LIMIT 5;
  ```

---

### 6. 📊 SQL Analysis (Future Work)
- Once in MySQL, data can be queried using:
  - Aggregations: `SUM`, `AVG`, `GROUP BY`
  - Filtering by branch, product category, payment methods
  - Time-based analysis (daily/monthly trends)

---

## 📁 Project Structure

```bash
|-- data/                   # Raw + cleaned datasets
|-- images/                 # ETL infographic + MySQL output screenshot
|-- notebooks/              # ETL process in Jupyter
|-- main.py                 # Optional script version of notebook
|-- README.md               # Project documentation (this file)
```

---

## ✅ Requirements

- Python 3.8+
- MySQL installed locally (port 3306)
- Python packages:
  - `pandas`
  - `sqlalchemy`
  - `pymysql`
  - `kaggle`

Install all via:
```bash
pip install -r requirements.txt
```

---

## 📌 Results & Proof

- 💾 Data loaded successfully into MySQL
- 🧾 Screenshot of loaded data available in `/images/mysql_output.png`
- 🔄 Full pipeline visualized in custom infographic

---

## 📈 Future Enhancements

- Connect SQL data to Power BI or Tableau dashboards
- Add scheduled automation via Airflow or Cron
- Expand SQL analysis notebook with business-driven questions

---

## 💼 Why This Project Matters

This project shows my ability to:
- Integrate external APIs
- Handle raw data programmatically
- Work with relational databases
- Build a reproducible pipeline with clear documentation

---

## 🔗 Contact & Showcase

Feel free to check out the [GitHub Repo](#) or connect with me on [LinkedIn](#)  
Open to feedback, contributions, or collaboration!
