# Customer Segmentation and Sales Analytics using K-Means Clustering

## IBM SkillsBuild Data Analytics with AI Internship 2026

A data analytics and machine learning project developed as part of the **IBM SkillsBuild Data Analytics with AI Internship 2026**, offered through the **AICTE–BharatCares–IBM SkillsBuild Internship Program**.

The project applies **Exploratory Data Analysis (EDA), RFM Analysis, Feature Scaling, K-Means Clustering, and Principal Component Analysis (PCA)** to identify meaningful customer segments and generate actionable business insights from retail transaction data.

---

## 👩‍💻 Student Information

| Field | Details |
|---|---|
| **Student Name** | VISALINI S |
| **Roll Number** | 2024PECML192 |
| **College** | PANIMALAR ENGINEERING COLLEGE |
| **Department** | Artificial Intelligence and Machine Learning (AIML) |
| **Internship** | IBM SkillsBuild Data Analytics with AI Internship 2026 |
| **Project Title** | Customer Segmentation and Sales Analytics using K-Means Clustering |

---

# 📌 Project Overview

Understanding customer behavior is important for businesses to improve customer retention, marketing strategies, and sales performance.

This project analyzes customer purchasing behavior using the **Online Retail Dataset** from the **UCI Machine Learning Repository**.

The project uses transaction-level retail data to:

- Clean and preprocess the dataset
- Perform exploratory data analysis
- Calculate **Recency, Frequency, and Monetary (RFM)** metrics
- Standardize customer-level features
- Apply the **K-Means clustering algorithm**
- Determine suitable customer groups
- Visualize clusters using **Principal Component Analysis (PCA)**
- Interpret customer segments
- Generate business-oriented recommendations

The final objective is to transform raw transaction data into meaningful customer segments that can support data-driven decision making.

---

# 🎯 Problem Statement

Retail businesses generate large amounts of customer transaction data, but raw transaction records do not directly reveal differences in customer behavior.

The objective of this project is to develop a customer segmentation system using machine learning techniques to group customers based on their purchasing behavior.

The project uses **RFM Analysis and K-Means Clustering** to identify customer groups with similar characteristics and provide useful insights for customer engagement and sales strategies.

---

# 🎯 Project Objectives

The main objectives of the project are:

1. Analyze customer transaction data from an online retail business.
2. Clean and preprocess the raw transaction dataset.
3. Perform exploratory data analysis to understand sales patterns.
4. Calculate customer-level **Recency, Frequency, and Monetary** values.
5. Standardize RFM features before clustering.
6. Apply **K-Means Clustering** to segment customers.
7. Evaluate clustering quality using the **Silhouette Score**.
8. Use PCA to visualize high-dimensional customer segments.
9. Interpret the characteristics of each customer segment.
10. Provide business recommendations based on the identified segments.

---

# 📊 Dataset

## Dataset Name

**Online Retail Dataset**

## Source

**UCI Machine Learning Repository**

🔗 **Dataset:**  
https://archive.ics.uci.edu/dataset/352/online+retail

The dataset contains transactional information from a UK-based online retail business.

### Original Dataset

| Property | Value |
|---|---|
| **Rows** | 541,909 |
| **Columns** | 8 |
| **Time Period** | December 2010 – December 2011 |

### Main Attributes

| Column | Description |
|---|---|
| `InvoiceNo` | Invoice number identifying a transaction |
| `StockCode` | Product/item code |
| `Description` | Product description |
| `Quantity` | Number of items purchased |
| `InvoiceDate` | Date and time of transaction |
| `UnitPrice` | Price per item |
| `CustomerID` | Customer identification number |
| `Country` | Customer's country |

---

# 📥 Dataset Loading

The notebook is designed to work directly in **Google Colab** without requiring manual dataset upload.

The notebook automatically:

1. Creates the required `data` directory.
2. Downloads the official Online Retail dataset from the UCI Machine Learning Repository.
3. Extracts the downloaded ZIP file.
4. Loads `Online Retail.xlsx` using Pandas.
5. Continues with the complete data analysis pipeline.

