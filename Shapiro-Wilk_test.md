# Shapiro-Wilk Test

The Shapiro-Wilk test is a test of normality, used to determine if a dataset is significantly different from a normally distributed dataset. It is considered one of the most powerful normality tests.

**Hypotheses:**

*   **Null Hypothesis (H₀):** The data is normally distributed.
*   **Alternative Hypothesis (H₁):** The data is not normally distributed.

**Interpretation:**

*   If the p-value is greater than the significance level (commonly α = 0.05), you fail to reject the null hypothesis and can assume the data is normally distributed.
*   If the p-value is less than or equal to the significance level (α = 0.05), you reject the null hypothesis and conclude that the data is not normally distributed.

**Worked Example:**

Let's perform a Shapiro-Wilk test on a small dataset to see if it is normally distributed.

Suppose we have the following sample data representing the scores of 10 students on a test:

`[85, 92, 78, 88, 95, 80, 83, 90, 87, 91]`

We will use a statistical software package (like Python with SciPy) to perform the test.
```
python
from scipy.stats import shapiro

data = [85, 92, 78, 88, 95, 80, 83, 90, 87, 91]

stat, p_value = shapiro(data)

print(f"Shapiro-Wilk Statistic: {stat:.4f}")
print(f"P-value: {p_value:.4f}")

alpha = 0.05

if p_value > alpha:
    print("Fail to reject the null hypothesis: The data appears to be normally distributed.")
else:
    print("Reject the null hypothesis: The data does not appear to be normally distributed.")
```
**Explanation of the Output:**

The output will provide the Shapiro-Wilk test statistic and the corresponding p-value.

*   **Shapiro-Wilk Statistic:** This is the test statistic calculated from the data.
*   **P-value:** This is the probability of observing the data (or more extreme data) if the null hypothesis (data is normally distributed) is true.

In this example, let's assume the output is:
```
Shapiro-Wilk Statistic: 0.9680
P-value: 0.8671
```
Since the p-value (0.8671) is greater than our significance level (0.05), we fail to reject the null hypothesis. We can conclude that there is not enough evidence to say that the data is not normally distributed. It appears to be consistent with a normal distribution.

**Important Considerations:**

*   The Shapiro-Wilk test is sensitive to small sample sizes.
*   Visual inspection of the data (e.g., histograms, Q-Q plots) should always accompany formal normality tests.