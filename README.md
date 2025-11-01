# Customer Segmentation using RFM Analysis and K-Means Clustering

📊 This project performs customer segmentation on a transactional dataset from an online retailer. The goal is to group customers into distinct segments based on their purchasing behavior to enable more effective and targeted marketing campaigns.

## Table of Contents
- [Objective](#objective)
- [Dataset](#dataset)
- [Project Workflow](#project-workflow)
- [Key Techniques & Libraries](#key-techniques--libraries)
- [Results: Customer Segments](#results-customer-segments)
- [Future Improvements](#future-improvements)

## Objective
To identify distinct customer groups by applying RFM (Recency, Frequency, Monetary) analysis and the K-Means clustering algorithm. By understanding the characteristics of each segment, a business can tailor its marketing efforts, improve customer retention, and maximize profitability.

## Dataset
The project uses the **Online Retail Dataset** from the UCI Machine Learning Repository.

- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/online+retail)
- **Instances:** 541,909
- **Attributes:** `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.

## Project Workflow
The project follows a standard data science pipeline:

1.  **Data Cleaning & Preprocessing:**
    - Loaded the dataset and handled initial data inconsistencies.
    - Removed rows with missing `CustomerID`.
    - Filtered out canceled transactions (invoices starting with 'C').
    - Removed records with negative quantities or zero unit price.
    - Created a `TotalPrice` feature (`Quantity` * `UnitPrice`).

2.  **Feature Engineering (RFM Analysis):**
    - Calculated the three key RFM metrics for each customer:
        - **Recency (R):** Days since the customer's last purchase.
        - **Frequency (F):** Total number of unique transactions made by the customer.
        - **Monetary (M):** Total amount of money spent by the customer.

3.  **Data Preparation for Clustering:**
    - Addressed the skewness in the RFM features using a log transformation.
    - Scaled the data using `StandardScaler` to ensure all features contribute equally to the clustering process.

4.  **K-Means Clustering:**
    - Used the **Elbow Method** to determine the optimal number of clusters (K) for the dataset.
    - Applied the K-Means algorithm with the chosen K to assign each customer to a specific segment.

5.  **Segment Analysis & Visualization:**
    - Analyzed the mean RFM values for each cluster to understand their characteristics.
    - Visualized the clusters using boxplots and a 3D scatter plot to illustrate the separation of segments.

## Key Techniques & Libraries
- **Techniques:** RFM Analysis, Unsupervised Learning, K-Means Clustering, Elbow Method.
- **Libraries:**
    - `pandas` for data manipulation.
    - `numpy` for numerical operations.
    - `scikit-learn` for scaling and K-Means modeling.
    - `matplotlib` & `seaborn` for data visualization.

## Results: Customer Segments
The analysis revealed several distinct customer segments (assuming 4 clusters were optimal):

-   **Cluster 0: Best Customers (Champions) 🏆**
    -   **Characteristics:** Low Recency, High Frequency, High Monetary value.
    -   **Insight:** These are the most loyal and profitable customers. They should be nurtured with loyalty programs and exclusive offers.

-   **Cluster 1: At-Risk Customers 😥**
    -   **Characteristics:** High Recency, Low Frequency, Low Monetary value.
    -   **Insight:** These customers have not purchased in a long time and are at risk of churning. They need to be re-engaged with personalized win-back campaigns.

-   **Cluster 2: Potential Loyalists 🌱**
    -   **Characteristics:** Moderate Recency, Moderate Frequency, and Moderate Monetary value.
    -   **Insight:** These customers are consistent but have room to grow. They can be targeted with promotions to increase their purchase frequency.

-   **Cluster 3: New Customers ✨**
    -   **Characteristics:** Low Recency, Low Frequency, Low Monetary value.
    -   **Insight:** Recent buyers with high potential. A good onboarding experience and follow-up communication are key to converting them into loyal customers.


## Future Improvements
-   Explore other clustering algorithms like DBSCAN to handle noise and outliers.
-   Incorporate additional features beyond RFM, such as product categories purchased.
-   Deploy the model as a simple web app to dynamically segment new customers.
