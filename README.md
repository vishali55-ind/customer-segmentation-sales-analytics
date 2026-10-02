# Customer Segmentation and Sales Analytics using K-Means Clustering

## IBM SkillsBuild Data Analytics with AI Internship 2026

A data analytics and machine learning project developed as part of the **IBM SkillsBuild Data Analytics with AI Internship 2026**, offered through the **AICTE–BharatCares–IBM SkillsBuild Internship Program**.

The project applies **Exploratory Data Analysis (EDA), RFM Analysis, Feature Scaling, K-Means Clustering, and Principal Component Analysis (PCA)** to identify meaningful customer segments and generate actionable business insights from retail transaction data.

---

## Student Information

| Field | Details |
|---|---|
| **Student Name** | VISALINI S |
| **Roll Number** | 2024PECML192 |
| **College** | PANIMALAR ENGINEERING COLLEGE |
| **Department** | Artificial Intelligence and Machine Learning (AIML) |
| **Internship** | IBM SkillsBuild Data Analytics with AI Internship 2026 |
| **Project Title** | Customer Segmentation and Sales Analytics using K-Means Clustering |

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

### Dataset Source

**UCI Machine Learning Repository**

Dataset link:

https://archive.ics.uci.edu/dataset/352/online+retail

### Dataset Summary

| Property | Value |
|---|---:|
| **Original transactions** | 541,909 |
| **Original columns** | 8 |
| **Transaction period** | December 2010 – December 2011 |
| **Final cleaned transactions** | 392,692 |
| **Unique customers analysed** | 4,338 |

### Main Attributes

| Column | Description |
|---|---|
| `InvoiceNo` | Invoice or transaction number |
| `StockCode` | Product code |
| `Description` | Product description |
| `Quantity` | Quantity purchased |
| `InvoiceDate` | Transaction date and time |
| `UnitPrice` | Price per unit |
| `CustomerID` | Customer identifier |
| `Country` | Customer country |

---

## Dataset Loading

The project is designed to run directly in **Google Colab** without requiring manual dataset upload.

The notebook automatically:

1. Creates the required `data` directory.
2. Downloads the official Online Retail dataset from the UCI Machine Learning Repository.
3. Extracts the downloaded ZIP file.
4. Loads `Online Retail.xlsx` using Pandas.
5. Continues with the complete data analysis pipeline.

The raw dataset is **not stored inside this GitHub repository** because it is large and is not required to be uploaded to the repository.

### Automatic Dataset Flow

```text
UCI Machine Learning Repository
            ↓
Download online+retail.zip
            ↓
Extract ZIP file
            ↓
Online Retail.xlsx
            ↓
Load using Pandas
            ↓
Data Analysis
```

This allows the notebook to work correctly in a fresh Google Colab runtime without manually uploading the dataset.

---

## Technologies Used

| Technology / Library | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data loading and data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Scikit-learn | StandardScaler, K-Means, PCA and clustering evaluation |
| OpenPyXL | Reading Excel dataset files |
| Google Colab | Notebook execution environment |
| Jupyter Notebook | Interactive notebook format |
| GitHub | Project version control and repository hosting |

### Analytical Techniques

- Exploratory Data Analysis (EDA)
- RFM Analysis
- Feature Scaling
- K-Means Clustering
- Elbow Method
- Silhouette Score
- Principal Component Analysis (PCA)

---

## Project Structure

```text
Customer_Segmentation_Project/
│
├── Visalini_Customer_Segmentation_and_Sales_Analytics.ipynb
├── requirements.txt
├── README.md
├── Customer_Segmentation_Project_Report.docx
└── Customer_Segmentation_Internship_Presentation.pptx
```

### File Description

| File | Description |
|---|---|
| `Visalini_Customer_Segmentation_and_Sales_Analytics.ipynb` | Complete project notebook containing data loading, cleaning, analysis, clustering, visualizations, and results |
| `requirements.txt` | Python libraries required for the project |
| `README.md` | Project documentation and execution instructions |
| `Customer_Segmentation_Project_Report.docx` | Detailed project report |
| `Customer_Segmentation_Internship_Presentation.pptx` | Project presentation |

---

## Project Workflow

The project follows the workflow below:

```text
UCI Online Retail Dataset
          ↓
Automatic Dataset Download
          ↓
Data Loading
          ↓
Data Quality Check
          ↓
Data Cleaning
          ↓
Exploratory Data Analysis
          ↓
RFM Analysis
          ↓
Feature Preparation
          ↓
Feature Scaling
          ↓
K-Means Clustering
          ↓
Elbow Method
          ↓
Cluster Evaluation
          ↓
PCA Visualization
          ↓
Customer Segment Interpretation
          ↓
Business Insights
          ↓
Recommendations
```

---

## Methodology

### 1. Data Loading

The Online Retail dataset is automatically downloaded from the UCI Machine Learning Repository and loaded into the notebook.

The original dataset contains **541,909 transaction records and 8 columns**.

The notebook loads the Excel file using:

```python
pd.read_excel()
```

The dataset file is:

```text
Online Retail.xlsx
```

