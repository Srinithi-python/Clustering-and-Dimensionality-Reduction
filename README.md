# Assignment 08 – Clustering and Dimensionality Reduction

## Project Overview
This project explores customer segmentation using clustering algorithms and dimensionality-reduction techniques on the **Mall Customer Spend** dataset. It compares different clustering approaches, visualizes customer patterns, and derives business recommendations from customer segments.

## Dataset
- **File:** `mall_customer_spend.xlsx`
- **Source:** [GitHub dataset](https://github.com/Srinithi-python/Clustering-and-Dimensionality-Reduction)
- **Key features used:** `Annual Income (k$)` and `Spending Score (1-100)`, along with numerical features selected for clustering in the preprocessing workflow.
- `CustomerID` is excluded from clustering features because it is an identifier rather than a meaningful customer measurement.

## Objectives
- Explore the dataset structure, columns, data types, and missing values.
- Encode categorical data such as `Genre` where needed.
- Prepare and standardize numerical features.
- Apply K-Means clustering and examine the effect of random initialization.
- Use the Elbow Method to help select the number of clusters.
- Apply Agglomerative Hierarchical Clustering and inspect a dendrogram.
- Apply DBSCAN to identify dense groups and potential noise points.
- Compare clustering results.
- Reduce dimensionality with PCA and t-SNE for visualization.
- Profile customer groups and suggest business actions.

## Technologies and Libraries
- Python
- pandas and NumPy
- Matplotlib and Seaborn
- scikit-learn
- SciPy
- Jupyter Notebook

## Workflow
1. **Data exploration and preprocessing** — load the Excel dataset, inspect its shape and columns, check data types and missing values, encode `Genre`, select numerical features, handle missing numeric values using medians, and standardize features with `StandardScaler`.
2. **K-Means clustering** — fit a model with three clusters, inspect cluster sizes and centers, compare random initialization seeds, and plot inertia using the Elbow Method.
3. **Hierarchical clustering** — create a Ward-linkage dendrogram and apply Agglomerative Clustering with three clusters.
4. **DBSCAN** — cluster standardized data with `eps=0.5` and `min_samples=5`, identify noise points (label `-1`), and compare results with the other algorithms.
5. **Dimensionality reduction** — use PCA to create two principal components and report explained variance; use t-SNE to create a two-dimensional visualization.
6. **Cluster interpretation** — summarize cluster characteristics, identify customer segments based on income and spending, and map segments to business recommendations.

## How to Run
1. Clone or download this repository.
2. Open `Assignment_08_Clustering_and_Dimensionality_Reduction.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.
3. Install the dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn scipy openpyxl jupyter
   ```
4. Run the notebook cells from top to bottom. The notebook reads the Excel dataset from the GitHub raw URL, so an internet connection is required unless the dataset URL is changed to a local file path.

## Methods at a Glance

| Method | Purpose |
|---|---|
| K-Means | Partitions customers into a specified number of clusters |
| Elbow Method | Helps assess a suitable cluster count using inertia (WCSS) |
| Agglomerative Hierarchical Clustering | Builds nested groups and can be inspected with a dendrogram |
| DBSCAN | Finds density-based clusters and marks noise points |
| PCA | Projects data into components that capture as much variance as possible |
| t-SNE | Creates a low-dimensional visualization emphasizing local similarities |

## Expected Outputs
- Dataset summary and preprocessing checks
- K-Means cluster labels, sizes, centers, and inertia plot
- Random-initialization comparison and Elbow plot
- Hierarchical dendrogram and cluster-size comparison
- DBSCAN cluster/noise counts and visualization
- PCA explained-variance results and scatter plot
- t-SNE scatter plot
- Cluster profiles, customer segment labels, and business recommendations

## Business Applications
Customer segments can support:
- Personalized marketing and promotions
- Loyalty programs for high-value customers
- Bundles and value offers for budget-conscious customers
- Targeted campaigns to increase engagement among lower-spending customers

Segment labels and recommendations should be based on the actual cluster profile outputs from the notebook rather than cluster numbers alone.

## Notes
- Cluster IDs (such as `0`, `1`, and `2`) are arbitrary and may differ across algorithms or runs.
- Standardization is important because clustering methods are sensitive to feature scale.
- PCA and t-SNE are visualization and dimensionality-reduction tools; visual separation alone does not prove that clusters are meaningful.
- DBSCAN results depend on parameters such as `eps` and `min_samples`.
- The notebook's final cluster count is set to three; review the Elbow plot and evaluation metrics before treating this as the best choice.

## Author
**Srinithi**
