# Task 3 – Data Cleaning

## 📌 Project Overview

This project demonstrates professional-level data cleaning using **Python, pandas, NumPy, and Google Colab/Jupyter Notebook**.

The goal is to take a deliberately messy café sales dataset and transform it into a clean, consistent, and analysis-ready dataset.

## 🎯 Objectives

The project covers:

- Data quality assessment
- Missing-value detection and handling
- Duplicate-row removal
- Data standardization
- Data-type correction
- Numeric outlier detection using the IQR method
- Final data validation
- Exporting cleaned data and quality reports

## 🛠️ Tech Stack

- **Python**
- **pandas**
- **NumPy**
- **Google Colab**
- **Jupyter Notebook**

## 📂 Dataset

The input dataset is:

```text
dirty_cafe_sales.csv
```

The dataset contains café transaction information such as:

- Transaction ID
- Item
- Quantity
- Price Per Unit
- Total Spent
- Payment Method
- Location
- Transaction Date

The dataset intentionally contains data-quality problems such as missing values, inconsistent values, duplicates, invalid data types, and potential outliers.

## 🧹 Data Cleaning Process

### 1. Data Quality Report

The notebook first examines the raw dataset and reports:

- Number of rows and columns
- Missing values per column
- `ERROR` and `UNKNOWN` values
- Number of unique values
- Data types
- Duplicate rows
- Invalid dates
- Numeric range anomalies
- Total-spending calculation inconsistencies

### 2. Missing Data Handling

Different strategies are used depending on the column type.

| Data Type | Columns | Strategy | Reason |
|---|---|---|---|
| Numeric | Quantity, Price Per Unit, Total Spent | Median imputation | Median is less affected by extreme values |
| Categorical | Item, Payment Method, Location | Mode imputation | Preserves the most common valid category |
| Date | Transaction Date | Forward fill + backward fill | Preserves chronological transaction structure |

Values such as `ERROR`, `UNKNOWN`, empty strings, and blank values are converted into proper missing values before imputation.

### 3. Duplicate Removal

Duplicate rows are identified and removed using all columns.

The notebook records:

- Number of rows before duplicate removal
- Number of duplicate rows removed
- Number of rows remaining

### 4. Data Standardization

The project standardizes inconsistent data by:

- Removing unnecessary whitespace
- Standardizing categorical values
- Converting placeholder values to missing values
- Standardizing date representation
- Keeping transaction IDs as strings

Example:

```text
coffee → Coffee
credit card → Credit Card
takeaway → Takeaway
```

### 5. Data-Type Correction

The final dataset uses appropriate data types:

```text
Transaction ID    → string
Transaction Date  → datetime
Quantity          → integer
Price Per Unit    → float
Total Spent      → float
```

### 6. Outlier Detection

The **Interquartile Range (IQR)** method is used to detect outliers in numeric columns.

The calculation is:

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

Outliers are documented rather than automatically deleted because unusually large or small café transactions may represent legitimate business activity.

### 7. Final Validation

The cleaned dataset is checked for:

- Remaining missing values
- Duplicate rows
- Invalid quantities
- Non-positive prices
- Non-positive total spending
- Invalid dates
- Total-spending calculation mismatches
- Correct data types

## 📊 Output Files

After running the notebook, the following files are created:

### Cleaned Dataset

```text
clean_cafe_sales.csv
```

Contains the final analysis-ready café sales data.

### Data Quality Report

```text
data_quality_report.csv
```

Contains the initial data-quality assessment.

### Outlier Report

```text
outlier_report.csv
```

Contains the IQR calculations, bounds, number of outliers, and the decision taken for each numeric column.

## 🚀 How to Run

### Option 1 – Google Colab

1. Open Google Colab.
2. Upload:

```text
Task_3_Cleaning_Data.ipynb
```

3. Run the notebook.
4. When prompted, upload:

```text
dirty_cafe_sales.csv
```

5. Run all cells from top to bottom.
6. Download the generated CSV files.

### Option 2 – Jupyter Notebook

Install the required libraries:

```bash
pip install pandas numpy
```

Then open:

```text
Task_3_Cleaning_Data.ipynb
```

Make sure `dirty_cafe_sales.csv` is available in the working directory.

## 📁 Recommended GitHub Structure

```text
Task-3-Data-Cleaning/
│
├── Task_3_Cleaning_Data.ipynb
├── dirty_cafe_sales.csv
├── clean_cafe_sales.csv
├── data_quality_report.csv
├── outlier_report.csv
└── README.md
```

## 📈 Skills Demonstrated

This project demonstrates practical skills in:

- Data exploration
- Data quality auditing
- Missing-data treatment
- Data preprocessing
- Duplicate detection
- Data normalization
- Type conversion
- Outlier analysis
- Data validation
- Reproducible data-cleaning workflows
- Python/pandas data manipulation

## ✅ Task Checklist

- [x] Load dataset and produce a data quality report
- [x] Count nulls per column
- [x] Check duplicate rows
- [x] Identify data-type issues
- [x] Identify value-range anomalies
- [x] Handle missing data with appropriate strategies
- [x] Document missing-data decisions
- [x] Identify and remove duplicate rows
- [x] Document number of duplicates removed
- [x] Standardize inconsistent formatting
- [x] Convert dates to `datetime`
- [x] Detect numeric outliers using IQR
- [x] Document the outlier decision
- [x] Correct column data types
- [x] Validate the final cleaned dataset
- [x] Export analysis-ready data

## 👨‍💻 Author

**Omar Mohamed Elmuslimany**

---

⭐ This project is part of a practical data-cleaning task focused on transforming messy real-world-style data into an analysis-ready dataset.
