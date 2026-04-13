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
- Dropped 'Description' as it is not required for RFM analysis and does not contribute to customer-level aggregation
- Removed rows with negative and zero values for "Quantity" and "UnitPrice" columns

---

### 2. Feature Engineering (RFM)
- Calculated Total Price from Quantity and UnitPrice 
- Derived the Recency, Frequency and Monetary features from the data using GroupBy function

---

### 3. Clustering
- Applied KMeans clustering on standardized RFM features to segment customers into distinct behavioral groups  
- Selected the optimal number of clusters (K=3) using the Elbow method  
- Interpreted clusters based on RFM characteristics:

  - **High-Value Customers**: Low recency, high frequency, and high monetary value  
  - **Mid-Value Customers**: Moderate recency, frequency, and spending  
  - **Low-Value / At-Risk Customers**: High recency, low frequency, and low monetary value  

---

## 📈 Key Results
- Segmented ~4300+ customers into 3 distinct behavioral groups  
- Identified a small segment of high-value customers with significantly higher purchase frequency and spending  
- Observed strong inverse relationship between recency and customer value  

---

## 💡 Business Insights
- High-value customers contribute disproportionately to total revenue and should be prioritized for retention strategies  
- Customers with high recency and low frequency represent churn risk and can be targeted with re-engagement campaigns  
- Mid-value customers present an opportunity for upselling and increased engagement  

---

## 📊 Evaluation
- Cluster quality evaluated using RFM distribution across segments  
- Verified clear separation between clusters based on customer behavior patterns  
- Elbow method used to determine optimal number of clusters  

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
