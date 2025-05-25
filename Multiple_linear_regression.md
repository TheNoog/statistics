# Multiple Linear Regression

Multiple linear regression is a statistical technique used to predict the outcome of a dependent variable based on the value of two or more independent variables. It extends simple linear regression, which uses only one independent variable.

The general form of the multiple linear regression equation is:

$Y = \beta_0 + \beta_1X_1 + \beta_2X_2 + ... + \beta_nX_n + \epsilon$

Where:

*   $Y$ is the dependent variable.
*   $\beta_0$ is the y-intercept (the value of Y when all independent variables are 0).
*   $\beta_1, \beta_2, ..., \beta_n$ are the regression coefficients for the independent variables. They represent the change in the mean of Y for a one-unit increase in the corresponding independent variable, holding other independent variables constant.
*   $X_1, X_2, ..., X_n$ are the independent variables.
*   $\epsilon$ is the error term, representing the variability in Y that is not explained by the independent variables.

## Assumptions of Multiple Linear Regression

Before performing a multiple linear regression analysis, several assumptions should be checked:

*   **Linearity:** The relationship between each independent variable and the dependent variable is linear.
*   **Independence of errors:** The errors (residuals) are independent of each other.
*   **Homoscedasticity:** The variance of the errors is constant across all levels of the independent variables.
*   **Normality of errors:** The errors are normally distributed.
*   **No multicollinearity:** The independent variables are not highly correlated with each other.

## Worked Example

Let's consider an example where we want to predict a person's salary (dependent variable) based on their years of experience and their education level (independent variables).

Assume we have the following data for a small sample of individuals:

| Salary ($) | Years of Experience | Education Level (1=High School, 2=Bachelor's, 3=Master's) |
|------------|---------------------|-------------------------------------------------------------|
| 40000      | 2                   | 1                                                           |
| 55000      | 5                   | 2                                                           |
| 60000      | 4                   | 3                                                           |
| 45000      | 3                   | 2                                                           |
| 70000      | 7                   | 3                                                           |
| 50000      | 6                   | 1                                                           |

Using statistical software (like Python with `statsmodels` or R), we can perform a multiple linear regression analysis.

The output from the regression analysis would provide the regression coefficients ($\beta_0$, $\beta_1$, $\beta_2$) and other statistics.

Let's assume the output gives us the following estimated coefficients:

*   $\hat{\beta}_0 \approx 30000$ (Intercept)
*   $\hat{\beta}_1 \approx 2500$ (Coefficient for Years of Experience)
*   $\hat{\beta}_2 \approx 10000$ (Coefficient for Education Level)

The regression equation would then be:

$\text{Predicted Salary} = 30000 + 2500 \times \text{Years of Experience} + 10000 \times \text{Education Level}$

**Interpretation of the coefficients:**

*   **Intercept (30000):** When years of experience and education level are both 0, the predicted salary is $30,000. However, interpreting the intercept can sometimes be difficult if 0 for the independent variables is not a meaningful value in the context.
*   **Years of Experience (2500):** For each additional year of experience, the predicted salary increases by $2500, holding education level constant.
*   **Education Level (10000):** For each unit increase in education level (e.g., moving from High School to Bachelor's), the predicted salary increases by $10,000, holding years of experience constant.

**Using the model for prediction:**

Let's predict the salary for someone with 6 years of experience and a Bachelor's degree (Education Level = 2):

$\text{Predicted Salary} = 30000 + 2500 \times 6 + 10000 \times 2$
$\text{Predicted Salary} = 30000 + 15000 + 20000$
$\text{Predicted Salary} = 65000$

So, based on this model, we would predict a salary of $65,000 for an individual with 6 years of experience and a Bachelor's degree.

In a real analysis, you would also examine the R-squared value (proportion of variance in the dependent variable explained by the independent variables), the p-values of the coefficients (to see if they are statistically significant), and check the model assumptions using diagnostic plots and tests.