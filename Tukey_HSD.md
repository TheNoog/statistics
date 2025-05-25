# Tukey's Honestly Significant Difference (HSD) Post-Hoc Test

Tukey's HSD is a post-hoc test used after a significant ANOVA result to determine which specific group means are significantly different from each other. It controls the family-wise error rate, which is the probability of making at least one Type I error (rejecting a true null hypothesis) when conducting multiple comparisons.

## When to Use

Use Tukey's HSD only after a one-way ANOVA has shown a statistically significant difference among the group means.

## Assumptions

*   The data within each group are approximately normally distributed.
*   The variances of the data in each group are roughly equal (homogeneity of variances).
*   The observations are independent.

## Procedure

1.  Calculate the ANOVA and obtain a significant p-value.
2.  Calculate the studentized range statistic (q) for each pair of group means.
3.  Compare the calculated q value to a critical q value from a studentized range distribution table, taking into account the number of groups and the degrees of freedom from the ANOVA's error term.
4.  Alternatively, many statistical software packages directly provide the p-values for each pairwise comparison using Tukey's HSD.

## Formula (Conceptual)

The formula for the Tukey-Kramer method (which is used when sample sizes are unequal, and is often the default in software) is:

$HSD = q \sqrt{\frac{MSE}{n}}$

Where:
*   $q$ is the studentized range statistic.
*   $MSE$ is the Mean Squared Error from the ANOVA.
*   $n$ is the sample size for the groups being compared (for Tukey-Kramer, an adjusted $n$ is used for unequal sample sizes).

## Worked Example

Imagine we conducted a one-way ANOVA to compare the mean scores of students taught using three different methods (Method A, Method B, Method C). The ANOVA result was significant (p < 0.05), indicating there is a difference among the group means. Now we use Tukey's HSD to find out which specific methods differ.

Let's assume the ANOVA results provided:
*   Mean score for Method A: 75
*   Mean score for Method B: 82
*   Mean score for Method C: 78
*   Mean Squared Error (MSE): 50
*   Number of groups (k): 3
*   Total sample size (N): 30
*   Degrees of freedom for error: N - k = 30 - 3 = 27

We would look up the critical studentized range statistic ($q$) for $\alpha = 0.05$, 3 groups, and 27 degrees of freedom. Let's assume the critical $q$ is approximately 3.50.

Now, we compare each pair of means:

**Comparison 1: Method A vs. Method B**

Difference in means = $|82 - 75| = 7$

Assume equal sample sizes for simplicity, say $n=10$ per group.

$HSD = 3.50 \sqrt{\frac{50}{10}} = 3.50 \sqrt{5} \approx 3.50 \times 2.236 \approx 7.83$

Since the absolute difference in means (7) is less than the calculated HSD (7.83), the difference between Method A and Method B is **not statistically significant** at the 0.05 level according to this simplified example.

**Comparison 2: Method A vs. Method C**

Difference in means = $|78 - 75| = 3$

$HSD = 7.83$ (since sample sizes and MSE are the same)

Since the absolute difference in means (3) is less than the calculated HSD (7.83), the difference between Method A and Method C is **not statistically significant**.

**Comparison 3: Method B vs. Method C**

Difference in means = $|82 - 78| = 4$

$HSD = 7.83$

Since the absolute difference in means (4) is less than the calculated HSD (7.83), the difference between Method B and Method C is **not statistically significant**.

**Note:** In a real statistical software output for Tukey's HSD, you would typically see a table showing each pairwise comparison, the difference in means, the calculated test statistic (often represented differently than the $q$ value we calculated manually), and the adjusted p-value. The conclusion is based on whether the adjusted p-value for a pair is less than your chosen alpha level (e.g., 0.05).

If the software provided the p-values directly for these comparisons, we might see p-values greater than 0.05 for all pairs, confirming our manual calculation result in this simplified example that no pairs are significantly different despite the overall ANOVA being significant. This can happen, especially if the differences, while contributing to the overall ANOVA significance, aren't large enough individually to meet the stricter threshold of Tukey's HSD which accounts for multiple comparisons.

A common output from statistical software for Tukey's HSD might look like this:

| Comparison   | Mean Difference | Lower 95% CI | Upper 95% CI | Adjusted P-value |
|--------------|-----------------|--------------|--------------|------------------|
| Method B - Method A | 7               | -0.83        | 14.83        | 0.09             |
| Method C - Method A | 3               | -4.83        | 10.83        | 0.55             |
| Method C - Method B | -4              | -11.83       | 3.83         | 0.45             |

In this hypothetical software output, all adjusted p-values are greater than 0.05, leading to the conclusion that none of the pairwise differences between the methods are statistically significant according to Tukey's HSD.