# MANOVA (Multivariate Analysis of Variance)

MANOVA (Multivariate Analysis of Variance) is an extension of ANOVA that is used when there is more than one dependent variable. It is used to determine whether there are any statistically significant differences between the means of two or more independent groups on two or more dependent variables.

The null hypothesis for a MANOVA is that the means of the dependent variables are equal across all groups. The alternative hypothesis is that at least one of the means of the dependent variables is different across the groups.

MANOVA tests for differences between groups on a combination of dependent variables. It looks for a linear combination of the dependent variables that maximizes the differences between the groups. This linear combination is called the discriminant function.

## Assumptions of MANOVA

*   **Independence of observations:** The observations within and between groups must be independent.
*   **Multivariate normality:** The dependent variables should follow a multivariate normal distribution in each group.
*   **Homogeneity of variance-covariance matrices:** The variance-covariance matrices of the dependent variables should be equal across all groups. This can be tested using Box's M test.
*   **Linearity:** There should be a linear relationship between the dependent variables.

## Worked Example

Let's consider an example where researchers are interested in the effect of different teaching methods on student performance in both math and science. They randomly assign students to one of three teaching methods (Method A, Method B, Method C) and measure their scores on a math test and a science test.

**Hypotheses:**

*   Null Hypothesis (H0): There is no statistically significant difference in the combined mean scores of math and science among the three teaching methods.
*   Alternative Hypothesis (H1): There is a statistically significant difference in the combined mean scores of math and science among the three teaching methods.

**Data:**

Imagine we have the following data for a small sample of students:

| Student | Teaching Method | Math Score | Science Score |
| :------ | :-------------- | :--------- | :------------ |
| 1       | A               | 75         | 80            |
| 2       | A               | 80         | 85            |
| 3       | A               | 70         | 78            |
| 4       | B               | 85         | 88            |
| 5       | B               | 90         | 92            |
| 6       | B               | 82         | 86            |
| 7       | C               | 78         | 83            |
| 8       | C               | 81         | 87            |
| 9       | C               | 76         | 81            |

**Analysis:**

To perform a MANOVA, you would typically use statistical software (like R, SPSS, or Python with libraries like `statsmodels`). The software would calculate various multivariate test statistics (e.g., Wilks' Lambda, Pillai's Trace, Hotelling-Lawley Trace, Roy's Largest Root) to determine if there is a significant overall difference between the groups on the combined dependent variables.

Let's assume the software output gives a p-value for Wilks' Lambda of 0.03.

**Interpretation:**

If the p-value (0.03) is less than the chosen significance level (e.g., 0.05), we reject the null hypothesis. This indicates that there is a statistically significant difference in the combined mean scores of math and science among the three teaching methods.

**Follow-up Analysis:**

If the MANOVA is significant, you would typically conduct post-hoc tests to determine which specific groups differ from each other on which dependent variables. This could involve:

*   **Univariate ANOVAs:** Performing separate ANOVAs for each dependent variable (Math Score and Science Score) to see if there are differences between groups on individual scores.
*   **Discriminant Function Analysis:** To understand how the dependent variables contribute to the group differences.

For instance, if the univariate ANOVAs were conducted and found significant differences for both Math Score and Science Score, you could then use post-hoc tests like Tukey's HSD on each dependent variable to pinpoint which pairs of teaching methods are significantly different on math scores and which on science scores.

This example illustrates how MANOVA can be used to examine the effect of an independent variable on multiple dependent variables simultaneously, providing a more comprehensive analysis than performing separate ANOVAs.