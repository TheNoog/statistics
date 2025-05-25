# Logistic Regression

Logistic regression is a statistical method used for predicting the probability of a binary outcome based on one or more predictor variables. The outcome variable has only two possible values (e.g., 0 or 1, yes or no, pass or fail). Unlike linear regression, which predicts a continuous outcome, logistic regression uses the logistic function (also known as the sigmoid function) to model the relationship between the predictor variables and the probability of the outcome.

The logistic function transforms the linear combination of the predictor variables into a probability value between 0 and 1. The model estimates the coefficients of the predictor variables, which indicate the change in the log-odds of the outcome associated with a one-unit increase in the predictor.

## When to Use

Logistic regression is appropriate when your dependent variable is dichotomous (binary). It can be used for:

*   **Classification:** Predicting which of two categories an observation belongs to.
*   **Risk Prediction:** Estimating the probability of an event occurring (e.g., the probability of developing a disease).

## Assumptions

*   **Binary Dependent Variable:** The outcome variable must be categorical with two levels.
*   **Independence of Observations:** Observations should be independent of each other.
*   **No Multicollinearity:** Predictor variables should not be highly correlated with each other.
*   **Linearity of Log-Odds:** There should be a linear relationship between the predictor variables and the log-odds of the outcome.

## Worked Example

Let's consider an example where we want to predict whether a student will pass an exam based on the number of hours they studied.

| Hours Studied | Pass (1) / Fail (0) |
|---------------|---------------------|
| 1             | 0                   |
| 2             | 0                   |
| 3             | 0                   |
| 4             | 1                   |
| 5             | 1                   |
| 6             | 1                   |
| 7             | 1                   |
| 8             | 1                   |

We can use a logistic regression model to estimate the probability of passing the exam for a given number of hours studied.

Using statistical software, we would fit a logistic regression model with "Pass/Fail" as the dependent variable and "Hours Studied" as the independent variable. The output would provide coefficients for the intercept and "Hours Studied".

Let's assume the fitted model yields the following equation for the log-odds:

Log-odds (Probability of Pass) = -3.5 + 1.0 * (Hours Studied)

To convert the log-odds to a probability, we use the logistic function:

Probability (Pass) = 1 / (1 + exp(-(Log-odds)))

For example, if a student studied for 4 hours:

Log-odds = -3.5 + 1.0 * 4 = 0.5

Probability (Pass) = 1 / (1 + exp(-0.5)) ≈ 1 / (1 + 0.6065) ≈ 1 / 1.6065 ≈ 0.622

So, according to this model, a student who studies for 4 hours has approximately a 62.2% probability of passing the exam.

If a student studied for 2 hours:

Log-odds = -3.5 + 1.0 * 2 = -1.5

Probability (Pass) = 1 / (1 + exp(1.5)) ≈ 1 / (1 + 4.4817) ≈ 1 / 5.4817 ≈ 0.182

A student who studies for 2 hours has approximately an 18.2% probability of passing.

The coefficient for "Hours Studied" (1.0 in this example) indicates that for every additional hour studied, the log-odds of passing the exam increase by 1. This means the odds of passing are multiplied by exp(1.0) ≈ 2.718 for each additional hour studied.

Logistic regression provides a powerful way to model and understand the relationship between predictor variables and the probability of a binary outcome.