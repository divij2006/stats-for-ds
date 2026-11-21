# Practical 06 - T-Tests, ANOVA, and Chi-Square

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To choose and run the right statistical test for each type of question. The practical covers:

- A t-test to compare two group means
- A one-way ANOVA to compare several group means
- A chi-square test for two categorical variables
- A correlation between two numeric variables

## 2. Dataset

`TeachingRatings.csv`: 463 course evaluations.

| Variable | Meaning |
|---|---|
| gender | Male or female |
| eval | Overall teaching evaluation score (1 to 5) |
| beauty | Average beauty rating of the instructor |
| age | Age of the instructor (grouped into four age bands for ANOVA) |
| tenure | Whether the instructor has tenure (yes / no) |

## 3. Approach

1. **T-test:** compared `eval` for male and female instructors with `ttest_ind`.
2. **ANOVA:** grouped age into Under 40, 40-49, 50-59 and 60+, then compared `beauty` across the groups with `f_oneway`.
3. **Chi-square:** built a gender by tenure table and ran `chi2_contingency`.
4. **Correlation:** calculated the Pearson correlation between `eval` and `beauty`.
5. Drew a box plot, a bar chart and a regression scatter plot to support the tests.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, SciPy, matplotlib, seaborn

## 5. Results

| Test | Result | Conclusion |
|---|---|---|
| T-test (gender and eval) | Male 4.07, female 3.90, t = 3.25, p = 0.0012 | Significant difference |
| ANOVA (age group and beauty) | F = 13.81, p about 1e-8 | Beauty differs by age group |
| Chi-square (tenure and gender) | chi-square = 2.21, p = 0.137 | No significant association |
| Correlation (eval and beauty) | r = 0.19, p about 4e-5 | Weak positive relationship |

- Average beauty score falls with age: about 0.34 for those under 40, -0.05 and -0.04 for the 40s and 50s, and -0.42 for 60 and over.
- In the raw numbers 80.6% of male and 74.4% of female instructors are tenured, but the chi-square test says this gap could easily be chance.

## 6. Key Takeaways

- Two groups and a numeric outcome call for a t-test. Three or more groups call for ANOVA. Two categorical variables call for chi-square.
- ANOVA needs groups, so a numeric variable like age has to be binned first.
- A result can be statistically significant and still small. The correlation of 0.19 is real but beauty explains only a small part of the evaluation score.
- A gap in percentages is not automatically meaningful, and the chi-square test is what separates a real pattern from noise.

## 7. Conclusion

Gender and age both show real effects in this data (evaluation scores differ by gender, and beauty scores fall with age). Tenure is not significantly linked to gender, and beauty has only a weak connection to evaluation scores.
