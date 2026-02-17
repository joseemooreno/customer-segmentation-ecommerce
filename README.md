# Customer Segmentation Strategy – Executive Analytics Project

## 🎯 Executive Summary
This project develops a customer segmentation framework using transactional data and an **RFM-based methodology** combined with **K-Means clustering**. 

The analysis reveals a highly concentrated revenue structure:
* **13.4%** of customers generate **61.8%** of total revenue.
* Meanwhile, **55.6%** of customers contribute only **12.8%** of revenue.

This imbalance highlights a major opportunity for strategic resource allocation. The segmentation enables value protection, targeted growth strategies, and cost optimization initiatives designed to improve overall marketing **ROI**.

---

## 💼 Business Context
Retail customer bases typically exhibit uneven value distribution. Treating all customers equally leads to inefficient marketing spend and diluted impact. 

This project addresses the core strategic question:  
> **How can customer behavior segmentation improve revenue efficiency and decision-making?**

---

## ⚙️ Analytical Approach

### 1. Data Preparation
* Transactional data cleaning and customer-level aggregation.
* Removal of invalid or cancelled transactions (Quantity < 0).

### 2. Feature Engineering
**RFM Framework:**
* **Recency:** Days since last purchase.
* **Frequency:** Total number of transactions.
* **Monetary:** Total revenue generated.
* *Correlation analysis was performed to remove redundant variables and prevent multicollinearity.*

### 3. Data Transformation
* **Log transformation** (`np.log1p`) to mitigate skewness.
* **RobustScaler** applied to reduce outlier influence on cluster centroids.

### 4. Segmentation Model
* **K-Means clustering** optimized via **Elbow Method** and **Silhouette Score**.
* Final model: **4 distinct customer segments**.

---

## 🔍 Key Findings

| Segment | Base % | Revenue % | Strategic Priority |
| :--- | :---: | :---: | :--- |
| 🔵 **High-Value Loyal** | 13.4% | 61.8% | **Value Protection** |
| 🔴 **Promising** | 31.0% | 25.4% | **Growth Acceleration** |
| 🟢 **At-Risk** | 33.3% | 10.1% | **Reactivation** |
| ⚫ **Low-Value Inactive** | 22.3% | 2.7% | **Cost Optimization** |

### Customer Base & Revenue Distribution
![Customer Distribution](images/cluster_distribution.png)
![Revenue Distribution](images/revenue_distribution.png)

---

## 🚀 Strategic Recommendations

### 💎 High-Value Loyal Customers
Our main strategic priority. Although small, this group generates more than half of the total revenue. 
* **Strategy:** Focused on value retention and protection.
* **Tactics:** Highly personalized direct marketing (segmented email marketing, exclusive communications, premium promotions). It is essential to reinforce a **sense of exclusivity and belonging**.
* **Monitoring:** Implement early warning signals for decreasing purchase frequency to prevent potential churn. Investing here requires a lower absolute budget but generates a significantly higher return.

### 📈 Promising Customers
Clients who purchased recently but have room to increase frequency and spending. 
* **Strategy:** Growth acceleration and migration to High-Value tier.
* **Tactics:** Behavior-based cross-selling, incentives aimed at recurrence (loyalty points, repeat-purchase promotions), and campaigns to increase average ticket size.
* **Objective:** Gradually convert this segment into high-value assets; even small increases in frequency will materially impact total revenue.

### ⚠️ At-Risk Customers
Past high-value clients who have reduced their activity. 
* **Strategy:** Strategic reactivation.
* **Tactics:** Deploy personalized re-engagement campaigns with time-limited incentives (**“come back and get…”**) to stimulate a new purchase.
* **Reboarding:** Once reactivated, these customers should be integrated into loyalty programs similar to those for "Promising" customers.

### 📉 Low-Value Inactive Customers
Significant in size (22.3%) but marginal in revenue contribution (2.7%).
* **Strategy:** Resource optimization.
* **Tactics:** Active investment is **not recommended**. Maintain low-cost automated actions only.
* **Objective:** Prioritize budget allocation toward higher-potential segments to maximize overall marketing efficiency.

---

## 📈 Estimated Business Impact
* **Value Retention:** A 5% improvement in retention within the **High-Value** segment would disproportionately impact total revenue due to its 61.8% contribution.
* **Frequency Expansion:** Increasing annual purchase frequency by just one additional transaction among **Promising** customers could materially expand the active revenue base.
* **Efficiency:** Reactivating a small fraction of **At-Risk** customers represents low-cost incremental revenue compared to expensive new acquisition strategies.

---

## 🛠️ Technical Stack
* **Tools:** `Python`, `Pandas`, `NumPy`, `Scikit-learn`, `Matplotlib`, `Seaborn`.
* **Techniques:** RFM Analysis, K-Means Clustering, Feature Engineering, Correlation-Based Selection, Log Transformation (`np.log1p`), Robust Scaling.

---

## ⚠️ Limitations & Next Steps
* **Limitations:** K-Means geometric assumptions; static historical window; no predictive churn modeling implemented in this phase.
* **Next Steps:** Implement **Churn Prediction**, **Customer Lifetime Value (CLV)** estimation, and perform **Uplift Modeling** to measure the impact of targeted actions.

## Dataset
*Online Retail* transactional dataset.  
Source: [Kaggle / UCI Machine Learning Repository](https://www.kaggle.com/datasets/ulrikthygepedersen/online-retail-dataset)
