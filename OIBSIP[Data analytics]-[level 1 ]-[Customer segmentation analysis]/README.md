# Customer Segmentation Analysis

## 📌 Project Overview

This project performs **customer segmentation using K-Means clustering** on an e-commerce/customer dataset.

The goal is to identify groups of customers with similar characteristics and spending behaviour so that businesses can develop **targeted marketing strategies** for different customer segments.

The analysis was completed in **Python using Google Colab**, with `pandas`, `scikit-learn`, `matplotlib`, and `seaborn`.

---

## 🎯 Objectives

The project aims to:

- Load and inspect the customer dataset.
- Handle missing values and duplicate records.
- Perform descriptive statistical analysis.
- Select meaningful customer and behavioural features.
- Standardise numerical features before clustering.
- Apply the **K-Means clustering algorithm**.
- Use the **Elbow Method** to determine an appropriate number of clusters.
- Evaluate clustering quality using the **Silhouette Score**.
- Visualise the resulting customer segments.
- Profile each cluster using customer characteristics.
- Recommend suitable marketing actions for each segment.
- Export the final customer segmentation results.

---

## 📊 Dataset

The project uses the supplied **`Customer Segmentation.csv`** dataset.

The dataset contains customer-level information including:

| Feature | Description |
|---|---|
| `ID` | Unique customer identifier |
| `Gender` | Customer gender |
| `Ever_Married` | Whether the customer has been married |
| `Age` | Customer age |
| `Graduated` | Whether the customer is a graduate |
| `Profession` | Customer profession |
| `Work_Experience` | Years of work experience |
| `Spending_Score` | Customer spending category |
| `Family_Size` | Customer family size |
| `Var_1` | Additional customer category |
| `Segmentation` | Original dataset segmentation label |

### Important Dataset Note

This dataset is **customer-level data**, rather than transaction-level retail data.

It does not contain transaction dates, purchase amounts, or purchase frequency. Therefore, a traditional **RFM (Recency, Frequency, Monetary)** analysis cannot be calculated directly without inventing information.

Instead, this project uses the available **Spending Score and customer demographic/behavioural characteristics** as clustering features.

The original `Segmentation` column is **not used to train K-Means**. It is only used afterward for comparison with the unsupervised clusters.

---

## 🛠️ Technologies Used

- **Python 3**
- **Pandas** — data manipulation and analysis
- **NumPy** — numerical operations
- **Matplotlib** — data visualisation
- **Seaborn** — statistical visualisation
- **Scikit-learn** — preprocessing and K-Means clustering
- **Kneed** — automatic Elbow Method detection
- **Google Colab / Jupyter Notebook**

---

## 🔍 Project Workflow

### 1. Data Loading

The supplied CSV dataset is loaded into a Pandas DataFrame.

### 2. Data Inspection

The dataset is inspected for:

- Number of rows and columns
- Data types
- Missing values
- Duplicate records
- Descriptive statistics
- Categorical distributions

### 3. Data Cleaning

The project:

- Removes unnecessary exported index columns.
- Removes duplicate records.
- Handles missing numerical values using the median.
- Handles missing categorical values using the most frequent category.
- Converts `Spending_Score` into an ordinal numerical feature.

The spending score is mapped as:

```text
Low     → 1
Average → 2
High    → 3
```

### 4. Feature Selection

The clustering model uses:

**Numerical features**
- Age
- Work Experience
- Family Size
- Spending Score

**Categorical features**
- Gender
- Ever Married
- Graduated
- Profession
- Var_1

The `ID` column is excluded because it is only an identifier.

The original `Segmentation` label is also excluded from clustering to prevent data leakage.

### 5. Preprocessing

Numerical features are:

- Imputed using the median.
- Standardised using `StandardScaler`.

Categorical features are:

- Imputed using the most frequent value.
- Converted into numerical features using One-Hot Encoding.

### 6. K-Means Clustering

K-Means is tested with different numbers of clusters, from **K = 2 to K = 10**.

The **Elbow Method** is used to identify an appropriate value for K.

### 7. Cluster Validation

The **Silhouette Score** is calculated as an additional measure of cluster quality.

A higher silhouette score generally indicates that customers are well separated into their respective clusters.

### 8. Cluster Visualisation

The project visualises clusters using multiple feature combinations, including:

- Age vs Work Experience
- Age vs Family Size
- Age vs Spending Score

### 9. Cluster Profiling

For every cluster, the project calculates:

- Number of customers
- Percentage of customers
- Average age
- Average work experience
- Average family size
- Average spending score
- Most common gender
- Most common marital status
- Most common graduation status
- Most common profession

### 10. Marketing Recommendations