The dataset is **not stored inside this GitHub repository** because the raw dataset is large and is not required for repository execution.

The notebook automatically obtains the dataset whenever it is not already available in the Colab runtime.

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

---

# 🛠️ Technologies Used

### Programming Language

- **Python**

### Data Analysis

- **Pandas**
- **NumPy**

### Data Visualization

- **Matplotlib**
- **Seaborn**

### Machine Learning

- **Scikit-learn**
- **K-Means Clustering**
- **Principal Component Analysis (PCA)**
- **StandardScaler**
- **Silhouette Score**

### File Handling

- **OpenPyXL**

### Development and Platforms

- **Jupyter Notebook**
- **Google Colab**
- **GitHub**

### Analytical Techniques

- **Exploratory Data Analysis (EDA)**
- **RFM Analysis**
- **Feature Scaling**
- **K-Means Clustering**
- **PCA**

---

# 📁 Project Structure

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

# 🔄 Project Workflow

The complete project workflow is:

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

# 1. 📥 Import Libraries

The project uses Python libraries for:

- Data manipulation
- Numerical computation
- Data visualization
- Machine learning
- Excel file handling

### Main Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import openpyxl

from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
from sklearn.metrics import silhouette_score
from sklearn.decomposition import PCA
```

---

# 2. 📂 Load Dataset

The notebook automatically downloads the official UCI Online Retail dataset when it is not already available.

The dataset is downloaded as a ZIP file and extracted before loading the Excel file.

The notebook uses:

```python
pd.read_excel()
```

to load the dataset.

The Excel file is:

```text
Online Retail.xlsx
```

This approach makes the notebook easier to run in a fresh Google Colab runtime without manually uploading the dataset.

---

# 3. 🔍 Data Quality Check

The initial dataset contains:

- Missing values
- Duplicate records
- Invalid transaction quantities
- Invalid or non-positive unit prices

A data quality inspection is performed before the dataset is cleaned.

The analysis checks:

- Dataset dimensions
- Column names
- Data types
- Missing values
- Duplicate records
- Descriptive statistics
- Invalid values

---

# 4. 🧹 Data Cleaning

The following cleaning operations are performed.

## Duplicate Removal

Duplicate transaction records are removed.

| Cleaning Step | Records |
|---|---:|
| **Duplicates removed** | 5,268 |

## Missing Customer IDs

Transactions without a valid `CustomerID` are removed because customer segmentation requires customer-level information.

| Cleaning Step | Records |
|---|---:|
| **Rows removed due to missing CustomerID** | 135,037 |

## Invalid Quantity and Price

Rows with invalid quantities or non-positive unit prices are removed.

| Cleaning Step | Records |
|---|---:|
| **Invalid quantity/price rows removed** | 8,912 |

## Final Clean Dataset

After preprocessing:

| Metric | Result |
|---|---:|
| **Final cleaned rows** | 392,692 |

The cleaned dataset is then used for customer-level analysis.

---

# 5. 📊 Exploratory Data Analysis

Exploratory Data Analysis is performed to understand the characteristics of the retail dataset.

The analysis includes:

- Transaction distribution
- Quantity distribution
- Unit price distribution
- Sales trends
- Customer purchasing behavior
- Country-wise sales information
- Total sales analysis

A new feature called `TotalPrice` is calculated as:

```text
TotalPrice = Quantity × UnitPrice
```

This feature is used for monetary analysis and customer-level spending calculations.

---

# 6. 👥 RFM Analysis

RFM Analysis is used to understand customer purchasing behavior.

**RFM** stands for:

## Recency

Measures how recently a customer made a purchase.

A lower Recency value means the customer purchased more recently.

## Frequency

Measures how often a customer makes purchases.

In this project, frequency is calculated using the number of unique invoices associated with each customer.

## Monetary

Measures how much money a customer has spent.

It is calculated using the total value of customer transactions.

---

## 📐 RFM Formula

```text
Recency   = Reference Date − Most Recent Purchase Date

