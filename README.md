# Retail Sales Data --- Exploratory Data Analysis (EDA)

## 📊 Project Overview

This project performs a complete **Exploratory Data Analysis (EDA)** on
a retail sales dataset using Python.

The goal is to identify sales trends, customer purchasing behavior,
best-performing categories and sub-categories, regional performance,
relationships between numerical variables, and actionable business
insights.

## 🎯 Objectives

-   Inspect and understand the dataset
-   Check data quality, missing values, duplicates, and data types
-   Calculate descriptive statistics
-   Analyze monthly and quarterly sales trends
-   Analyze customer purchasing behavior
-   Identify top-performing sub-categories
-   Compare revenue across product categories
-   Analyze correlations between numerical variables
-   Investigate discount levels and profitability
-   Identify regional and yearly performance patterns
-   Provide actionable business recommendations

## 🛠️ Tech Stack

-   **Python**
-   **Pandas**
-   **NumPy**
-   **Matplotlib**
-   **Seaborn**
-   **Jupyter Notebook / Google Colab**

## 📁 Project Structure

``` text
Retail-Sales-EDA/
│
├── Retail_Sales_EDA_Task1.ipynb
├── Retail_Sales_EDA_Task1.py
├── Retail sales data set.csv
├── retail_sales_cleaned.csv
├── category_summary.csv
├── region_summary.csv
├── customer_summary.csv
├── subcategory_summary.csv
├── monthly_summary.csv
├── quarterly_summary.csv
├── yearly_summary.csv
└── README.md
```

> The summary CSV files are generated automatically when the notebook is
> executed.

## 📋 Dataset

The dataset contains retail transaction information including:

-   Order ID
-   Order Date
-   Customer Name
-   City
-   State
-   Region
-   Category
-   Sub Category
-   Sales
-   Discount
-   Profit

The dataset contains approximately **9,994 transactions** covering the
period from **2015 to 2018**.

## 🔍 Analysis Performed

### 1. Data Inspection

The project checks:

-   Dataset shape
-   Column names
-   Data types
-   Missing values
-   Duplicate records
-   Unique values

The supplied dataset contains **no missing values and no duplicate
rows**.

### 2. Data Cleaning & Feature Engineering

The analysis includes:

-   Converting `Order Date` to datetime
-   Creating Year, Month, Quarter, and Year-Month fields
-   Calculating Profit Margin
-   Validating the date range and dataset structure

### 3. Descriptive Statistics

The notebook calculates:

-   Mean
-   Median
-   Mode
-   Standard deviation
-   Minimum
-   Maximum

for the numerical variables.

### 4. Time Series Analysis

The project analyzes:

-   Monthly sales
-   Quarterly sales and profit
-   Year-over-year sales growth

### 5. Customer Analysis

Customers are analyzed using:

-   Number of orders
-   Total sales
-   Total profit

The project also identifies the top 10 customers by sales.

### 6. Product & Category Analysis

The project analyzes:

-   Top 10 best-selling sub-categories
-   Revenue by category
-   Category profit
-   Category order volume

### 7. Correlation Analysis

A heatmap examines relationships between:

-   Sales
-   Discount
-   Profit

### 8. Additional Analysis

Discount bands are compared with average profit margins to investigate
whether larger discounts necessarily result in lower profitability.

### 9. Regional Analysis

Sales, profit, and order performance are compared across regions.

## 💡 Key Insights

### Strong Business Growth

Year-over-year sales growth was approximately:

-   **2016:** +5.3%
-   **2017:** +23.6%
-   **2018:** +28.6%

This indicates accelerating growth, with **2018 being the strongest
year**.

### Q4 Is the Strongest Quarter

**Q4 2018** was the strongest quarter, generating approximately:

-   **1.81M in sales**
-   **463.8K in profit**

This highlights the importance of seasonal planning.

### September 2018 Was the Strongest Month

The highest monthly sales occurred in **September 2018**, with
approximately **705.7K in sales**.

### Strongest Category

**Eggs, Meat & Fish** generated approximately **2.27M in sales**, making
it the highest-revenue category.

### Strongest Sub-Category

Using `Sub Category` as the product-level proxy, **Health Drinks**
generated approximately **1.05M in sales**, followed by **Soft Drinks**
at approximately **1.03M**.

### Regional Performance

The **West region** generated approximately **4.80M in sales**,
representing around **32% of total sales**.

### Customer Behavior

The dataset contains **50 unique customers**, with substantial repeat
purchasing activity.

The highest-sales customer generated approximately **334K in sales
across 224 orders**.

### Discount & Profitability

Discount has almost no linear correlation with Sales or Profit:

-   Discount vs Sales: approximately **-0.006**
-   Discount vs Profit: approximately **0.000**

Average profit margins also remain relatively stable across discount
bands.

This suggests that **discount percentage should not be evaluated in
isolation** when measuring promotion effectiveness.

## 🚀 Business Recommendations

### 1. Prepare for Q4 Demand

Increase inventory, staffing, logistics capacity, and marketing
preparation before Q4 because it consistently generates strong sales.

### 2. Prioritize High-Performing Categories

Protect inventory availability for strong categories such as **Eggs,
Meat & Fish** and **Snacks**, and pay particular attention to
high-performing sub-categories such as **Health Drinks**.

### 3. Improve Customer Retention

Use loyalty programs, personalized offers, repeat-purchase incentives,
and targeted campaigns for high-value customers.

### 4. Allocate Resources by Region

The West and East regions generate a large share of revenue. Inventory
and marketing resources should reflect regional demand.

### 5. Evaluate Discounts Using Multiple KPIs

Promotions should be evaluated using revenue, profit, profit margin,
order volume, product mix, and customer response rather than discount
percentage alone.

## ⚠️ Dataset Limitations

The assignment requested customer analysis by **age group and gender**,
but the supplied dataset does not contain `Age` or `Gender` columns.

It also does not contain an individual `Product Name` field.

Therefore:

-   Age and gender values were **not fabricated or inferred**
-   Customer behavior was analyzed using available sales and order
    information
-   `Sub Category` was used as the closest available product-level proxy

## ▶️ How to Run

### Google Colab

1.  Open `Retail_Sales_EDA_Task1.ipynb` in Google Colab.
2.  Run the cells from top to bottom.
3.  Upload `Retail sales data set.csv` when prompted.
4.  The notebook performs the complete EDA.
5.  The final section generates cleaned data and summary CSV files.

### Jupyter Notebook

Install the required libraries:

``` bash
pip install pandas numpy matplotlib seaborn jupyter
```

Then open:

``` text
Retail_Sales_EDA_Task1.ipynb
```

and run the cells sequentially.

## 📊 Project Outcome

This project demonstrates practical skills in:

-   Exploratory Data Analysis
-   Data cleaning
-   Data transformation
-   Descriptive statistics
-   Time-series analysis
-   Customer analysis
-   Product and category analysis
-   Regional analysis
-   Correlation analysis
-   Data visualization
-   Business insight generation
-   Data-driven decision making

The analysis transforms raw retail transaction data into insights that
can support decisions around **inventory, marketing, customer retention,
regional strategy, and promotional planning**.

## 👨‍💻 Author

**Omar Elmuslimany**

Data Analysis \| Excel \| Power BI \| Tableau \| Python \| SQL Server