Each cluster receives a suggested marketing strategy based on its customer profile and spending behaviour.

Examples include:

- VIP and loyalty rewards for high-spending customers.
- Discounts and value bundles for price-sensitive customers.
- Digital campaigns for younger growth-oriented customers.
- Cross-selling and personalised offers for average-spending customers.

---

## 📈 Example Marketing Segments

The project generates practical segment labels such as:

### High-Spending Customers
Customers with relatively high spending scores.

**Recommended strategy:**
- VIP rewards
- Premium products
- Personalised recommendations
- Exclusive access
- Loyalty benefits

### Low-Spending / Price-Sensitive Customers
Customers with relatively low spending scores.

**Recommended strategy:**
- Discounts
- Value bundles
- Free-shipping thresholds
- Affordable product recommendations

### Young Growth Customers
Younger customers showing potential for increased spending.

**Recommended strategy:**
- Social media campaigns
- Personalised recommendations
- Product bundles
- Repeat-purchase incentives

### Average-Spending Customers
Customers with moderate spending behaviour.

**Recommended strategy:**
- Cross-selling
- Loyalty points
- Personalised promotions
- Offers designed to increase basket value

---

## 📁 Project Files

```text
Customer-Segmentation/
│
├── Customer Segmentation.csv
├── Task_2_Customer_Segmentation_Analysis_Custom_Dataset.ipynb
├── Task_2_Customer_Segmentation_Analysis_Custom_Dataset.py
├── customer_segments.csv
├── cluster_profile.csv
└── README.md
```

### Main Notebook

`Task_2_Customer_Segmentation_Analysis_Custom_Dataset.ipynb`

Contains the complete analysis and visualisations.

### Python Script

`Task_2_Customer_Segmentation_Analysis_Custom_Dataset.py`

Contains the Python code used to perform the analysis.

### Output Files

`customer_segments.csv`

Contains each customer together with their assigned K-Means cluster and interpreted segment.

`cluster_profile.csv`

Contains the summary statistics and marketing recommendations for each cluster.

---

## 🚀 How to Run the Project

### Option 1 — Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload the `.ipynb` notebook.
3. Upload `Customer Segmentation.csv` when prompted.
4. Run the cells from top to bottom.
5. Review the clustering visualisations and segment profiles.
6. Download the generated CSV results.

### Option 2 — Jupyter Notebook

Install the required packages:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn kneed openpyxl
```

Then open:

```text
Task_2_Customer_Segmentation_Analysis_Custom_Dataset.ipynb
```

and execute the notebook cells.

---

## 📌 Key Machine Learning Concepts

### K-Means

K-Means is an unsupervised machine learning algorithm that divides observations into K groups based on similarity.

The algorithm attempts to minimise the distance between observations and the centroid of their assigned cluster.

### StandardScaler

`StandardScaler` transforms numerical variables so that they have approximately:

```text
Mean = 0
Standard deviation = 1
```

This is important for K-Means because clustering is based on distances.

### Elbow Method

The Elbow Method evaluates the model's inertia for different K values.

The selected K is based on the point where adding additional clusters provides progressively smaller improvements.

### Silhouette Score

The Silhouette Score measures how well observations fit within their assigned cluster compared with neighbouring clusters.

---

## 📊 Evaluation

The notebook reports:

- K-Means inertia for K values from 2 to 10.
- The Elbow Method plot.
- The selected number of clusters.
- Silhouette Score for the final model.
- Cluster sizes and percentages.
- Cluster-level feature profiles.

The original `Segmentation` column is also compared with the discovered clusters after training using a cross-tabulation and **Adjusted Rand Index (ARI)**.

---

## 💡 Business Value

Customer segmentation can help an e-commerce business:

- Personalise marketing campaigns.
- Identify high-value customer groups.
- Target price-sensitive customers with appropriate offers.
- Improve customer retention.
- Design better loyalty programmes.
- Recommend products based on customer profiles.
- Allocate marketing budgets more efficiently.

Instead of treating every customer identically, the company can tailor its strategy to the behaviour and characteristics of each segment.

---

## 🔮 Future Improvements

Possible improvements include:

- Adding transaction-level purchase history.
- Performing a true RFM analysis.
- Adding total revenue and average order value.
- Using customer purchase frequency.
- Testing additional clustering algorithms such as DBSCAN or hierarchical clustering.
- Comparing different feature-selection strategies.
- Creating an interactive dashboard with Power BI or Tableau.
- Building a customer lifetime value model.
- Testing cluster stability over different random seeds.

---

## 👤 Author

**Omar mohamed Elmuslimany**
---

## 📄 License

This project is intended for educational and portfolio purposes.
