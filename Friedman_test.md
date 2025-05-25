# Friedman Test

The Friedman test is a non-parametric statistical test used to detect differences in treatments across multiple test attempts. It is an alternative to the repeated measures ANOVA when the assumptions of ANOVA are not met, specifically the assumption of normality. It is used when you have three or more groups (treatments) and the observations within each group are paired or related (e.g., the same subjects are exposed to all treatments).

The null hypothesis (H₀) for the Friedman test is that the median values of the different groups are the same. The alternative hypothesis (H₁) is that at least one of the group medians is different from the others.

The test works by ranking the observations within each block (or subject). If the null hypothesis is true, the average ranks for each treatment should be roughly the same. A large difference in the average ranks leads to a large test statistic, which suggests rejecting the null hypothesis.

## Worked Example

Let's say we have 5 participants who are asked to rate the perceived effectiveness of three different study methods (A, B, and C) on a scale of 1 to 10. Each participant tries all three methods.

| Participant | Method A | Method B | Method C |
|-------------|----------|----------|----------|
| 1           | 7        | 8        | 6        |
| 2           | 5        | 6        | 4        |
| 3           | 9        | 7        | 8        |
| 4           | 6        | 7        | 5        |
| 5           | 8        | 9        | 7        |

Now, we rank the scores for each participant across the three methods.

| Participant | Method A Rank | Method B Rank | Method C Rank |
|-------------|---------------|---------------|---------------|
| 1           | 2             | 3             | 1             |
| 2           | 2             | 3             | 1             |
| 3           | 3             | 1             | 2             |
| 4           | 2             | 3             | 1             |
| 5           | 2             | 3             | 1             |

Next, we calculate the sum of the ranks for each method:

*   Sum of Ranks for Method A (Rᴀ) = 2 + 2 + 3 + 2 + 2 = 11
*   Sum of Ranks for Method B (Rʙ) = 3 + 3 + 1 + 3 + 3 = 13
*   Sum of Ranks for Method C (Rᴄ) = 1 + 1 + 2 + 1 + 1 = 6

The formula for the Friedman test statistic (χ²ᵣ) is:

χ²ᵣ = [(12 / (Nk(k+1))) * Σ(Rᵢ)²] - 3N(k+1)

Where:
*   N = Number of blocks (participants) = 5
*   k = Number of treatments (methods) = 3
*   Rᵢ = Sum of ranks for the i-th treatment

Plugging in the values:

χ²ᵣ = [(12 / (5 * 3 * (3 + 1))) * (11² + 13² + 6²)] - 3 * 5 * (3 + 1)
χ²ᵣ = [(12 / (5 * 3 * 4)) * (121 + 169 + 36)] - 3 * 5 * 4
χ²ᵣ = [(12 / 60) * 326] - 60
χ²ᵣ = [0.2 * 326] - 60
χ²ᵣ = 65.2 - 60
χ²ᵣ = 5.2

To determine statistical significance, we compare this calculated χ²ᵣ value to a critical value from the chi-square distribution with k-1 degrees of freedom. In this case, the degrees of freedom are 3 - 1 = 2.

Looking up the critical chi-square value for a significance level of 0.05 with 2 degrees of freedom, we find it to be 5.991.

Since our calculated χ²ᵣ (5.2) is less than the critical value (5.991), we fail to reject the null hypothesis.

**Conclusion:** Based on this analysis, there is not enough statistically significant evidence to conclude that there is a difference in the perceived effectiveness of the three study methods at the 0.05 significance level.