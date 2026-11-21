# Practical 05 - Probability and a Two-Tailed Test

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To work with probabilities from a normal distribution and to carry out a two-tailed hypothesis test. The practical covers:

- The probability of an evaluation score above 4.5
- The probability of a score between 3.5 and 4.2
- A two-tailed z-test for the mean points scored by regional basketball players

## 2. Dataset

Questions 1 and 2 use `TeachingRatings.csv` (the `eval` column, 463 values, mean 3.998, standard deviation 0.555).

Question 3 uses the figures given in the question:

| Quantity | Value |
|---|---|
| Historic mean of the pro team | 12 points per game |
| Standard deviation | 5.5 |
| Regional players in the sample | 36 |
| Sample mean | 10.7 points per game |

## 3. Approach

1. Took the mean and standard deviation of `eval` and treated the scores as normally distributed.
2. Used `stats.norm.cdf` to get P(eval > 4.5) and P(3.5 < eval < 4.2), and compared them with the real proportions in the data.
3. Wrote the hypotheses for the basketball question:
   - H0: the mean of the regional players is not different from the historic mean
   - H1: the mean of the regional players is different from the historic mean
4. Calculated the standard error, the z statistic and the two-tailed p-value.
5. Drew the normal curve with the two rejection regions and marked the z value.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, SciPy, matplotlib

## 5. Results

| Question | Normal distribution | Actual in data |
|---|---|---|
| P(eval > 4.5) | 18.3% | 17.1% |
| P(3.5 < eval < 4.2) | 45.7% | 35.4% |

| Two-tailed test | Value |
|---|---|
| Standard error | 0.917 |
| z statistic | -1.418 |
| p-value | 0.156 |
| Decision at 5% | Fail to reject H0 |

## 6. Key Takeaways

- The normal approximation is close for the single cutoff but less accurate for the range, because the real scores are not perfectly normal.
- A two-tailed test checks for a difference in either direction, so the p-value is twice the area in one tail.
- A p-value above 0.05 does not prove the means are equal. It only says the data is not strong enough to show a difference.
- With only 36 players, a gap of 1.3 points is not large compared with the variation between players.

## 7. Conclusion

The normal model describes the evaluation scores reasonably well. For the basketball question, regional players scored lower on average (10.7 against 12), but the difference is not statistically significant, so there is no strong evidence that they score differently from the historic pro mean.
