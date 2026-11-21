# Practical 10 - Principal Component Analysis (PCA)

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To explore a dataset with many features and use PCA to reduce it to two components while keeping the classes separated. The practical covers:

- Basic statistics with `describe()`
- A box plot by class and a scatter plot of two variables
- The covariance matrix
- Data scaling
- Showing class separation with principal components

## 2. Dataset

The wine dataset that comes with scikit-learn (`load_wine`), so there is no separate file.

- **Size:** 178 wines x 13 chemical measurements, in 3 classes (59, 71 and 48 wines)

The 13 measurements are alcohol, malic acid, ash, alcalinity of ash, magnesium, total phenols, flavanoids, nonflavanoid phenols, proanthocyanins, color intensity, hue, OD280/OD315 of diluted wines and proline. The target is the wine class (0, 1 or 2).

## 3. Approach

1. Used `describe()` to look at the scale of each feature.
2. Drew box plots of alcohol, flavanoids, color intensity and proline for each class.
3. Drew a scatter plot of flavanoids against color intensity, coloured by class.
4. Plotted the covariance matrix as an annotated heatmap.
5. Scaled the features with `StandardScaler`.
6. Ran `PCA(n_components=2)` on the scaled data and plotted the two components coloured by class.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, scikit-learn, matplotlib, seaborn

## 5. Results

| Item | Value |
|---|---|
| Variance of proline | about 99,167 |
| Variance of hue | about 0.05 |
| Average flavanoids (class 0 / 1 / 2) | 2.98 / 2.08 / 0.78 |
| Average proline (class 0 / 1 / 2) | 1116 / 520 / 630 |
| Variance kept by PC1 and PC2 | 36.2% and 19.2% (55.4% together) |

- Flavanoids and proline separate the classes best. Alcohol overlaps more.
- In the scatter plot class 2 sits apart, while classes 0 and 1 overlap a little.
- In the PCA plot the three classes form clearly separate groups with only a few points overlapping.

## 6. Key Takeaways

- The covariance matrix is dominated by proline because its numbers are so much bigger, so scaling is essential before PCA.
- PCA finds the directions with the most variance. Without scaling it would simply follow the biggest-scale feature.
- Two components keep only about 55% of the information, yet they separate the classes better than any two original features I plotted.
- PCA is a way to see high-dimensional data on a flat plot.

## 7. Conclusion

The wine features are on very different scales, so scaling came first. After that, two principal components were enough to show the three wine classes clearly on one graph.
