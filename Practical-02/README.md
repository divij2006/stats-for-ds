# Practical 02 - Statistics Foundations with a Rating Dataset

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To practise the basic statistics workflow on a real dataset. The practical covers:

- Deciding whether a dataset is time series or cross-sectional
- Mean, median, minimum and maximum of a variable
- A full descriptive statistics table
- A histogram and a comment on the shape of the data
- Comparing groups (male and female instructors) using means and standard deviations

## 2. Dataset

The teaching ratings dataset (`TeachingRatings.csv`) holds course evaluations of professors at the University of Texas at Austin (Hamermesh and Parker study).

- **Size:** 463 rows x 13 columns (463 courses taught by 94 instructors)

| Variable | Meaning |
|---|---|
| age | Age of the instructor |
| gender | Male or female |
| beauty | Average beauty rating of the instructor, shifted so the mean is 0 |
| eval | Overall teaching evaluation score (1 to 5) |
| tenure | Whether the instructor has tenure (yes / no) |
| students | Number of students who filled in the evaluation |
| allstudents | Number of students enrolled in the course |

## 3. Approach

1. Loaded the CSV into a pandas DataFrame and checked its shape, columns and data types.
2. Checked how the rows are organised to decide between time series and cross-sectional data.
3. Used `agg()` to get the mean, median, min and max of `students`.
4. Built a descriptive statistics table for age, beauty, eval, students and allstudents using `describe()`.
5. Plotted a histogram of `beauty` with matplotlib.
6. Used `groupby("gender")` to get the mean and standard deviation of beauty for each gender.
7. Used `value_counts(normalize=True)` to get the percentage of tenured instructors.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, matplotlib, seaborn

## 5. Results

| Question | Result |
|---|---|
| Type of data | Cross-sectional (different courses and instructors, no time dimension) |
| Students per course | Mean 36.62, median 23, minimum 5, maximum 380 |
| Age | Mean 48.37, standard deviation 9.80 |
| Evaluation score | Mean 4.00, standard deviation 0.55 (range 2.1 to 5.0) |
| Beauty by gender | Female 0.116 (sd 0.818), male -0.084 (sd 0.757) |
| Tenure | 77.97% tenured, 22.03% not tenured |

- The beauty histogram is roughly bell shaped with a mild right skew (skewness about 0.5).
- Female instructors have a slightly higher average beauty score than male instructors.
- Male instructors are tenured a little more often than female instructors (about 80.6% against 74.4%). The gap is small and is tested properly in Practical 6.

## 6. Key Takeaways

- Each row is one course, not one instructor, so the data is a snapshot of many units and not a series over time.
- When the mean (36.62) is far above the median (23), a few very large classes are pulling the average up.
- `describe()` and `groupby()` answer most first-look questions about a dataset in a few lines.
- The beauty score is already standardised, so its mean of about 0 is by construction and says nothing about the instructors.

## 7. Conclusion

This practical set up the basic habits used in every later practical: look at the structure first, summarise with a few numbers, plot the shape, then compare groups. The ratings data is cross-sectional, class sizes are heavily right skewed, and the gender differences in beauty score and tenure are small.
