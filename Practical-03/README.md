# Practical 03 - Descriptive Statistics

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To use descriptive statistics and simple plots to compare groups in the ratings data. The practical covers:

- Tenure rate for visible minority and other instructors
- Average age for tenured and untenured instructors
- Choosing the right graph for a continuous variable (age)
- The difference between `plt.bar` and `plt.barh`, with a plot of gender
- The median evaluation score of tenured instructors

## 2. Dataset

`TeachingRatings.csv`: 463 course evaluations from the University of Texas at Austin.

| Variable | Meaning |
|---|---|
| minority | Whether the instructor is a visible minority (yes / no) |
| age | Age of the instructor |
| gender | Male or female |
| tenure | Whether the instructor has tenure (yes / no) |
| eval | Overall teaching evaluation score (1 to 5) |

## 3. Approach

1. Built a cross-tab of `minority` against `tenure` and converted it to row percentages.
2. Grouped by `tenure` and calculated the mean and standard deviation of `age`.
3. Plotted `age` as a histogram because it is a continuous variable.
4. Counted instructors by gender and drew a bar chart.
5. Filtered the tenured instructors and took the median of `eval`.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, matplotlib, seaborn

## 5. Results

| Question | Result |
|---|---|
| Tenured among visible minorities | 84.4% (54 of 64) |
| Tenured among other instructors | 76.9% (307 of 399) |
| Mean age, tenured | 47.85 (sd 10.42) |
| Mean age, not tenured | 50.19 (sd 6.95) |
| Instructors by gender | 268 male, 195 female |
| Median evaluation, tenured | 4.0 |

- Tenure status does differ by minority status in this sample, by about 7 percentage points in favour of visible minorities. The minority group is small (64 instructors), so this should be read with care.
- Tenured instructors are slightly younger on average than untenured ones, and the untenured group has a much narrower age spread.

## 6. Key Takeaways

- A histogram suits continuous data such as age because it groups values into bins. A bar chart is for a small set of categories such as gender.
- `plt.bar()` draws vertical bars and `plt.barh()` draws horizontal bars. Both show the same information, and `barh` is handy when category names are long.
- Row percentages from `pd.crosstab(..., normalize="index")` make groups of different sizes easy to compare.
- The median is a better "typical" value when the data is not symmetric.

## 7. Conclusion

Tenure rates differ between minority and other instructors, though the small minority group limits how strong that statement can be. Age differs a little by tenure status, and tenured instructors still have a median evaluation of 4 out of 5.