---

### 2. Data Quality Check

The dataset is examined for:

- Missing values
- Duplicate records
- Invalid quantity values
- Invalid unit price values
- Date formatting issues
- Customer identification

The data quality check is performed before the cleaning process.

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
| **Original transactions** | 541,909 |
| **Duplicate records removed** | 5,268 |
| **Records without CustomerID removed** | 135,037 |
| **Invalid quantity/price records removed** | 8,912 |
| **Final cleaned transactions** | 392,692 |

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

A lower Recency value indicates a more recent purchase.

### Frequency

Frequency represents the number of unique invoices associated with a customer.

### Monetary

Monetary represents the total purchase value generated by a customer.

A total of **4,338 unique customers** were analysed using these three features.

### RFM Formula

```text
Recency   = Reference Date − Most Recent Purchase Date

Frequency = Number of Unique Invoices

Monetary  = Sum of Total Purchase Value
```

### RFM Summary

| Metric | Mean |
|---|---:|
| **Recency** | 92.54 days |
| **Frequency** | 4.27 invoices |
| **Monetary** | £2,048.69 |

---

## Feature Scaling

The RFM features have different numerical ranges.

To prevent features with larger numerical values from disproportionately affecting the K-Means distance calculations, the RFM features were standardized using **StandardScaler** from scikit-learn.

```python
StandardScaler()
```

The standardized RFM features are then used as input for K-Means clustering.

---

## K-Means Clustering

K-Means is an unsupervised machine learning algorithm used to group similar data points into clusters.

In this project, K-Means was applied to the standardized RFM features to identify groups of customers with similar purchasing behaviour.

### Cluster Selection

The **Elbow Method** was examined for different values of `k`.

The final model used:

- **Number of clusters (k): 4**
- **Final inertia: 4096.30**
- **Silhouette Score: 0.6162**

The Elbow Method and Silhouette Score were used together to evaluate the clustering configuration.

---

## PCA Visualization

**Principal Component Analysis (PCA)** was used to visualize the standardized RFM feature space in two dimensions.

| Component | Variance Explained |
|---|---:|
| **PC1** | 55.47% |
| **PC2** | 30.25% |
| **Combined** | **85.73%** |

The first two principal components explain **85.73% of the variance** in the standardized RFM feature space.

---

## Customer Segmentation Results

The final K-Means model produced four customer segments.

| Cluster | Customers | Recency | Frequency | Monetary | Segment |
|---:|---:|---:|---:|---:|---|
| **0** | 3,054 | 43.70 | 3.68 | £1,353.63 | Regular Customers |
| **1** | 1,067 | 248.08 | 1.55 | £478.85 | At-Risk / Inactive Customers |
| **2** | 13 | 7.38 | 82.54 | £127,187.96 | VIP / Champion Customers |
| **3** | 204 | 15.50 | 22.33 | £12,690.50 | High-Value Loyal Customers |

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

### Recommended Strategies

| Customer Segment | Recommended Strategy |
|---|---|
| **Regular Customers** | Loyalty rewards, personalized recommendations, cross-selling |
| **At-Risk / Inactive** | Re-engagement campaigns, reminders, targeted discounts |
| **VIP / Champion** | Exclusive rewards, premium service, early access |
| **High-Value Loyal** | Loyalty programs, personalized offers, upselling |

---

## Key Results

The major outcomes of the project are:

| Metric | Result |
|---|---:|
| **Original Dataset** | 541,909 rows |
| **Final Cleaned Dataset** | 392,692 rows |
| **Customers Analyzed** | 4,338 |
| **Number of Clusters** | 4 |
| **K-Means Inertia** | 4096.30 |
| **Silhouette Score** | 0.6162 |
| **PCA Explained Variance** | 85.73% |

The project successfully identifies **four customer segments** based on RFM behaviour.

---

## Future Work

The project can be further extended by:

- Exploring **DBSCAN** or **Hierarchical Clustering** as alternative segmentation approaches.
- Incorporating additional customer and transaction attributes.
- Developing a **customer churn prediction model** using the identified segments.
- Automating the analysis pipeline for periodic customer segmentation updates.
- Extending the project with interactive dashboards for business users.
- Tracking customer movement between different segments over time.

---

## Required Libraries

The project requires the following Python libraries:

```text
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
scikit-learn>=1.3.0
notebook>=7.0.0
ipykernel>=6.0.0
openpyxl>=3.1.5
```

These dependencies are also provided in:

```text
requirements.txt
```

---

## Installation

### Clone the Repository

```bash
git clone https://github.com/vishali55-ind/customer-segmentation-sales-analytics.git
```

### Navigate to the Project Directory

```bash
cd customer-segmentation-sales-analytics
```

### Install Required Libraries

```bash
pip install -r requirements.txt
```

---

## How to Run

### Using Google Colab

The project was developed and executed using **Google Colab**.

1. Open `Visalini_Customer_Segmentation_and_Sales_Analytics.ipynb` in Google Colab.

2. Run the notebook cells sequentially from Section 1 onwards.

3. The notebook automatically downloads the official Online Retail dataset from the UCI Machine Learning Repository.

