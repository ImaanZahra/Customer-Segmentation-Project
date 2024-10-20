# Customer-Segmentation-Project
This project implements customer segmentation using clustering techniques, specifically K-Means. The goal is to divide customers into meaningful groups based on their purchase behavior, which can help businesses in targeted marketing strategies.

# Tools & Libraries
Python 3.12.4
Libraries:
pandas: Data manipulation and analysis
numpy: Numerical computations
matplotlib & seaborn: Data visualization
scikit-learn: Machine learning algorithms (K-Means, StandardScaler)

# Dataset
The dataset used is Online Retail dataset, which contains transaction data of an online retail store:

Features: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country
Target: CustomerID is used to segment customers based on their purchasing behavior.

# Key Steps
- Data Preprocessing:
Removed rows with missing customer IDs.
Filtered out negative quantities and prices.
Calculated total price for each transaction.
- Feature Engineering:
Aggregated data by customer, calculating metrics like total spending (monetary value), number of transactions (frequency), and recency of purchases.
- Clustering:
Applied K-Means clustering.
Used the Elbow method and Silhouette score to determine the optimal number of clusters.
reducing feature dimensions and visualizing customer segments.
- Results:
The customers were segmented into X groups based on their purchase history:

Cluster 1: High-spending customers with frequent purchases
Cluster 2: Moderate spenders with fewer purchases
Cluster 3: Low spenders with infrequent purchases

Usage:
You can run the project file to perform customer segmentation on the dataset. The results include visualizations and insights about each customer group.

Future Enhancements
Experiment with different clustering algorithms like DBSCAN.
Incorporate more customer attributes to refine the segmentation.

Contact
For any questions or suggestions, feel free to reach out to me at:

Email: imaanzahra529@gmail.com
LinkedIn: [https://www.linkedin.com/in/imaan-zahra-/]
