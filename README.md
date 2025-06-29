# 🛒ETL Pipeline (Python + MySQL)

## 🚀 Project Overview

![ETL Pipeline](https://github.com/Peter-Opapa/python_sql_project/blob/main/ETL_pipeline_layout.png) 

This project demonstrates a **real-world end-to-end ETL (Extract, Transform, Load) pipeline** using **Kaggle API, Python (Pandas), and MySQL**. I extracted Walmart sales data from Kaggle, cleaned and transformed it using Python, and loaded the final dataset into a MySQL database for analysis.

This project showcases my data engineering skills in API integration, data cleaning, SQL database interaction, and structured pipeline development.

---

## 🧱 Project Steps

### 1. ✅ Environment Setup
- **Tools Used**: VS Code, Python 3.10+, Jupyter Notebook, MySQL
- **Python Libraries**: `pandas`, `sqlalchemy`, `pymysql`, `kaggle`

---

### 2. 🔐 Kaggle API Setup
- I Downloaded `kaggle.json` from my account on [Kaggle API Settings](https://www.kaggle.com).
- I Placed the file in `~/.kaggle/`(the project root).
- I Downloaded the dataset using:
  ```bash
  kaggle datasets download -d najir0123/walmart-10k-sales-datasets --unzip
  ```

---

### 3. 📥 Extract: Geting Walmart Sales Data
- Dataset Source: [Kaggle - Walmart Sales Dataset](https://www.kaggle.com/datasets/najir0123/walmart-10k-sales-datasets)
- I Downloaded and unzipped using Kaggle CLI.

---

### 4. 🧹 Transform: Clean with Pandas
- I Handled:
  - Duplicates & missing values
  - Currency format (`$`) and data type conversions
  - Column renaming for consistency
- Added new column:
  ```python
  df['Total_Amount'] = df['unit_price'] * df['quantity']
  ```

---

### 5. 🗃️ Load: Push to MySQL
- I Used SQLAlchemy and PyMySQL to connect:
  ```python
  engine_mysql = create_engine('mysql+pymysql://root:Opapa%401292@localhost:3306/walmart_db')
  df.to_sql('walmart_sales', con=engine_mysql, if_exists='replace', index=False)
  ```
- I Verified that data was loaded with:
  ```sql
  SELECT * FROM walmart_sales;
  ```
![Loaded Data](https://github.com/Peter-Opapa/python_sql_project/blob/main/loaded_data.jpg)
---

## 📁 Project Structure

```bash
|-- data/                   # Raw + cleaned datasets
|-- images/                 # ETL infographic + MySQL output screenshot
|-- project.ipynb/          # ETL process in Jupyter
|-- main.py                 # Optional script version of notebook
|-- README.md               # Project documentation (this file)
```

---

## 📌 Results & Proof

- 💾 Data loaded successfully into MySQL
- 🧾 Screenshot of loaded data available here (https://github.com/Peter-Opapa/python_sql_project/blob/main/loaded_data.jpg)
- 🔄 ETL Process in the Jupyter Notebook here (https://github.com/Peter-Opapa/python_sql_project/blob/main/project.ipynb)
- 🔄 Pipeline visualized in custom infographic here (https://github.com/Peter-Opapa/python_sql_project/blob/main/ETL_pipeline_layout.png)

---

## 📈 Future Enhancements

- I would Connect SQL data to Power BI or Tableau dashboards
- I would Add scheduled automation via Airflow
- I would Expand SQL analysis notebook with business-driven questions

---

## 💼 Why This Project Matters

This project shows my ability to:
- Integrate external APIs
- Handle raw data programmatically
- Work with relational databases
- Build a reproducible pipeline with clear documentation

---
