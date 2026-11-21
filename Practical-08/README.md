# Practical 08 - Decision Trees and Maximum Depth

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To build a decision tree classifier with scikit-learn and explain why it chooses its root node. The practical covers:

- Splitting the columns into a target variable and feature variables
- Splitting the data into training and test sets
- Building and visualising a decision tree
- Calculating entropy, information gain and the Gini index for the root node

## 2. Dataset

The Pima Indians Diabetes dataset (`diabetes.csv`).

- **Size:** 768 rows x 9 columns (500 without diabetes, 268 with diabetes)

| Variable | Meaning |
|---|---|
| Pregnancies | Number of times pregnant |
| Glucose | Plasma glucose concentration |
| BloodPressure | Diastolic blood pressure (mm Hg) |
| SkinThickness | Skin fold thickness (mm) |
| Insulin | 2-hour serum insulin |
| BMI | Body mass index |
| DiabetesPedigreeFunction | Family history score for diabetes |
| Age | Age in years |
| Outcome | Target: 1 = diabetes, 0 = no diabetes |

## 3. Approach

1. Set `Outcome` as the target (y) and the other eight columns as features (X).
2. Split the data 80/20 into 614 training rows and 154 test rows.
3. Trained `DecisionTreeClassifier(criterion="entropy", max_depth=3)`.
4. Checked accuracy, the confusion matrix and the classification report.
5. Plotted the tree with `plot_tree`.
6. Calculated entropy, information gain and the Gini index by hand for the root split.
7. Plotted the feature importances.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, scikit-learn, matplotlib, seaborn

## 5. Results

| Item | Value |
|---|---|
| Root node | Glucose <= 127.5 (390 training rows on the left, 224 on the right) |
| Entropy before the split | 0.931 |
| Entropy after the split (weighted) | 0.804 |
| Information gain | 0.128 |
| Gini before / after the split | 0.453 / 0.373 (gain 0.080) |
| Test accuracy | 76.6% |

Feature importance: Glucose 0.525, BMI 0.298, Age 0.176, and 0 for the rest.

## 6. Key Takeaways

- The tree picks the split with the biggest drop in impurity. Glucose gives the largest information gain, which is why it sits at the root.
- Entropy and the Gini index measure how mixed the classes are. Both agree on the root node here.
- `max_depth` controls how complicated the tree can get. A shallow tree is easier to read and less likely to overfit, but may miss some patterns.
- Accuracy alone is not enough. The confusion matrix shows which kind of mistakes the model makes.

## 7. Conclusion

A decision tree with a depth of 3 predicts diabetes with about 77% accuracy on unseen data. Glucose is the most important feature by a wide margin, followed by BMI and age, which agrees with the medical idea that blood sugar is the main sign of diabetes.
