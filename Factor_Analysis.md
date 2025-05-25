# Factor Analysis

Factor Analysis is a statistical method used to describe variability among observed, correlated variables in terms of a potentially lower number of unobserved variables called factors. It aims to reduce the dimensionality of a dataset while retaining as much of the original information as possible. It's commonly used in social sciences, psychology, and market research to identify underlying constructs or latent variables.

There are two main types:

1.  **Exploratory Factor Analysis (EFA):** Used when the researcher does not have a predefined idea about which variables load onto which factors. It explores the data to determine the underlying factor structure.
2.  **Confirmatory Factor Analysis (CFA):** Used when the researcher has a hypothesis about the factor structure and wants to test if the data fits that structure.

**Assumptions:**

*   The data is interval or ratio scale.
*   The variables are linearly related.
*   There is multivariate normality (though factor analysis is somewhat robust to violations).
*   There is a sufficient sample size (often recommended to have at least 100-200 observations or a subject-to-variable ratio of at least 10:1).

**Steps in Exploratory Factor Analysis:**

1.  **Data Collection:** Gather data on the observed variables.
2.  **Correlation Matrix:** Compute the correlation matrix among all observed variables. Factor analysis is based on the relationships between variables.
3.  **Factor Extraction:** Choose a method to extract factors from the correlation matrix. Common methods include Principal Component Analysis (PCA) and Principal Axis Factoring. The goal is to identify the minimum number of factors that explain a significant portion of the variance in the observed variables.
4.  **Factor Rotation:** Rotate the factors to make them more interpretable. Rotation methods (like Varimax, Promax, or Oblimin) aim to achieve a simple structure where each variable loads highly on only one factor.
5.  **Factor Interpretation:** Examine the rotated factor loadings (the correlations between the observed variables and the factors) to understand what each factor represents. Variables with high loadings on the same factor are considered to be measuring the same underlying construct.
6.  **Factor Scores (Optional):** Calculate factor scores, which are the values for each subject on the extracted factors. These can be used in subsequent analyses.

**Worked Example (Conceptual):**

Let's imagine a survey asking customers to rate a new product on several attributes using a 1-5 scale:

*   Attribute 1: Ease of Use
*   Attribute 2: Installation Difficulty
*   Attribute 3: User Interface Design
*   Attribute 4: Performance Speed
*   Attribute 5: Reliability
*   Attribute 6: Build Quality

After collecting data from 200 customers, we perform an Exploratory Factor Analysis.

1.  **Correlation Matrix:** We compute the correlations between all pairs of attributes. We would likely see high positive correlations between Ease of Use, Installation Difficulty (perhaps inversely correlated), and User Interface Design, suggesting they might measure a similar concept. Similarly, Performance Speed, Reliability, and Build Quality might be highly correlated.

2.  **Factor Extraction:** Using a method like Principal Component Analysis, the analysis might suggest that two factors explain a large proportion of the variance in the data (e.g., 70%).

3.  **Factor Rotation (e.g., Varimax):** The rotation aims to clarify which attributes load onto which factor. After rotation, we might see the following idealized factor loadings:

    | Attribute               | Factor 1 (Usability) | Factor 2 (Performance) |
    | :---------------------- | :------------------- | :--------------------- |
    | Ease of Use             | 0.85                 | 0.10                   |
    | Installation Difficulty | 0.78                 | 0.15                   |
    | User Interface Design   | 0.90                 | 0.05                   |
    | Performance Speed       | 0.12                 | 0.88                   |
    | Reliability             | 0.08                 | 0.82                   |
    | Build Quality           | 0.18                 | 0.79                   |

4.  **Factor Interpretation:** Based on the high loadings, we can interpret Factor 1 as "Usability" because the attributes related to ease of use, installation, and interface design load heavily on it. Factor 2 can be interpreted as "Performance" as the attributes related to speed, reliability, and build quality load heavily on it.

This example demonstrates how Factor Analysis can reduce six observed attributes into two underlying factors, "Usability" and "Performance," providing a simpler structure to understand customer perceptions of the product. We can then use these two factors for further analysis or reporting instead of the original six attributes.

**Note:** A real-world factor analysis involves statistical software that performs the calculations and provides detailed output, including eigenvalues, communalities, and various fit indices (especially for CFA). The interpretation requires careful consideration of the theoretical context and statistical results.