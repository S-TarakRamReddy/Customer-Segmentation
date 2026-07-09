# Project Report: Customer Segmentation using K-Means

**Internship:** Synent Technologies Data Science Internship (Task 6)  
**Author:** Tarak Ram Reddy  
**Date:** 2026-07-09  

---

## 1. Executive Summary
This report details the methodology, execution, and findings of the Customer Segmentation project. Utilizing the Mall Customer dataset, we applied the K-Means clustering algorithm to identify distinct purchasing behavior segments. The segmentation provides the mall's marketing and management teams with actionable insights to optimize targeted campaigns and improve customer retention.

## 2. Dataset Overview
The dataset contains 200 records with 5 features:
*   `CustomerID`: Unique sequential identifier.
*   `Gender`: Categorical variable (Male/Female).
*   `Age`: Continuous numerical variable.
*   `Annual Income (k$)`: Continuous numerical variable representing earning capacity.
*   `Spending Score (1-100)`: Continuous numerical variable assigned by the mall based on transaction history.

**Data Cleaning:** No missing values or duplicates were found. Columns were renamed for programmatic accessibility.

## 3. Exploratory Data Analysis (EDA)
Our EDA revealed several key characteristics of the customer base:
*   The average customer is 38 years old.
*   The customer base leans slightly female.
*   Most customers earn around \$60k annually, but the distribution shows a long tail of high earners.
*   A pairplot of `Annual Income` vs `Spending Score` showed visually distinct, naturally occurring clusters even before applying any machine learning algorithms.

## 4. Methodology
### 4.1 Feature Selection & Preprocessing
`CustomerID` was dropped as it carries no variance in behavior. The primary features selected for clustering were `Annual Income` and `Spending Score`. `StandardScaler` was applied to these features to ensure that K-Means, which relies on Euclidean distance, did not heavily weight one feature over another simply due to magnitude differences.

### 4.2 Optimal Cluster Determination
To determine the optimal number of clusters ($K$), we utilized the **Elbow Method** and **Silhouette Score**:
*   **WCSS (Inertia):** Plotted against K values from 2 to 10, a clear "elbow" was observed at $K=5$, suggesting diminishing returns on variance explanation beyond 5 clusters.
*   **Silhouette Score:** Confirmed this finding by peaking at exactly $K=5$ (score $\approx 0.55$), indicating strong cluster cohesion and separation.

### 4.3 Model Training
A K-Means model was instantiated with `n_clusters=5` and `init='k-means++'` for optimized centroid initialization. The model successfully converged and assigned each customer to one of the 5 segments.

## 5. Segment Profiling & Interpretation
Based on the centroid coordinates, the 5 clusters were profiled as follows:

1.  **Premium Customers (High Income, High Spend):** Affluent individuals who frequently shop and spend heavily. They are the most lucrative demographic.
2.  **Target / High Potential (Low Income, High Spend):** Likely younger demographics or fashion-conscious shoppers who spend a disproportionate amount of their income at the mall.
3.  **Standard Customers (Mid Income, Mid Spend):** The bulk of the customer base. Typical middle-class shoppers with average spending habits.
4.  **Conservative Customers (High Income, Low Spend):** High-net-worth individuals who are extremely selective with their purchases.
5.  **Budget Shoppers (Low Income, Low Spend):** Low-income individuals who only purchase essentials or heavily discounted items.

## 6. Business Recommendations
*   **Premium Customers:** Deploy VIP loyalty programs. Offer early access to exclusive product launches.
*   **Target Customers:** Use gamified loyalty systems and point-based rewards to keep their engagement high without straining their finances.
*   **Standard Customers:** Implement standard promotional bundles (e.g., "Buy 2 Get 1 Free") to encourage incremental spending increases.
*   **Conservative Customers:** Shift marketing tone toward quality, durability, and practical value to overcome their spending hesitation.
*   **Budget Shoppers:** Target with clearance sales and discount events via low-cost marketing channels (like email).

## 7. Conclusion
K-Means clustering proved highly effective for this dataset, revealing a clear 5-segment structure. Implementing targeted marketing strategies tailored to these specific segments will likely yield a higher return on investment (ROI) compared to generalized, mall-wide promotions.
