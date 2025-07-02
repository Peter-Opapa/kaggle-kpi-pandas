# 🛒ETL Pipeline (Python + MySQL)

## 🚀 Project Overview

![ETL Pipeline](https://github.com/Peter-Opapa/python_sql_project/blob/main/ETL_pipeline_layout.png) 

This project demonstrates a real-world ETL (Extract, Transform, Load) pipeline using the Kaggle API, Python (Pandas), and MySQL.
The goal was to extract Walmart sales data from Kaggle, clean and transform it using Python, and load the final dataset into a MySQL database for structured analysis.

It showcases key data engineering skills including API integration, data cleaning, SQL database handling, and ETL pipeline development.

-[Full ETL Implementation](https://github.com/Peter-Opapa/python_sql_project/blob/main/project.ipynb)

---

## 🧱 Project Steps

### 1. ✅ Environment Setup
- **Tools Used**: VS Code, Python 3.10+, Jupyter Notebook, MySQL
- **Python Libraries**: `pandas`, `sqlalchemy`, `pymysql`, `kaggle`

---

### 2. 🔐 Kaggle API Setup
- Downloaded `kaggle.json` from my account on [Kaggle API Settings](https://www.kaggle.com).
- Placed the file in `~/.kaggle/`(the project root).
- Downloaded the dataset using:
  ```bash
  kaggle datasets download -d najir0123/walmart-10k-sales-datasets --unzip
  ```

---

### 3. 📥 Extract: Geting Walmart Sales Data
- Dataset Source: [Kaggle - Walmart Sales Dataset](https://www.kaggle.com/datasets/najir0123/walmart-10k-sales-datasets)
- Retrieved and unzipped using Kaggle CLI.

---

### 4. 🧹 Transform: Data Cleaning with Pandas
- Performed data cleaning and transformation:
  - Removed duplicates and handled missing values
  - Converted currency-formatted strings to float
  - Renamed columns for consistency
- Added new column:
  ```python
  df['Total_Amount'] = df['unit_price'] * df['quantity']
  ```

---

### 5. 🗃️ Load: Push to MySQL
- Used SQLAlchemy and PyMySQL to connect:
  ```python
  engine_mysql = create_engine('mysql+pymysql://root:Opapa%401292@localhost:3306/walmart_db')
  df.to_sql('walmart_sales', con=engine_mysql, if_exists='replace', index=False)
  ```
- Verified that data was loaded with:
  ```sql
  SELECT * FROM walmart_sales;
  ```
![Loaded Data](https://github.com/Peter-Opapa/python_sql_project/blob/main/loaded_data.jpg)
---

## 📁 Project Structure

```bash
|-- data/                   # Raw and cleaned datasets
|-- images/                 # ETL infographic + MySQL output screenshot
|-- project.ipynb/          # Full ETL process in Jupyter
|-- main.py                 # Optional script version of notebook
|-- README.md               # Project documentation
```

---

## 📌 Results & Proof

- 💾 Data loaded successfully into MySQL
- 🧾 [Screenshot of loaded data](https://github.com/Peter-Opapa/python_sql_project/blob/main/loaded_data.jpg)
- 🔄 [Full ETL Process Jupyter Notebook](https://github.com/Peter-Opapa/python_sql_project/blob/main/project.ipynb)
- 🔄 [ETL Pipeline infographic](https://github.com/Peter-Opapa/python_sql_project/blob/main/ETL_pipeline_layout.png)

---

## 📈 Future Enhancements

- Integrate SQL data into Power BI for dashboarding
- Automate the ETL Process Using Apache Airflow
- Add deeper SQL business logic and analytical queries

---

## 💼 Why This Project Matters

This project shows my ability to:
- Work with APIs and external datasets
- Perform real-world data transformation with Pandas
- Load and interact with relational databases using Python
- Build reproducible, clean, and documented data pipelines

---
**Author**: Peter Opapa © 2025