4. The ZIP file is automatically extracted.

5. `Online Retail.xlsx` is automatically loaded using Pandas.

6. No manual dataset upload is required.

7. Continue running the notebook through the final section to view the analysis, visualizations, clustering results, and customer segment profiles.

### Dataset Download Process

```text
UCI Repository
      ↓
Download online+retail.zip
      ↓
Extract ZIP
      ↓
Online Retail.xlsx
      ↓
Pandas read_excel()
      ↓
Data Analysis
```

### Using Jupyter Notebook

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
Visalini_Customer_Segmentation_and_Sales_Analytics.ipynb
```

Run the notebook cells sequentially.

---

## Raw Dataset and GitHub

The raw Online Retail dataset is **not included** in this GitHub repository.

The dataset is available from the official UCI Machine Learning Repository:

https://archive.ics.uci.edu/dataset/352/online+retail

The notebook automatically downloads the dataset during execution when it is not already available in the runtime.

This approach keeps the GitHub repository lightweight while allowing the project to remain reproducible.

---

## Project Deliverables

The project includes the following deliverables:

### 1. Project Notebook

```text
Visalini_Customer_Segmentation_and_Sales_Analytics.ipynb
```

Contains:

- Dataset loading
- Data quality checks
- Data cleaning
- Exploratory Data Analysis
- RFM analysis
- Feature preparation
- K-Means clustering
- Cluster evaluation
- PCA
- Visualizations
- Customer segmentation
- Business insights
- Recommendations

### 2. Project Report

```text
Customer_Segmentation_Project_Report.docx
```

Contains the detailed project documentation, methodology, analysis, results, and conclusions.

### 3. Project Presentation

```text
Customer_Segmentation_Internship_Presentation.pptx
```

Contains the project presentation and major findings.

### 4. Requirements File

```text
requirements.txt
```

Contains the Python dependencies required to execute the project.

### 5. README

```text
README.md
```

Contains project documentation, dataset information, setup instructions, methodology, results, and execution details.

---

## Internship Information

This project was developed as part of the:

**IBM SkillsBuild Data Analytics with AI Internship 2026**

**AICTE–BharatCares–IBM SkillsBuild Internship Program**

The internship provided exposure to:

- Data Analytics
- Artificial Intelligence
- Machine Learning
- Data Visualization
- Practical Project Development

The internship was conducted as a **6-week virtual internship** scheduled from **17 August 2026 to 30 September 2026**.

---

## Academic Context

This project demonstrates the practical application of concepts related to:

- Data Analytics
- Machine Learning
- Unsupervised Learning
- Customer Analytics
- Data Preprocessing
- Exploratory Data Analysis
- Feature Engineering
- RFM Analysis
- K-Means Clustering
- Dimensionality Reduction
- PCA
- Business Intelligence

---

## Author

**VISALINI S**

| Information | Details |
|---|---|
| **Name** | VISALINI S |
| **Roll Number** | 2024PECML192 |
| **Department** | Artificial Intelligence and Machine Learning (AIML) |
| **Institution** | PANIMALAR ENGINEERING COLLEGE |

---

## Internship Project Attribution

This project was completed by **VISALINI S** as part of the **IBM SkillsBuild Data Analytics with AI Internship 2026**, conducted under the **AICTE–BharatCares–IBM SkillsBuild Internship Program**.

The project demonstrates the application of data analytics and machine learning techniques to a real-world retail customer segmentation problem.

---

## Project Summary

The project successfully applies a complete customer analytics workflow to the **UCI Online Retail dataset**.

The workflow begins with automatic dataset acquisition and data cleaning, followed by exploratory analysis and RFM feature construction. The standardized customer-level data is then analyzed using K-Means clustering.

Four distinct customer segments are identified:

1. **Regular Customers**
2. **At-Risk / Inactive Customers**
3. **VIP / Champion Customers**
4. **High-Value Loyal Customers**

PCA is used to visualize the resulting customer groups, while the Silhouette Score is used to evaluate the clustering quality.

The resulting customer segments provide a structured way to understand customer behaviour and support targeted business strategies such as:

- Customer retention
- Re-engagement
- Loyalty programs
- Personalized recommendations
- Targeted marketing

---

## Conclusion

Customer segmentation helps organizations understand differences in customer purchasing behaviour and develop more targeted strategies.

In this project, **RFM Analysis and K-Means Clustering** were used to transform retail transaction data into meaningful customer segments.

The analysis identified four distinct customer groups with different purchasing patterns and business characteristics.

The results demonstrate how **data analytics and machine learning** can be applied to real-world retail data to support customer relationship management and data-driven business decision making.

---

## Dataset

**UCI Machine Learning Repository — Online Retail Dataset**

https://archive.ics.uci.edu/dataset/352/online+retail

---

## Developed By

**VISALINI S**

**Artificial Intelligence and Machine Learning**

**PANIMALAR ENGINEERING COLLEGE**

**IBM SkillsBuild Data Analytics with AI Internship 2026**

**AICTE–BharatCares–IBM SkillsBuild Internship Program**