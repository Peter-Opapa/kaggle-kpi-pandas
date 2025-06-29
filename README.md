# ETL Pipeline( Python + MySQL)

## Project Overview
![ETL Pipeline](images/etl_pipeline.png)


This project demonstrates a real-world end-to-end ETL (Extract, Transform, Load) pipeline using Kaggle API, Python (Pandas), and MySQL. I extracted Walmart sales data from Kaggle, cleaned and transformed it using Python, and loaded the final dataset into a MySQL database for analysis.

I built this project to showcase my data engineering skills in API integration, data cleaning, SQL database interaction, and structured pipeline development.

---

## Project Steps

### 1. Environment Set Up
   - **Tools Used**: VS Code, Python 3.10+, Jupyter Notebook,MySQL
   - **Python Libraries**: pandas, sqlalchemy, pymysql, kaggle.

### 2. Kaggle API Set Up
   - I Obtained the Kaggle API token from [Kaggle](https://www.kaggle.com/) by navigating to my profile settings and downloading the JSON file.
   - I Placed the downloaded `kaggle.json` file in my local `.kaggle` folder.

### 3. Walmart Sales Data Download
   - **Data Source**: Use the Kaggle API to download the Walmart sales datasets from Kaggle.
   - **Dataset Link**: [Walmart Sales Dataset](https://www.kaggle.com/najir0123/walmart-10k-sales-datasets)

### 4.  Required Libraries Installation and Loading Data
   - I Installed the necessary Python libraries using:
     ```bash
     pip install pandas numpy sqlalchemy mysql
     ```
   - I then Read the data into a Pandas DataFrame for initial analysis and transformations.

### 5. Data Exploration
   - I Conducted data exploration to understand data distribution, check column names, types, and identify potential issues.
   - I Used functions: `df.info()`, `df.describe()`, `df.dtypes`and `df.head()` to get a quick overview of the data structure and statistics.

### 6. Data Cleaning
   - I Identified and removed duplicate entries to avoid skewed results using `df.drop_duplicates(inplace=True)`.
   - I Dropped insignificant rows or columns with missing values using `df.dropna(inplace=True)`.
   - I Ensured all columns had consistent data types.
   - I Used `.replace()` to handle and format currency values for analysis.
   - I Checked remaining inconsistencies and verified that the data was clean.

### 7. Feature Engineering
   - I Calculated the `Total Amount` for each transaction by multiplying `unit_price` by `quantity` and I added this as a new column.

### 8. Loading the Data into MySQL
   - I Connected to MySQL using `sqlalchemy` and loaded the cleaned data into my database named `walmart_db`.
   - I then Set up tables in MySQL using Python SQLAlchemy so as to automate table creation and data insertion.
   - I then Run initial SQL queries and confirmed that the data had been loaded and successfully accurately.


## Project Structure

```plaintext
|-- data/                     # Raw data and transformed data
|-- sql_queries/              # SQL scripts for analysis and queries
|-- notebooks/                # Jupyter notebooks for Python analysis
|-- README.md                 # Project documentation
|-- requirements.txt          # List of required Python libraries
|-- main.py                   # Main script for loading, cleaning, and processing data
```
---

## Future Enhancements

I will Connect SQL data to Power BI or Tableau dashboards

-I will Add scheduled automation via Airflow

-I will Expand SQL analysis notebook with business-driven questions

---

## License

This project is licensed under the MIT License. 

---

## Acknowledgments

- **Data Source**: Kaggle’s Walmart Sales Dataset
- **Inspiration**: Walmart’s business case studies on sales and supply chain optimization.

---
