# Customer-Segmentation-of-an-E-commerce-data-set-from-a-real-world-organisation

## Background
Understanding customers is central to effective retail marketing. This project uses global e-commerce transaction data from a real-world organisation to group customers by purchasing behaviour, so that marketing campaigns, retention efforts and resources can be targeted more effectively.

## Objective
Build an unsupervised learning pipeline that segments customers into distinct behavioural groups, covering data cleaning, feature engineering, clustering with **K-means** and **hierarchical clustering**, and interpretation of each segment.

## Data
- ~950,000 transaction rows (20 columns), aggregated to **68,300 customers**
- Engineered features: **frequency, recency, customer lifetime value (CLV), average unit cost and customer age**
- The dataset is **not included** in this repository due to licensing. It was provided as part of the University of Cambridge / FourthRev Data Science course.

## Approach
1. **Pre-processing:** removed exact duplicates, handled missing location data, cleaned discount, date and currency formats
2. **Feature engineering:** aggregated transactions to one row per customer
3. **Scaling:** StandardScaler applied to the engineered features
4. **Choosing k:** elbow method, silhouette scores and a Ward dendrogram
5. **Clustering:** K-means (k = 6), compared with hierarchical clustering
6. **Interpretation:** box plots of features by cluster, with PCA and t-SNE visualisations

## Key outcomes
- K-means with **k = 6** produced distinct, interpretable behavioural profiles for targeted marketing. The choice was supported by the elbow, a silhouette score of **0.24**, and a Ward dendrogram consistent with six branches.
- PCA and t-SNE showed the segments, but clusters overlap rather than forming isolated groups, suggesting customer behaviour varies continuously.
- A small, high-value cluster (~785 customers, ~1%) has the highest CLV and unit cost. It exists because extreme values were kept rather than removed as outliers, which matters because these may be the most valuable customers.
- CLV and average unit cost are strongly correlated (r = 0.73), so spending level may have carried more weight in the clustering than other features.

## Next steps
- Test cluster robustness by removing one of the correlated features
- Explore additional features that may influence customer behaviour

## Skills demonstrated
- **Data cleaning and feature engineering:** turned raw transaction records into customer-level behavioural features
- **Unsupervised machine learning:** applied and compared K-means and hierarchical clustering
- **Model evaluation:** used elbow, silhouette and dendrogram evidence to choose and justify k
- **Dimensionality reduction and visualisation:** used PCA and t-SNE to explore cluster structure
- **Critical interpretation:** assessed cluster overlap, outliers and feature correlation, and their effect on results
- **Business communication:** translated cluster profiles into marketing-relevant insights

## Tools
Python · pandas · NumPy · scikit-learn · matplotlib · seaborn · Google Colab
