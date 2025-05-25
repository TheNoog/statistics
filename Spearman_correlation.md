# Spearman Rank Correlation

Spearman's rank correlation coefficient (often denoted by ρ, rho or r_s) is a non-parametric measure of the monotonicity of the relationship between two datasets. Unlike the Pearson correlation, it assesses how well the relationship between two variables can be described using a monotonic function. If the relationship is perfectly monotonic, the Spearman rank correlation coefficient is +1 or -1.

It is calculated by ranking the data for each variable separately and then applying the Pearson correlation formula to the ranks.

**Formula:**

The formula for Spearman's rank correlation coefficient is:

ρ = 1 - (6 Σd_i²) / (n(n² - 1))

Where:

*   d_i is the difference between the ranks of corresponding values in the two datasets.
*   n is the number of data points.

**Worked Example:**

Let's say we want to determine if there is a monotonic relationship between hours studied and exam score for a group of students.

| Student | Hours Studied (X) | Exam Score (Y) | Rank(X) | Rank(Y) | d_i (Rank(X) - Rank(Y)) | d_i² |
|---------|-------------------|----------------|---------|---------|-------------------------|------|
| A       | 2                 | 50             | 1       | 1       | 0                       | 0    |
| B       | 5                 | 65             | 3       | 3       | 0                       | 0    |
| C       | 4                 | 60             | 2       | 2       | 0                       | 0    |
| D       | 7                 | 75             | 4       | 4       | 0                       | 0    |
| E       | 8                 | 80             | 5       | 5       | 0                       | 0    |

In this simple example, the data is already perfectly monotonically increasing, so the ranks are the same for both variables.

Σd_i² = 0 + 0 + 0 + 0 + 0 = 0
n = 5

ρ = 1 - (6 * 0) / (5 * (5² - 1))
ρ = 1 - 0 / (5 * (25 - 1))
ρ = 1 - 0 / (5 * 24)
ρ = 1 - 0 / 120
ρ = 1 - 0
ρ = 1

A Spearman correlation coefficient of 1 indicates a perfect positive monotonic relationship between hours studied and exam score.

Let's consider a slightly more complex example:

| Student | Hours Studied (X) | Exam Score (Y) | Rank(X) | Rank(Y) | d_i (Rank(X) - Rank(Y)) | d_i² |
|---------|-------------------|----------------|---------|---------|-------------------------|------|
| A       | 2                 | 50             | 1       | 2       | -1                      | 1    |
| B       | 5                 | 65             | 3       | 4       | -1                      | 1    |
| C       | 4                 | 60             | 2       | 3       | -1                      | 1    |
| D       | 7                 | 75             | 4       | 5       | -1                      | 1    |
| E       | 8                 | 68             | 5       | 1       | 4                       | 16   |

First, rank the data for X and Y separately (from lowest to highest).

Σd_i² = 1 + 1 + 1 + 1 + 16 = 20
n = 5

ρ = 1 - (6 * 20) / (5 * (5² - 1))
ρ = 1 - 120 / (5 * (25 - 1))
ρ = 1 - 120 / (5 * 24)
ρ = 1 - 120 / 120
ρ = 1 - 1
ρ = 0

In this case, the Spearman correlation coefficient is 0, indicating no monotonic relationship between hours studied and exam score in this specific dataset. This is because the last data point (E) significantly disrupts the monotonic trend.

Spearman correlation is useful when your data does not meet the assumptions for Pearson correlation (e.g., not normally distributed, non-linear relationship).