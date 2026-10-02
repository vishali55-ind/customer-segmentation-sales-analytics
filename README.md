# Customer Segmentation and Sales Analytics using K-Means Clustering

## IBM SkillsBuild Data Analytics with AI Internship 2026

**AICTE–BharatCares–IBM SkillsBuild Internship Program**

**Student:** VISALINI S  
**Roll Number:** 2024PECML192  
**College:** PANIMALAR ENGINEERING COLLEGE  
**Department:** Artificial Intelligence and Machine Learning (AIML)  
**Internship:** IBM SkillsBuild Data Analytics with AI Internship 2026

---

## Problem Statement

Businesses collect large volumes of customer transaction data but often struggle to convert this data into actionable customer insights.

This project applies **K-Means Clustering**, an unsupervised machine learning technique, to segment customers based on their purchasing behaviour. Customer purchasing behaviour is represented using **RFM (Recency, Frequency, Monetary)** features.

The resulting customer segments are analysed to identify different purchasing patterns and generate data-driven business recommendations.

---

## Objectives

1. Load and explore a real-world retail transaction dataset.
2. Perform data quality checks and clean the transaction data.
3. Conduct Exploratory Data Analysis (EDA).
4. Analyse customer purchasing behaviour using RFM metrics.
5. Standardize RFM features for clustering.
6. Apply K-Means Clustering and evaluate the clustering configuration.
7. Visualize and interpret the customer segments.
8. Generate business insights and recommendations from the identified segments.

---

## Dataset

The project uses the **Online Retail dataset** from the **UCI Machine Learning Repository**.

Due to GitHub file-size limitations, the raw dataset is not included in this repository.

### Dataset Source

[UCI Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)

### Dataset Details

- Original transactions: 541,909
- Original columns: 8
- Transaction period: December 2010 – December 2011
- Final cleaned transactions: 392,692
- Unique customers analysed: 4,338

### Dataset Summary

| Property | Value |
|---|---:|
| Original transactions | 541,909 |
| Original columns | 8 |
| Transaction period | December 2010 – December 2011 |
| Final cleaned transactions | 392,692 |
| Unique customers analysed | 4,338 |

### Main Attributes

- `InvoiceNo` — Invoice or transaction number
- `StockCode` — Product code
- `Description` — Product description
- `Quantity` — Quantity purchased
- `InvoiceDate` — Transaction date and time
- `UnitPrice` — Price per unit
- `CustomerID` — Customer identifier
- `Country` — Customer country

---

## Technologies Used

| Technology / Library | Purpose |
|---|---|
| Python | Core programming language |
| pandas | Data loading and data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| scikit-learn | StandardScaler, K-Means, PCA and clustering evaluation |
| Google Colab | Notebook execution environment |
| Jupyter Notebook | Interactive notebook format |

---

## Project Structure

```text
Customer_Segmentation_Project/
│
├── customer_segmentation.ipynb
├── requirements.txt
├── README.md
├── Customer_Segmentation_Project_Report.docx
└── Customer_Segmentation_Internship_Presentation.pptx
```

---

## Project Workflow

The project follows the workflow below:

```text
Online Retail Dataset
        ↓
Data Quality Check
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
RFM Feature Engineering
        ↓
Feature Scaling
        ↓
K-Means Clustering
        ↓
Cluster Evaluation
        ↓
PCA Visualization
        ↓
Customer Segment Interpretation
        ↓
Business Insights & Recommendations
```

---

## Methodology

### 1. Data Loading

The Online Retail dataset was loaded and examined to understand its structure, columns, transaction records, and customer information.

The original dataset contains **541,909 transaction records and 8 columns**.

---

### 2. Data Quality Check

The dataset was examined for:

- Missing values
- Duplicate records
- Invalid quantity values
- Invalid unit price values
- Date formatting issues
- Customer identification

---

### 3. Data Cleaning

The following preprocessing steps were performed:

