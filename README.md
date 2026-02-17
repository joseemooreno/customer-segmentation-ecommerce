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
* Transactional data cleaning.
* Customer-level aggregation.
* Removal of invalid or cancelled transactions.

### 2. Feature Engineering
**RFM Framework:**
* **Recency:** Days since last purchase.
* **Frequency:** Total number of transactions.
* **Monetary:** Total revenue generated.
* *Correlation analysis was performed to remove redundant variables and prevent multicollinearity.*

### 3. Data Transformation
* **Log transformation** using `np.log1p` to mitigate skewness.
* **RobustScaler** applied to reduce outlier influence on cluster centroids.

### 4. Segmentation Model
* **K-Means clustering.**
* Optimal **k** selected via **Elbow Method** and **Silhouette Score**.
* Final model: **4 customer segments**.

---

## 🔍 Key Findings

| Segment | Base % | Revenue % | Description |
| :--- | :---: | :---: | :--- |
| 🔵 **High-Value Loyal** | 13.4% | 61.8% | Critical revenue drivers. Small size, massive impact. |
| 🔴 **Promising** | 31.0% | 25.4% | High growth potential. Focus on increasing frequency. |
| 🟢 **At-Risk** | 33.3% | 10.1% | Declining engagement. Needs low-cost reactivation. |
| ⚫ **Low-Value Inactive** | 22.3% | 2.7% | Minimal contribution. Recommended minimal investment. |

### Customer Base Distribution
![Customer Distribution](images/cluster_distribution.png)

### Revenue Share Distribution
![Revenue Distribution](images/revenue_distribution.png)

---

## 📈 Estimated Business Impact
Based on current revenue concentration, the following strategic levers were identified:

* **Value Retention:** A 5% improvement in retention within the **High-Value** segment would disproportionately impact total revenue due to its 61.8% contribution.
* **Upselling:** Increasing annual purchase frequency by just one additional transaction among **Promising** customers could materially expand total revenue.
* **Efficiency:** Reactivating a small fraction of **At-Risk** customers represents low-cost incremental revenue compared to expensive new acquisition strategies.

---

## 🚀 Strategic Implications
* **Value Protection:** Prioritize churn prevention among High-Value customers.
* **Growth Acceleration:** Target Promising customers with frequency-driving initiatives.
* **Reactivation Strategy:** Deploy personalized campaigns to At-Risk customers.
* **Cost Optimization:** Limit active marketing spend on structurally low-value segments.

**The organization shifts from mass marketing to precision-based resource allocation.**

---

## 🛠️ Technical Stack
* **Tools:** `Python`, `Pandas`, `NumPy`, `Scikit-learn`, `Matplotlib`, `Seaborn`.
* **Techniques:** RFM Analysis, K-Means Clustering, Feature Engineering, Correlation-Based Feature Selection, Log Transformation (`np.log1p`), Robust Scaling.

---

## ⚠️ Limitations & Next Steps

### Limitations
* K-Means geometric assumptions (spherical clusters).
* Static historical analysis window.
* No predictive churn or CLV modeling implemented in this phase.

### Next Steps
1. **Churn Prediction Modeling:** Move from descriptive to predictive analysis.
2. **Customer Lifetime Value (CLV) Estimation.**
3. **Campaign Uplift Modeling:** Measure real-world impact of targeted actions.
4. **Periodic Segmentation Refresh.**
