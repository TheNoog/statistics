# Sign Test

The Sign Test is a non-parametric test used to compare two related samples or to compare a sample to a hypothesized median. It is a simple alternative to the paired t-test or Wilcoxon signed-rank test when the assumptions of those tests are not met (e.g., data is not normally distributed or is ordinal).

The test works by looking at the differences between pairs of observations and recording the direction (sign) of the difference. Differences of zero are typically ignored. The test then examines whether the number of positive and negative differences is significantly different from what would be expected by chance (assuming the null hypothesis that the median difference is zero).

**Assumptions:**

*   The data consists of paired observations.
*   The observations within each pair are related.
*   The measurement scale is at least ordinal.

**Hypotheses:**

*   **Null Hypothesis (H0):** The median difference between the pairs is zero (or the median of the differences is zero).
*   **Alternative Hypothesis (H1):** The median difference is not zero (two-sided), or the median difference is greater than zero (one-sided), or the median difference is less than zero (one-sided).

**Procedure:**

1.  Calculate the difference between each pair of observations.
2.  Record the sign (+ or -) of each difference. Ignore differences of zero.
3.  Count the number of positive signs ($n_+$) and the number of negative signs ($n_-$).
4.  Let $N$ be the total number of non-zero differences ($N = n_+ + n_-$).
5.  Under the null hypothesis, the probability of getting a positive sign is 0.5, and the probability of getting a negative sign is 0.5.
6.  The number of positive signs (or negative signs) follows a binomial distribution B($N$, 0.5) under the null hypothesis.
7.  Calculate the p-value based on this binomial distribution. For a two-sided test, the p-value is twice the probability of observing a number of positive signs as extreme as or more extreme than the observed number.

**Worked Example:**

A researcher wants to test if a new training program improves the scores of employees on a standardized test. They recruit 10 employees and record their scores before and after the training.

| Employee | Score Before | Score After | Difference (After - Before) | Sign |
| :------- | :----------- | :---------- | :-------------------------- | :--- |
| 1        | 75           | 80          | 5                           | +    |
| 2        | 88           | 91          | 3                           | +    |
| 3        | 65           | 68          | 3                           | +    |
| 4        | 92           | 90          | -2                          | -    |
| 5        | 78           | 85          | 7                           | +    |
| 6        | 80           | 80          | 0                           | (Ignored) |
| 7        | 70           | 73          | 3                           | +    |
| 8        | 85           | 87          | 2                           | +    |
| 9        | 60           | 62          | 2                           | +    |
| 10       | 95           | 98          | 3                           | +    |

**Calculations:**

1.  Differences are calculated in the table.
2.  Signs are recorded in the table.
3.  There are 9 non-zero differences ($N=9$).
4.  Number of positive signs ($n_+$) = 8.
5.  Number of negative signs ($n_-$) = 1.

We want to test if the median difference is greater than zero (one-sided test), suggesting the training improved scores.

Under the null hypothesis, $n_+$ follows B(9, 0.5). We want to find the probability of getting 8 or more positive signs.

P(X ≥ 8) for X ~ B(9, 0.5) = P(X=8) + P(X=9)

P(X=k) = C(n, k) * p^k * (1-p)^(n-k)

P(X=8) = C(9, 8) * 0.5^8 * 0.5^1 = 9 * 0.00390625 * 0.5 = 0.017578125
P(X=9) = C(9, 9) * 0.5^9 * 0.5^0 = 1 * 0.001953125 * 1 = 0.001953125

P(X ≥ 8) = 0.017578125 + 0.001953125 = 0.01953125

The p-value for the one-sided test is approximately 0.0195.

**Conclusion:**

Assuming a significance level (α) of 0.05, the p-value (0.0195) is less than α. Therefore, we reject the null hypothesis and conclude that there is sufficient evidence to suggest that the new training program significantly improves the employees' test scores.