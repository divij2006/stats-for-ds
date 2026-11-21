# Practical 12 - Deterministic Model

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To write the Metropolis algorithm from scratch and then use its samples to work out deterministic quantities. The practical has two parts:

- **Part A:** implement the Metropolis algorithm and check that it works
- **Part B:** calculate quantities that are fixed exactly by the model parameters (mean, variance, standard deviation and a tail probability) and compare them with the real data

## 2. Dataset

`sunspots_1749_2018.csv` (the same data as Practical 11): the monthly mean total sunspot number from January 1749 to November 2018.

- **Size:** 3239 rows (months)

| Variable | Meaning |
|---|---|
| year | Year of the observation |
| month | Month of the observation |
| date | Date as a decimal year |
| sunspots | Monthly mean total sunspot number |

## 3. Approach

1. Wrote a `metropolis()` function that proposes a small random step, accepts it according to the ratio of likelihoods and saves every sample.
2. Tested it on a normal(5, 2) distribution, starting far away at 0, and compared the samples with the true curve.
3. Used the same function on the gamma model of the sunspot counts, starting at a = 4 and b = 10, with 5000 samples and the first 500 dropped as burn-in.
4. For every remaining sample of a and b, calculated:
   - mean = a x b
   - variance = a x b squared
   - standard deviation = square root of a, times b
   - the probability that a month has more than 200 sunspots
5. Summarised each quantity with its average and 95% range, and compared it with the real value in the data.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, SciPy, matplotlib

## 5. Results

**Part A: test on a normal(5, 2) distribution**

| Item | Value |
|---|---|
| Acceptance rate | about 50% |
| Sample mean / standard deviation | 5.02 / 1.99 (true values 5 and 2) |

**Part B: deterministic quantities for the sunspot model**

| Quantity | Model (95% range) | Actual in data |
|---|---|---|
| Mean | 82.3 (79.4 to 85.4) | 82.4 |
| Standard deviation | 83.2 (79.8 to 87.0) | 67.8 |
| P(count > 200) | 8.9% (8.1% to 9.8%) | 6.9% |

The estimates of the parameters were a of about 0.98 and b of about 84, the same as the direct gamma fit.

## 6. Key Takeaways

- The samples of a and b are random, but a quantity like the mean (a x b) is calculated exactly from them, so it is called deterministic.
- Calculating a quantity for every sample gives a whole range of values, which shows how uncertain the estimate is.
- Testing an algorithm on a case with a known answer is a good way to trust it before using it on real data.
- The model matches the average but overestimates the spread and the share of very high months, so the gamma distribution is not a perfect description of the counts.

## 7. Conclusion

The Metropolis algorithm worked on the test distribution and on the sunspot model. The deterministic quantities show that the gamma model gets the average count right (about 82), but its standard deviation and its probability of a very high month are larger than what the data shows.
