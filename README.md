# Statistics for Data Science - Practicals

![Python](https://img.shields.io/badge/Python-3-blue) ![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange) ![Practicals](https://img.shields.io/badge/Practicals-12-green)

A collection of 12 practicals for the Statistics for Data Science course, done in Python with Jupyter notebooks. They go from data handling and descriptive statistics to hypothesis testing, regression, machine learning models (decision trees, KNN, PCA) and MCMC sampling.

Every practical has its own folder with the notebook and a README that explains the exercise. The notebooks are saved with their outputs, so the results can be read directly on GitHub.

## Author

| | |
|---|---|
| **Submitted by** | Divij Grack |
| **GitHub** | [divij2006](https://github.com/divij2006) |

## Practicals

| No. | Topic | Dataset | Main techniques | Links |
|---|---|---|---|---|
| 01 | Revisiting Pandas and NumPy | See practical README | Pandas and NumPy basics | [README](Practical-01/README.md) · [Notebook](Practical-01/Practical_01.ipynb) |
| 02 | Statistics Foundations with a Rating Dataset | TeachingRatings | Summary statistics, histogram, group comparison | [README](Practical-02/README.md) · [Notebook](Practical-02/Practical_02.ipynb) |
| 03 | Descriptive Statistics | TeachingRatings | Descriptive statistics, choosing graphs | [README](Practical-03/README.md) · [Notebook](Practical-03/Practical_03.ipynb) |
| 04 | Understanding Data with Graphs | TeachingRatings | Duplicates, bar chart, age vs evaluation | [README](Practical-04/README.md) · [Notebook](Practical-04/Practical_04.ipynb) |
| 05 | Probability and a Two-Tailed Test | TeachingRatings | Normal probabilities, two-tailed z-test | [README](Practical-05/README.md) · [Notebook](Practical-05/Practical_05.ipynb) |
| 06 | T-Tests, ANOVA, and Chi-Square | TeachingRatings | T-test, ANOVA, chi-square, correlation | [README](Practical-06/README.md) · [Notebook](Practical-06/Practical_06.ipynb) |
| 07 | Regression, T-Tests, and ANOVA | TeachingRatings | OLS regression, ANOVA table | [README](Practical-07/README.md) · [Notebook](Practical-07/Practical_07.ipynb) |
| 08 | Decision Trees and Maximum Depth | Pima Indians Diabetes | Decision tree, entropy, information gain, Gini index | [README](Practical-08/README.md) · [Notebook](Practical-08/Practical_08.ipynb) |
| 09 | K-Nearest Neighbors (KNN) | Iris | Feature scaling, confusion matrix, choosing K | [README](Practical-09/README.md) · [Notebook](Practical-09/Practical_09.ipynb) |
| 10 | Principal Component Analysis (PCA) | Wine | Covariance matrix, scaling, PCA | [README](Practical-10/README.md) · [Notebook](Practical-10/Practical_10.ipynb) |
| 11 | Monte Carlo and MCMC | Sunspots | Gamma model, MCMC, burn-in | [README](Practical-11/README.md) · [Notebook](Practical-11/Practical_11.ipynb) |
| 12 | Deterministic Model | Sunspots | Metropolis algorithm, deterministic quantities | [README](Practical-12/README.md) · [Notebook](Practical-12/Practical_12.ipynb) |

## Repository structure

```text
stats-for-ds/
├── Practical-01/
│   ├── Practical_01.ipynb
│   └── README.md
├── Practical-02/
│   ├── Practical_02.ipynb
│   └── README.md
├── ...                         (one folder per practical, up to Practical-12)
├── TeachingRatings.csv
├── StudentRatingData.csv
├── diabetes.csv
├── sunspots_1749_2018.csv
└── README.md
```

## Data files

CSV files are kept in the repository root. The notebooks read them with a relative path from their practical folder (for example `../TeachingRatings.csv`).

| File | Used in | Description |
|---|---|---|
| `TeachingRatings.csv` | Practicals 02-07 | Course evaluations of 463 courses (94 instructors) at the University of Texas at Austin |
| `StudentRatingData.csv` | Additional | Additional student ratings dataset |
| `diabetes.csv` | Practical 08 | Pima Indians Diabetes dataset (768 patients) |
| `sunspots_1749_2018.csv` | Practicals 11 and 12 | Monthly mean total sunspot number, January 1749 to November 2018 (3,239 months) |

Practicals 09 and 10 use the Iris and Wine datasets included with scikit-learn, so they have no separate file.

## Tools

- Python 3 and Jupyter Notebook
- pandas and NumPy
- Matplotlib and Seaborn
- SciPy and statsmodels
- scikit-learn
