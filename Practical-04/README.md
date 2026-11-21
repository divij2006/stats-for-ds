# Practical 04 - Understanding Data with Graphs

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To find duplicated records and to study how teaching evaluation scores relate to division and age. The practical covers:

- Finding duplicate instructors with the `prof` column
- Comparing age statistics before and after keeping one row per instructor
- A bar chart of average evaluation by course division
- The relationship between age and evaluation score, overall, by gender and by gender with tenure

## 2. Dataset

`TeachingRatings.csv` (same as Practical 2): 463 rows, one per course, covering 94 instructors.

| Variable | Meaning |
|---|---|
| prof | Instructor ID, repeated if the instructor taught several courses |
| age | Age of the instructor |
| division | Course level (lower or upper division) |
| eval | Overall teaching evaluation score (1 to 5) |
| gender | Male or female |
| tenure | Whether the instructor has tenure (yes / no) |

## 3. Approach

1. Counted repeated `prof` values with `duplicated()` and `nunique()`.
2. Calculated the mean and standard deviation of age using all rows, then again after `drop_duplicates(subset="prof")`.
3. Grouped by `division` and drew a bar chart of the mean evaluation.
4. Measured how age and evaluation move together (correlation) for all instructors.
5. Repeated this for each gender, and for each gender and tenure combination.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, matplotlib

## 5. Results

| Question | Result |
|---|---|
| Duplicate rows | 369 (only 94 different instructors in 463 rows) |
| Age, all rows | Mean 48.37, standard deviation 9.80 |
| Age, one row per instructor | Mean 47.55, standard deviation 10.26 |
| Evaluation, lower division | 4.09 |
| Evaluation, upper division | 3.95 |
| Age and evaluation, everyone | Correlation about -0.05 |
| Female / male instructors | About -0.21 / -0.04 |

- By gender and tenure the relationship is negative but weak in every group, and strongest for female instructors without tenure (about -0.26).
- Male instructors without tenure have the highest average evaluation (about 4.40), from only 52 courses.

## 6. Key Takeaways

- Repeated rows give some instructors extra weight, so the same statistic can change when each person is counted once.
- Lower-division courses score a little higher than upper-division ones, but the difference is only about 0.13 points.
- A correlation close to 0 means there is almost no straight-line relationship, even if a few groups look different.
- Splitting a dataset into smaller groups makes each result less reliable because there are fewer rows behind it.

## 7. Conclusion

The dataset is really 94 instructors teaching 463 courses. Lower-division courses are rated slightly higher, and age has almost no link to evaluation scores overall. The link is a little stronger for female instructors, but it stays weak.
