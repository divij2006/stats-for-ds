# Practical 11 - Monte Carlo and MCMC

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To model monthly sunspot counts with a gamma distribution and estimate its two parameters with MCMC. The practical covers:

- Plotting the sunspot data over time
- Marking a new cycle every 12 years
- A histogram of the counts with a gamma model
- MCMC for the shape `a` and scale `b`, starting at a = 4 and b = 10
- Burn-in, trace plots and histograms of the traces, and the final estimates

## 2. Dataset

`sunspots_1749_2018.csv`: the monthly mean total sunspot number from January 1749 to November 2018, from the World Data Center SILSO.

- **Size:** 3239 rows (months)

| Variable | Meaning |
|---|---|
| year | Year of the observation |
| month | Month of the observation |
| date | Date as a decimal year (used for the time axis) |
| sunspots | Monthly mean total sunspot number |

## 3. Approach

1. Plotted the counts against the year.
2. Added a cycle number and a year-in-cycle column (a new cycle every 144 months).
3. Replaced the 67 months with a count of 0 by 0.1, because a gamma distribution only takes positive values, then fitted a gamma with scipy.
4. Wrote the log likelihood of the gamma model and ran a Metropolis sampler for 5000 samples from a = 4, b = 10.
5. Plotted the first 50 samples, all samples and the last 50 samples.
6. Dropped the first 500 samples as burn-in and plotted the traces and histograms of a and b.
7. Calculated the estimates and 95% ranges from the remaining samples.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy, SciPy, matplotlib

## 5. Results

| Item | Value |
|---|---|
| Average monthly count | 82.39 (standard deviation 67.82, maximum 398.2) |
| Cycles in the data | 23 (the last one is partial) |
| Average by year in cycle | Highest in year 4 (about 102.7), lowest in year 11 (about 61.1) |
| Direct gamma fit | a = 0.979, b = 84.18 |
| MCMC acceptance rate | about 31.5% |
| MCMC estimate of a | 0.979 (95% range 0.938 to 1.019) |
| MCMC estimate of b | 84.16 (95% range 79.86 to 88.78) |
| Predicted average (a x b) | 82.39, equal to the real average |

## 6. Key Takeaways

- The first 50 samples show the chain walking away from the starting values, and the full trace shows it settling after a few hundred samples.
- Burn-in is the early part of the chain that depends on where it started, so it is removed before the estimates.
- A bell-shaped histogram of the trace and a trace with no trend are signs the chain has settled.
- MCMC gives a range for each parameter, not just a single value.

## 7. Conclusion

Monthly sunspot counts follow a gamma distribution with a shape close to 1 and a scale of about 84. The MCMC estimates agree with the direct fit, and the model reproduces the real average count of about 82 sunspots per month.
