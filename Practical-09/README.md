# Practical 09 - K-Nearest Neighbors (KNN)

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To build a K-Nearest Neighbors classifier and choose a good value of K. The practical covers:

- Exploring the data with `head()`, `describe()` and `groupby()`
- Feature scaling
- Training the model and checking a confusion matrix, accuracy and classification report
- Comparing the error rate for different values of K and finding the best K

## 2. Dataset

The iris dataset that comes with scikit-learn (`load_iris`), so there is no separate file.

- **Size:** 150 flowers x 4 measurements, in 3 species with 50 flowers each

| Variable | Meaning |
|---|---|
| sepal length (cm) | Length of the sepal |
| sepal width (cm) | Width of the sepal |
| petal length (cm) | Length of the petal |
| petal width (cm) | Width of the petal |
| species | Target: setosa, versicolor or virginica |

## 3. Approach

1. Looked at the data and compared the species with `groupby("species").mean()`.
2. Split the data 80/20 (120 training and 30 test flowers) and scaled the features with `StandardScaler`, fitting the scaler on the training data only.
3. Trained `KNeighborsClassifier` with K = 5.
4. Checked the confusion matrix, accuracy and classification report.
5. Calculated the error rate for K from 1 to 25 and plotted it.
6. Picked the best K from the odd values (odd values avoid ties in the vote).

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, scikit-learn, matplotlib, seaborn

## 5. Results

| Item | Value |
|---|---|
| Accuracy with K = 5 | 93.3% (2 virginica flowers predicted as versicolor) |
| Lowest error rate | 3.3%, reached by several K values |
| Best K chosen | 13 |
| Accuracy with K = 13 | 96.7% (29 of 30 test flowers correct) |

- Setosa is classified correctly every time.
- The error rate stays between about 3% and 7% for most K values and rises to 10% at K = 24 and 25.

## 6. Key Takeaways

- KNN works on distances, so features must be on the same scale or the largest numbers dominate.
- A very small K reacts to single noisy points, and a very large K blurs the boundaries between classes.
- Many values of K can tie for the best error rate, so I took the middle of the tied values rather than K = 1.
- Versicolor and virginica have similar measurements, and that is where nearly all the mistakes happen.

## 7. Conclusion

KNN classifies the iris species very well. After scaling, the model reaches about 93% accuracy with K = 5 and about 97% with the best K of 13. The only confusion is between versicolor and virginica.
