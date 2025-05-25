# Simple Linear Regression

Simple linear regression is a statistical method used to model the relationship between two continuous variables. One variable is considered the predictor or independent variable (often denoted as $X$), and the other is considered the response or dependent variable (often denoted as $Y$). The goal is to find a linear equation that best describes how $Y$ changes as $X$ changes.

The equation for a simple linear regression model is:

$Y = \beta_0 + \beta_1 X + \epsilon$

Where:
- $Y$ is the dependent variable.
- $X$ is the independent variable.
- $\beta_0$ is the y-intercept (the value of $Y$ when $X$ is 0).
- $\beta_1$ is the slope (the change in $Y$ for a one-unit increase in $X$).
- $\epsilon$ is the error term, representing the part of $Y$ not explained by the linear relationship with $X$.

The process of simple linear regression involves estimating the values of $\beta_0$ and $\beta_1$ from sample data. This is typically done using the method of least squares, which minimizes the sum of the squared differences between the observed $Y$ values and the $Y$ values predicted by the regression line.

## Worked Example

Let's say we want to investigate the relationship between the number of hours a student studies (X) and their score on a test (Y). We collect data from 5 students:

| Hours Studied (X) | Test Score (Y) |
|-------------------|----------------|
| 2                 | 60             |
| 3                 | 75             |
| 4                 | 80             |
| 5                 | 90             |
| 6                 | 95             |

We can use simple linear regression to find the line that best fits this data and predict test scores based on study hours.

**Steps:**

1.  **Calculate the means of X and Y:**
    $\bar{X} = (2+3+4+5+6)/5 = 4$
    $\bar{Y} = (60+75+80+90+95)/5 = 80$

2.  **Calculate the sum of the products of the deviations of X and Y:**
    $\sum (X_i - \bar{X})(Y_i - \bar{Y})$
    $(2-4)(60-80) + (3-4)(75-80) + (4-4)(80-80) + (5-4)(90-80) + (6-4)(95-80)$
    $(-2)(-20) + (-1)(-5) + (0)(0) + (1)(10) + (2)(15)$
    $40 + 5 + 0 + 10 + 30 = 85$

3.  **Calculate the sum of the squared deviations of X:**
    $\sum (X_i - \bar{X})^2$
    $(2-4)^2 + (3-4)^2 + (4-4)^2 + (5-4)^2 + (6-4)^2$
    $(-2)^2 + (-1)^2 + (0)^2 + (1)^2 + (2)^2$
    $4 + 1 + 0 + 1 + 4 = 10$

4.  **Calculate the slope ($\beta_1$):**
    $\beta_1 = \frac{\sum (X_i - \bar{X})(Y_i - \bar{Y})}{\sum (X_i - \bar{X})^2} = \frac{85}{10} = 8.5$

5.  **Calculate the y-intercept ($\beta_0$):**
    $\beta_0 = \bar{Y} - \beta_1 \bar{X} = 80 - (8.5)(4) = 80 - 34 = 46$

6.  **Write the regression equation:**
    $\hat{Y} = 46 + 8.5 X$

Where $\hat{Y}$ represents the predicted test score.

**Interpretation:**

The regression equation suggests that for every additional hour a student studies, their test score is predicted to increase by 8.5 points. The y-intercept of 46 suggests that a student who studies 0 hours is predicted to score 46 points, although this may not be meaningful in all contexts.

Using this model, we can predict the test score for a student who studies, say, 4.5 hours:
$\hat{Y} = 46 + 8.5(4.5) = 46 + 38.25 = 84.25$

So, a student studying 4.5 hours is predicted to score approximately 84.25 on the test.