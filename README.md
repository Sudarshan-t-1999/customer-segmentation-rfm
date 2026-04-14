# Customer Segmentation using RFM Analysis and KMeans

## 🎯 Goal
Segment customers based on purchasing behavior to identify:
- High-value customers  
- Churn-risk users  
- Low-engagement users  

This enables targeted business strategies for improving retention and revenue.

---

## 📊 Problem Statement
Businesses often treat all customers equally, leading to inefficient marketing and missed revenue opportunities.  
This project uses **RFM (Recency, Frequency, Monetary) analysis** to segment customers and derive actionable insights.

---

## 🏗️ Approach / Data Flow
Raw Transactions → Data Cleaning → RFM Feature Engineering → Clustering (KMeans) → Segment Analysis → Business Insights

---

## ⚙️ Methodology

### 1. Data Cleaning
- Removed rows with missing `CustomerID`
- Dropped `Description` as it is not required for RFM analysis and does not contribute to customer-level aggregation
- Removed rows with negative and zero values for `Quantity` and `UnitPrice` columns

---

### 2. Feature Engineering (RFM)
- Calculated Total Price from `Quantity` and `UnitPrice`
- Aggregated transaction-level data to customer-level using groupby operations to compute Recency, Frequency, and Monetary features

---

### 3. Clustering
- Applied KMeans clustering on standardized RFM features to segment customers into distinct behavioral groups  
- Selected the number of clusters (K=3) using the Elbow method 
- Interpreted clusters based on RFM characteristics:

  - **High-Value Customers**: Low recency, high frequency, and high monetary value  
  - **Mid-Value Customers**: Moderate recency, frequency, and spending  
  - **Low-Value / At-Risk Customers**: High recency, low frequency, and low monetary value  

---

## 📈 Key Results
- Segmented 4338 customers into 3 distinct behavioral groups  
- Identified a high-value segment comprising <1% of customers contributing ~20% of total revenue  
- Observed strong inverse relationship between recency and customer value  

---

## 💡 Business Insights
- High-value customers contribute ~20% of revenue despite being <1% of customers, indicating strong revenue concentration  

- The mid-value segment drives the majority of revenue due to its scale, making it the primary growth lever  

- The low-value segment contributes minimal revenue, suggesting limited ROI from aggressive re-engagement strategies  

- This highlights a trade-off between scale (mid-value customers) and intensity (high-value customers) in revenue generation  

- These findings enable targeted allocation of marketing resources across customer segments to maximize ROI and reduce revenue risk  

---

## 📊 Evaluation
- Evaluated cluster separation using RFM feature distributions across segments  
- Observed distinct behavioral differences between clusters in terms of recency, frequency, and monetary values  
- Used Elbow method as a heuristic to select number of clusters  

---

## 🛠️ Tech Stack
- Python (Pandas, NumPy, Scikit-learn)  
- Matplotlib / Seaborn  

---

## ⚠️ Limitations
- KMeans assumes spherical clusters and may not capture complex customer behavior patterns  
- Clustering is based only on RFM features and does not include external factors such as product categories or seasonality  

---

## 🚀 Future Improvements
- Track customer movement between segments over time  
- Incorporate additional features such as product categories or customer demographics  
- Build predictive models for churn and customer lifetime value   

---

## 📦 Dataset
- Online Retail Dataset (UCI Machine Learning Repository)

> Note: Dataset is not included in this repository. Place it in a local `data/` folder.
