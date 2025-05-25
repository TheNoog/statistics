## Poisson Regression

Poisson regression is a generalized linear model used to model count data. Count data represents the number of times an event occurs, and is often non-negative integers (0, 1, 2, ...). This type of data often exhibits a Poisson distribution, where the variance is equal to the mean.

Poisson regression is suitable when:

*   The dependent variable is a count.
*   The events are independent.
*   The mean and variance of the dependent variable are roughly equal.

The model predicts the expected count given the independent variables. The relationship between the independent variables and the expected count is typically modeled using a logarithm link function:

$$ \log(\text{Expected Count}) = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + ... + \beta_n X_n $$

Where:

*   Expected Count is the predicted number of events.
*   $ \beta_0 $ is the intercept.
*   $ \beta_i $ are the coefficients for the independent variables $ X_i $.

Exponentiating both sides gives the expected count directly:

$$ \text{Expected Count} = e^{\beta_0 + \beta_1 X_1 + \beta_2 X_2 + ... + \beta_n X_n} $$

### Worked Example

Let's consider an example where we want to model the number of emails a person receives per day based on their work hours and whether they use a spam filter.

**Data:**

| Emails Received | Work Hours | Spam Filter (0=No, 1=Yes) |
|-----------------|------------|---------------------------|
| 12              | 8          | 0                         |
| 5               | 6          | 1                         |
| 15              | 9          | 0                         |
| 7               | 7          | 1                         |
| 10              | 8          | 0                         |
| 4               | 5          | 1                         |
| 13              | 9          | 0                         |
| 6               | 7          | 1                         |
| 11              | 8          | 0                         |
| 3               | 5          | 1                         |

**Objective:** Model the number of emails received using Poisson regression with 'Work Hours' and 'Spam Filter' as predictors.

**Steps (Conceptual):**

1.  **Fit the Poisson Regression Model:** Statistical software is used to estimate the coefficients ($\beta$) for the intercept, Work Hours, and Spam Filter.
2.  **Interpret the Coefficients:**
    *   The coefficient for Work Hours represents the change in the *log* of the expected email count for a one-unit increase in work hours, holding other variables constant.
    *   The coefficient for Spam Filter represents the change in the *log* of the expected email count when a spam filter is used (compared to not using one), holding work hours constant.
    *   Exponentiating the coefficients gives the multiplicative change in the expected count. For example, $e^{\beta_{\text{Work Hours}}}$ is the factor by which the expected email count changes for each additional hour worked. $e^{\beta_{\text{Spam Filter}}}$ is the factor by which the expected email count changes when a spam filter is used.
3.  **Assess Model Fit:** Evaluate how well the model fits the data using statistics like deviance and AIC.
4.  **Prediction:** Use the fitted model to predict the expected number of emails for new individuals based on their work hours and spam filter status.

**Illustrative Results (Conceptual):**

Let's assume the fitted model gives the following estimated coefficients:

*   Intercept: $ \hat{\beta}_0 = 1.5 $
*   Work Hours: $ \hat{\beta}_1 = 0.1 $
*   Spam Filter: $ \hat{\beta}_2 = -0.5 $

The model equation would be:

$$ \log(\text{Expected Emails}) = 1.5 + 0.1 \times \text{Work Hours} - 0.5 \times \text{Spam Filter} $$

To predict the expected number of emails for someone working 8 hours with no spam filter (Spam Filter = 0):

$$ \log(\text{Expected Emails}) = 1.5 + 0.1 \times 8 - 0.5 \times 0 = 1.5 + 0.8 - 0 = 2.3 $$
$$ \text{Expected Emails} = e^{2.3} \approx 9.97 $$

For someone working 7 hours with a spam filter (Spam Filter = 1):

$$ \log(\text{Expected Emails}) = 1.5 + 0.1 \times 7 - 0.5 \times 1 = 1.5 + 0.7 - 0.5 = 1.7 $$
$$ \text{Expected Emails} = e^{1.7} \approx 5.47 $$

**Interpretation of Coefficients:**

*   For every additional hour worked, the expected number of emails is multiplied by $e^{0.1} \approx 1.105$. This means an approximate 10.5% increase in expected emails per extra hour.
*   Using a spam filter (compared to not using one) is associated with multiplying the expected number of emails by $e^{-0.5} \approx 0.6065$. This means an approximate 39.35% reduction in expected emails when using a spam filter.

**Note:** In practice, the significance of the coefficients and the overall model fit would be assessed using statistical tests and diagnostic plots.