- Removed duplicate records.
- Removed transactions without `CustomerID`.
- Removed transactions with non-positive `Quantity`.
- Removed transactions with non-positive `UnitPrice`.
- Converted `InvoiceDate` using the correct day-first format.
- Created a `TotalPrice` feature.

The `TotalPrice` feature was calculated as:

```text
TotalPrice = Quantity × UnitPrice
```

### Cleaning Results

| Cleaning Step | Records |
|---|---:|
| Original transactions | 541,909 |
| Duplicate records removed | 5,268 |
| Records without CustomerID removed | 135,037 |
| Invalid quantity/price records removed | 8,912 |
| Final cleaned transactions | 392,692 |

---

## Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to understand the characteristics of the cleaned retail transaction data.

The analysis focused on:

- Transaction patterns
- Customer purchasing behaviour
- Product and sales characteristics
- Distribution of transaction values
- Relationships within the retail dataset

The EDA helped establish an understanding of the data before customer-level segmentation was performed.

---

## RFM Analysis

Customer purchasing behaviour was represented using **RFM analysis**.

RFM stands for:

### Recency

Recency represents the number of days since a customer's most recent purchase.

### Frequency

Frequency represents the number of unique invoices associated with a customer.

### Monetary

Monetary represents the total purchase value generated by a customer.

A total of **4,338 unique customers** were analysed using these three features.

### RFM Summary

| Metric | Mean |
|---|---:|
| Recency | 92.54 days |
| Frequency | 4.27 invoices |
| Monetary | £2,048.69 |

---

## Feature Scaling

The RFM features have different numerical ranges.

To prevent features with larger numerical values from disproportionately affecting the K-Means distance calculations, the RFM features were standardized using **StandardScaler** from scikit-learn.

---

## K-Means Clustering

K-Means is an unsupervised machine learning algorithm used to group similar data points into clusters.

In this project, K-Means was applied to the standardized RFM features to identify groups of customers with similar purchasing behaviour.

### Cluster Selection

The **Elbow Method** was examined for values of `k` from 1 to 10.

The final model used:

- **Number of clusters (k): 4**
- **Final inertia:** 4,096.30
- **Silhouette Score:** 0.6162

The Elbow Method and Silhouette Score were used together to evaluate the clustering configuration.

---

## PCA Visualization

**Principal Component Analysis (PCA)** was used to visualize the standardized RFM feature space in two dimensions.

| Component | Variance Explained |
|---|---:|
| PC1 | 55.47% |
| PC2 | 30.25% |
| Combined | 85.73% |

The first two principal components explain **85.73% of the variance** in the standardized RFM feature space.

---

## Customer Segmentation Results

The final K-Means model produced four customer segments.

| Cluster | Customers | Recency | Frequency | Monetary | Segment |
|---|---:|---:|---:|---:|---|
| 0 | 3,054 | 43.70 | 3.68 | £1,353.63 | Regular Customers |
| 1 | 1,067 | 248.08 | 1.55 | £478.85 | At-Risk / Inactive Customers |
| 2 | 13 | 7.38 | 82.54 | £127,187.96 | VIP / Champion Customers |
| 3 | 204 | 15.50 | 22.33 | £12,690.50 | High-Value Loyal Customers |

---

## Cluster Interpretation

### Cluster 0 — Regular Customers

This is the largest segment, containing **3,054 customers**.

- **Recency:** 43.70 days
- **Frequency:** 3.68 purchases
- **Monetary:** £1,353.63

**Suggested approach:** Maintain engagement through personalized product recommendations, loyalty incentives, and relevant promotional offers.

---

### Cluster 1 — At-Risk / Inactive Customers

This segment contains **1,067 customers** with relatively high recency and lower purchasing activity.

- **Recency:** 248.08 days
- **Frequency:** 1.55 purchases
- **Monetary:** £478.85

**Suggested approach:** Use re-engagement and win-back campaigns, personalized offers, and reminders to encourage another purchase.

