# Practical 07 - Regression, T-Tests, and ANOVA

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To see that the t-test, ANOVA and correlation from Practical 6 are all special cases of regression. The practical covers:

- A regression with a 0/1 gender variable, which gives the same answer as a t-test
- A regression with age groups, summarised as an ANOVA table
- A simple regression of evaluation score on beauty score, which is the correlation question

## 2. Dataset

`TeachingRatings.csv`: 463 course evaluations.

| Variable | Meaning |
|---|---|
| eval | Overall teaching evaluation score (1 to 5) |
| gender | Male or female (converted to a 0/1 variable `female`) |
| beauty | Average beauty rating of the instructor |
| age | Age of the instructor (grouped for the ANOVA) |

## 3. Approach

1. Created a `female` variable (1 for female, 0 for male) and fitted `eval ~ female` with OLS from statsmodels.
2. Grouped age into age groups and fitted `beauty ~ age_group`, then produced the ANOVA table with `anova_lm`.
3. Fitted `eval ~ beauty` with OLS and read the slope, R-squared and F-test.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, statsmodels

## 5. Results

| Model | Key numbers |
|---|---|
| eval ~ female | Constant 4.069, female coefficient -0.168 (p = 0.001), R-squared 0.022, F = 10.56 |
| beauty ~ age group (ANOVA) | 2 degrees of freedom, F about 17.6, p about 4e-8 |
| eval ~ beauty | Constant 3.998, beauty coefficient 0.133 (p < 0.001), R-squared 0.036, F = 17.08 |

- The constant of 4.069 is the average evaluation of male instructors, and female instructors score about 0.17 lower.
- Each extra point of beauty score adds about 0.13 to the predicted evaluation score.

## 6. Key Takeaways

- A t-test is a regression on a 0/1 variable. The p-value of the coefficient matches the t-test p-value from Practical 6.
- ANOVA is a regression on group labels, and its F-test asks whether the groups explain any of the variation.
- A low R-squared (0.022 and 0.036) means the effects are real but explain only a small share of the differences in scores.
- Reading the regression summary (coefficient, standard error, t, p-value, R-squared) is the main skill in this practical.

## 7. Conclusion

Regression gives the same conclusions as the separate tests in Practical 6: gender has a small but significant effect on evaluation score, beauty differs by age group, and beauty is weakly but significantly related to evaluation. The advantage is that one framework handles all three questions.
