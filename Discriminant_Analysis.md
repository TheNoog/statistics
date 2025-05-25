# Discriminant Analysis

Discriminant analysis is a statistical technique used to predict which group a case belongs to based on values on one or more predictor variables. It's similar to regression analysis, but instead of predicting a continuous outcome, it predicts a categorical outcome (group membership).

There are two main types of discriminant analysis:

1.  **Linear Discriminant Analysis (LDA):** Assumes that the variance-covariance matrices are equal across groups.
2.  **Quadratic Discriminant Analysis (QDA):** Does not assume equal variance-covariance matrices.

The goal of discriminant analysis is to find a linear combination of predictors that best separates the groups. This combination is called a discriminant function.

## When to use Discriminant Analysis:

*   You have a categorical dependent variable with two or more groups.
*   You have two or more continuous independent variables.
*   You want to predict group membership based on the independent variables.
*   You want to understand which independent variables contribute most to the separation between groups.

## Assumptions of Discriminant Analysis:

*   **Multivariate Normality:** The independent variables are normally distributed within each group.
*   **Homogeneity of Variances (for LDA):** The variance-covariance matrices of the independent variables are equal across all groups.
*   **Linearity:** There is a linear relationship between the independent variables and the discriminant function.
*   **No Multicollinearity:** The independent variables are not highly correlated with each other.

## Worked Example: Predicting Species of Iris

Let's use the famous Iris dataset, which contains measurements of sepal length, sepal width, petal length, and petal width for three species of iris: setosa, versicolor, and virginica. We will use discriminant analysis to predict the species based on the four measurements.

Imagine we have a new iris and we want to classify its species based on its measurements.

**Data:**

We'll use a simplified subset of the Iris data for demonstration.

| Sepal Length | Sepal Width | Petal Length | Petal Width | Species     |
|--------------|-------------|--------------|-------------|-------------|
| 5.1          | 3.5         | 1.4          | 0.2         | setosa      |
| 4.9          | 3.0         | 1.4          | 0.2         | setosa      |
| 6.3          | 3.3         | 6.0          | 2.5         | virginica   |
| 5.8          | 2.7         | 5.1          | 1.9         | virginica   |
| 5.5          | 2.3         | 4.0          | 1.3         | versicolor  |
| 5.0          | 2.0         | 3.5          | 1.0         | versicolor  |

**Steps:**

1.  **Train the model:** We use the existing data with known species to train the discriminant analysis model. The model will find the discriminant functions that best separate the three species based on the measurements.
2.  **Evaluate the model:** We can evaluate how well the model performs on the training data by looking at the classification accuracy (how many irises were correctly classified).
3.  **Predict for a new case:** Given the measurements of a new iris with an unknown species, we can use the trained model to predict its species.

**Conceptual Illustration (without complex calculations):**

Discriminant analysis essentially finds a line (or a plane in higher dimensions) that best separates the groups. For our Iris example with four measurements, it finds a way to project the data onto a lower-dimensional space (using the discriminant functions) where the species are as separated as possible.

Imagine plotting two of the measurements, say petal length and petal width. Discriminant analysis would find a line that best divides the data points belonging to different species. A new iris's position relative to this line would determine its predicted species.

**Interpreting Results:**

The output of a discriminant analysis typically includes:

*   **Discriminant functions:** The equations that combine the predictor variables.
*   **Eigenvalues:** Indicate the amount of variance explained by each discriminant function.
*   **Canonical correlations:** Measure the association between the discriminant functions and the groups.
*   **Centroids:** The mean values of the discriminant functions for each group.
*   **Classification accuracy:** How well the model predicts group membership.

**Example Prediction:**

Let's say we have a new iris with the following measurements:

*   Sepal Length: 5.9
*   Sepal Width: 3.0
*   Petal Length: 4.5
*   Petal Width: 1.5

The discriminant analysis model would plug these values into the discriminant functions it learned during training. Based on the resulting scores on the discriminant functions, the model would predict which species the new iris most likely belongs to. For these values, it would likely predict "versicolor".

**Conclusion:**

Discriminant analysis is a powerful tool for classifying cases into groups based on predictor variables. It helps us understand which variables are most important for distinguishing between groups and allows us to predict group membership for new, unclassified cases.