---

### Cluster 2 — VIP / Champion Customers

This is a very small but high-value segment containing **13 customers**.

- **Recency:** 7.38 days
- **Frequency:** 82.54 purchases
- **Monetary:** £127,187.96

**Suggested approach:** Provide VIP loyalty benefits, personalized service, exclusive offers, and retention-focused engagement.

---

### Cluster 3 — High-Value Loyal Customers

This segment contains **204 customers** with relatively recent and frequent purchasing behaviour.

- **Recency:** 15.50 days
- **Frequency:** 22.33 purchases
- **Monetary:** £12,690.50

**Suggested approach:** Strengthen loyalty through rewards, personalized recommendations, cross-selling, and targeted promotions.

---

## Business Insights and Recommendations

The identified customer segments can support differentiated customer engagement strategies.

1. **Retain high-value customers** through personalized engagement and loyalty benefits.
2. **Re-engage at-risk customers** using targeted win-back campaigns and relevant offers.
3. **Nurture regular customers** to encourage higher purchase frequency and spending.
4. **Track segment migration** by periodically repeating the RFM analysis and clustering process.
5. **Use customer segment labels** to support targeted communication and marketing activities.

---

## Key Results

The major outcomes of the project are:

- Analysed **541,909 original retail transactions**.
- Cleaned the dataset to **392,692 transactions**.
- Analysed purchasing behaviour for **4,338 unique customers**.
- Created customer-level **RFM features**.
- Standardized RFM features using **StandardScaler**.
- Applied **K-Means clustering** with four clusters.
- Obtained a **Silhouette Score of 0.6162**.
- Used PCA for two-dimensional visualization with **85.73% combined variance explained**.
- Identified four customer purchasing behaviour segments.
- Developed business recommendations based on the identified segments.

---

## Future Work

The project can be further extended by:

- Exploring **DBSCAN** or **Hierarchical Clustering** as alternative segmentation approaches.
- Incorporating additional customer and transaction attributes.
- Developing a **customer churn prediction model** using the identified segments.
- Automating the analysis pipeline for periodic customer segmentation updates.
- Extending the project with interactive dashboards for business users.

---

## How to Run

### Using Google Colab

The project was developed and executed using **Google Colab**.

1. Open `customer_segmentation.ipynb` in Google Colab.
2. Upload the `online_retail.csv` dataset.
3. Place the dataset inside the `data/` folder.
4. Run the notebook cells sequentially from Section 1 to Section 12.
5. Review the generated analysis, visualizations, clustering results, and customer segment profiles.

The notebook uses:

```python
DATA_FILE = 'data/online_retail.csv'
```

### Required Libraries

The project uses the following Python libraries:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
```

The corresponding dependencies are listed in `requirements.txt`.

---

## Project Deliverables

The project includes:

- `customer_segmentation.ipynb` — Complete analysis and machine learning workflow
- `online_retail.csv` — Dataset used for the analysis
- `outputs/` — Generated analysis and visualization outputs
- `Customer_Segmentation_Project_Report.docx` — Internship project report
- `Customer_Segmentation_Internship_Presentation.pptx` — Project presentation
- `requirements.txt` — Python dependencies
- `README.md` — Project documentation

---

## Internship Information

This project was developed as part of the:

**IBM SkillsBuild Data Analytics with AI Internship 2026**

**AICTE–BharatCares–IBM SkillsBuild Internship Program**

According to the internship offer letter, the program is a **6-week virtual internship** scheduled from **17 August 2026 to 30 September 2026**.

---

## Author

**VISALINI S**  
**Roll Number:** 2024PECML192  
**Department:** Artificial Intelligence and Machine Learning (AIML)  
**Panimalar Engineering College**

---

## Internship Attribution

This project was developed as part of the **IBM SkillsBuild Data Analytics with AI Internship 2026**, conducted under the **AICTE–BharatCares–IBM SkillsBuild Internship Program**.