Frequency = Number of Unique Invoices

Monetary  = Sum of Total Purchase Value
```

---

# 📈 RFM Results

The average RFM values obtained from the analyzed customers are:

| Metric | Mean |
|---|---:|
| **Recency** | 92.54 days |
| **Frequency** | 4.27 invoices |
| **Monetary** | £2,048.69 |

The RFM table is then used as the input for customer segmentation.

---

# 7. ⚙️ Feature Preparation

Before applying K-Means clustering, the RFM features are prepared for machine learning.

### Selected Features

```text
Recency
Frequency
Monetary
```

Because these features have different scales, standardization is performed using:

```python
StandardScaler()
```

Standardization prevents a feature with a larger numerical range from dominating the clustering process.

---

# 8. 🤖 K-Means Clustering

K-Means is an unsupervised machine learning algorithm used to divide customers into groups based on similarity.

The algorithm works by:

1. Selecting initial cluster centroids.
2. Assigning customers to the nearest centroid.
3. Recalculating the centroid of each cluster.
4. Repeating the assignment and centroid update process.
5. Continuing until the cluster assignments stabilize.

---

# 9. 📐 Choosing the Number of Clusters

The **Elbow Method** is used to examine different values of `K`.

The within-cluster sum of squares, represented by inertia, is evaluated for different cluster counts.

The analysis identifies:

```text
Selected K = 4
```

The K-Means model is therefore trained using **four clusters**.

---

# 10. 📏 Cluster Evaluation

The quality of the clustering result is evaluated using the **Silhouette Score**.

### Silhouette Score

```text
0.6162
```

### K-Means Inertia

```text
4096.30
```

These metrics are used to assess the separation and compactness of the resulting customer groups.

---

# 11. 📉 PCA Visualization

Customer segmentation is based on multiple RFM features.

To visualize the customer groups in a two-dimensional space, **Principal Component Analysis (PCA)** is applied.

### Explained Variance

| Principal Component | Explained Variance |
|---|---:|
| **PC1** | 55.47% |
| **PC2** | 30.25% |
| **Combined** | **85.73%** |

The first two principal components therefore provide a useful two-dimensional representation of the customer data.

---

# 12. 👥 Customer Segmentation Results

The K-Means model identifies four customer segments.

| Cluster | Segment | Customers | Recency | Frequency | Monetary |
|---:|---|---:|---:|---:|---:|
| **0** | Regular Customers | 3,054 | 43.70 | 3.68 | £1,353.63 |
| **1** | At-Risk / Inactive | 1,067 | 248.08 | 1.55 | £478.85 |
| **2** | VIP / Champion | 13 | 7.38 | 82.54 | £127,187.96 |
| **3** | High-Value Loyal | 204 | 15.50 | 22.33 | £12,690.50 |

---

# 13. 🧠 Cluster Interpretation

## Cluster 0 — Regular Customers

### Characteristics

- Largest customer group
- Moderate recency
- Moderate purchase frequency
- Moderate monetary value

These customers regularly interact with the business but are not among the highest-value customers.

### Possible Strategies

- Personalized offers
- Product recommendations
- Loyalty rewards
- Cross-selling opportunities

---

## Cluster 1 — At-Risk / Inactive Customers

### Characteristics

- High recency value
- Low purchase frequency
- Low monetary value

These customers have not purchased recently and show relatively low engagement.

### Possible Strategies

- Re-engagement campaigns
- Personalized discounts
- Reminder emails
- Win-back offers

---

## Cluster 2 — VIP / Champion Customers

### Characteristics

- Very recent purchases
- Extremely high frequency
- Extremely high monetary value
- Very small customer group

These customers demonstrate exceptionally strong purchasing activity and spending.

### Possible Strategies

- VIP loyalty programs
- Exclusive offers
- Early product access
- Personalized customer service
- Premium rewards

---

## Cluster 3 — High-Value Loyal Customers

### Characteristics

- Very recent purchases
- High purchase frequency
- High monetary value
- Strong customer engagement

### Possible Strategies

- Loyalty programs
- Premium offers
- Personalized recommendations
- Cross-selling
- Upselling

---

# 14. 💡 Business Insights

The customer segmentation analysis provides several useful business insights.

## 1. Customer Behavior Is Not Uniform

Customers differ significantly in terms of purchase recency, frequency, and spending.

## 2. High-Value Customers Form a Smaller Segment

A relatively small number of customers contribute substantially higher monetary value.

## 3. At-Risk Customers Require Re-Engagement

Customers with high recency and low purchasing frequency may require targeted campaigns to encourage repeat purchases.

## 4. Regular Customers Represent a Large Opportunity

The large regular-customer segment can potentially be developed into more loyal and higher-value customers through targeted engagement.

## 5. Customer Segmentation Supports Personalization

Different customer groups can receive different marketing and retention strategies rather than receiving the same communication.

---

# 15. 📌 Business Recommendations

Based on the identified customer segments:

| Customer Segment | Recommended Strategy |
|---|---|
| **Regular Customers** | Loyalty rewards, personalized recommendations, cross-selling |
| **At-Risk / Inactive** | Re-engagement campaigns, reminders, targeted discounts |
| **VIP / Champion** | Exclusive rewards, premium service, early access |
| **High-Value Loyal** | Loyalty programs, personalized offers, upselling |

Businesses can use these segments to develop more targeted customer engagement strategies.

---

# 16. 🔄 Future Work

The project can be extended in several ways.

## Advanced Clustering

Other clustering algorithms can be explored, such as:

- DBSCAN
- Hierarchical Clustering
- Gaussian Mixture Models

## Additional Customer Features

Future versions can include:

- Product categories
- Country
- Average order value
- Purchase intervals
- Product diversity
- Customer lifetime value

## Customer Churn Prediction

Machine learning models can be developed to predict customers who are likely to stop purchasing.

## Automated Segmentation

The segmentation pipeline can be automated so that new transactions are periodically analyzed and customers are assigned to updated segments.

## Segment Migration Analysis

Future work can track how customers move between segments over time.

---

# 17. 📊 Key Results

The major results of the project are:

| Metric | Result |
|---|---:|
| **Original Dataset** | 541,909 rows |
| **Final Cleaned Dataset** | 392,692 rows |
| **Customers Analyzed** | 4,338 |
| **Number of Clusters** | 4 |
| **K-Means Inertia** | 4096.30 |
| **Silhouette Score** | 0.6162 |
| **PCA Explained Variance** | 85.73% |

The project successfully identifies **four customer segments** based on RFM behavior.

---

# 18. 📦 Required Libraries

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

# 19. ⚙️ Installation

## Clone the Repository

```bash
git clone https://github.com/vishali55-ind/customer-segmentation-sales-analytics.git
```

## Navigate to the Project Directory

```bash
cd customer-segmentation-sales-analytics
```

## Install Required Libraries

```bash
pip install -r requirements.txt
```

---

# 20. ▶️ Running the Project

## Option 1 — Google Colab

The recommended execution environment for this project is **Google Colab**.

### Steps

1. Open the notebook:

   ```text
   Visalini_Customer_Segmentation_and_Sales_Analytics.ipynb
   ```

2. Upload/open the notebook in Google Colab.

3. Run the notebook cells from beginning to end.

4. The notebook automatically downloads the Online Retail dataset from the UCI Machine Learning Repository.

5. **No manual CSV upload is required.**

6. The complete analysis will execute from dataset loading through customer segmentation and visualization.

---

## Option 2 — Jupyter Notebook

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Start Jupyter Notebook

```bash
jupyter notebook
```

### Open

```text
Visalini_Customer_Segmentation_and_Sales_Analytics.ipynb
```

Run the notebook cells sequentially.

---

# 21. 🌐 Dataset Handling in Google Colab

Google Colab runtimes are temporary.

Therefore, the notebook does not depend on a manually uploaded file remaining in the `/content` directory.

Instead, the notebook automatically downloads the official UCI dataset when required.

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

This allows the notebook to be executed in a fresh Colab runtime without manually uploading the dataset every time.

---

# 22. 📂 Raw Dataset and GitHub

The raw Online Retail dataset is **not included** in this GitHub repository.

This keeps the repository lightweight and avoids unnecessary large data files.

The dataset can be obtained from the official UCI Machine Learning Repository:

🔗 https://archive.ics.uci.edu/dataset/352/online+retail

The notebook automatically downloads the dataset during execution when it is not already available.

---

# 23. 📋 Project Deliverables

The repository contains the main project deliverables.

## 1. 📓 Project Notebook

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

---

## 2. 📄 Project Report

```text
Customer_Segmentation_Project_Report.docx
```

Contains the detailed project documentation, methodology, analysis, results, and conclusions.

---

## 3. 📊 Project Presentation

```text
Customer_Segmentation_Internship_Presentation.pptx
```

Contains the project presentation and major findings.

---

## 4. 📦 Requirements File

```text
requirements.txt
```

Contains the Python dependencies required to execute the project.

---

## 5. 📖 README

```text
README.md
```

Contains project documentation, dataset information, setup instructions, methodology, results, and execution details.

---

# 24. 🏢 Internship Information

This project was developed as part of:

### IBM SkillsBuild Data Analytics with AI Internship 2026

under the:

### AICTE–BharatCares–IBM SkillsBuild Internship Program

The internship provided exposure to:

- Data Analytics
- Artificial Intelligence
- Machine Learning
- Data Visualization
- Practical Project Development

---

# 25. 🎓 Academic Context

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

# 26. 👩‍💻 Author

## VISALINI S

| Information | Details |
|---|---|
| **Name** | VISALINI S |
| **Roll Number** | 2024PECML192 |
| **Department** | Artificial Intelligence and Machine Learning (AIML) |
| **Institution** | PANIMALAR ENGINEERING COLLEGE |

---

# 27. 🏆 Internship Project Attribution

This project was completed by **VISALINI S** as part of the **IBM SkillsBuild Data Analytics with AI Internship 2026**, conducted under the **AICTE–BharatCares–IBM SkillsBuild Internship Program**.

The project demonstrates the application of data analytics and machine learning techniques to a real-world retail customer segmentation problem.

---

# 28. 📜 Project Summary

The project successfully applies a complete customer analytics workflow to the **UCI Online Retail dataset**.

The workflow begins with data acquisition and cleaning, followed by exploratory analysis and RFM feature construction. The standardized customer-level data is then analyzed using K-Means clustering.

Four distinct customer segments are identified:

1. **Regular Customers**
2. **At-Risk / Inactive Customers**
3. **VIP / Champion Customers**
4. **High-Value Loyal Customers**

PCA is used to visualize the resulting customer groups, while the Silhouette Score is used to evaluate the clustering quality.

The resulting customer segments provide a structured way to understand customer behavior and support targeted business strategies such as:

- Customer retention
- Re-engagement
- Loyalty programs
- Personalized recommendations
- Targeted marketing

---

# ⭐ Conclusion

Customer segmentation helps organizations understand differences in customer purchasing behavior and develop more targeted strategies.

In this project, **RFM Analysis and K-Means Clustering** were used to transform retail transaction data into meaningful customer segments.

The analysis identified four distinct customer groups with different purchasing patterns and business characteristics.

The results demonstrate how **data analytics and machine learning** can be applied to real-world retail data to support customer relationship management and data-driven business decision making.

---

# 🔗 Dataset

**UCI Machine Learning Repository — Online Retail Dataset**

https://archive.ics.uci.edu/dataset/352/online+retail

---

# 👩‍💻 Developed By

**VISALINI S**

**Artificial Intelligence and Machine Learning**

**PANIMALAR ENGINEERING COLLEGE**

### IBM SkillsBuild Data Analytics with AI Internship 2026

**AICTE–BharatCares–IBM SkillsBuild Internship Program**