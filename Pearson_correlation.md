# Pearson Correlation Coefficient

The Pearson correlation coefficient, denoted by *r*, is a measure of the linear association between two continuous variables. It quantifies the strength and direction of the linear relationship. The value of *r* ranges from -1 to +1.

*   *r* = +1 indicates a perfect positive linear relationship.
*   *r* = -1 indicates a perfect negative linear relationship.
*   *r* = 0 indicates no linear relationship.

The formula for the Pearson correlation coefficient is:

$$ r = \frac{\sum{(x_i - \bar{x})(y_i - \bar{y})}}{\sqrt{\sum{(x_i - \bar{x})^2}\sum{(y_i - \bar{y})^2}}} $$

Where:
*   $x_i$ and $y_i$ are individual data points
*   $\bar{x}$ and $\bar{y}$ are the means of the *x* and *y* variables

## Worked Example

Let's calculate the Pearson correlation coefficient for the following two sets of data, representing hours studied (*x*) and exam score (*y*) for 5 students:

| Student | Hours Studied (x) | Exam Score (y) |
|---------|-------------------|----------------|
| 1       | 2                 | 60             |
| 2       | 4                 | 75             |
| 3       | 6                 | 80             |
| 4       | 8                 | 90             |
| 5       | 10                | 95             |

**Step 1: Calculate the means of x and y.**

$\bar{x} = \frac{2+4+6+8+10}{5} = \frac{30}{5} = 6$
$\bar{y} = \frac{60+75+80+90+95}{5} = \frac{400}{5} = 80$

**Step 2: Calculate the deviations from the mean for each data point (x - $\bar{x}$) and (y - $\bar{y}$).**

| Student | x | y  | x - $\bar{x}$ | y - $\bar{y}$ |
|---------|---|----|---------------|---------------|
| 1       | 2 | 60 | 2 - 6 = -4    | 60 - 80 = -20 |
| 2       | 4 | 75 | 4 - 6 = -2    | 75 - 80 = -5  |
| 3       | 6 | 80 | 6 - 6 = 0     | 80 - 80 = 0   |
| 4       | 8 | 90 | 8 - 6 = 2     | 90 - 80 = 10  |
| 5       | 10| 95 | 10 - 6 = 4    | 95 - 80 = 15  |

**Step 3: Calculate the product of the deviations (x - $\bar{x}$)(y - $\bar{y}$) and the sum of these products.**

| Student | x - $\bar{x}$ | y - $\bar{y}$ | (x - $\bar{x}$)(y - $\bar{y}$) |
|---------|---------------|---------------|--------------------------------|
| 1       | -4            | -20           | (-4)(-20) = 80                 |
| 2       | -2            | -5            | (-2)(-5) = 10                  |
| 3       | 0             | 0             | (0)(0) = 0                     |
| 4       | 2             | 10            | (2)(10) = 20                   |
| 5       | 4             | 15            | (4)(15) = 60                   |
| **Sum** |               |               | **80 + 10 + 0 + 20 + 60 = 170** |

**Step 4: Calculate the squared deviations for x and y, and the sum of these squared deviations.**

| Student | x - $\bar{x}$ | (x - $\bar{x}$)$^2$ | y - $\bar{y}$ | (y - $\bar{y}$)$^2$ |
|---------|---------------|---------------------|---------------|---------------------|
| 1       | -4            | (-4)$^2$ = 16       | -20           | (-20)$^2$ = 400     |
| 2       | -2            | (-2)$^2$ = 4        | -5            | (-5)$^2$ = 25       |
| 3       | 0             | (0)$^2$ = 0         | 0             | (0)$^2$ = 0         |
| 4       | 2             | (2)$^2$ = 4         | 10            | (10)$^2$ = 100      |
| 5       | 4             | (4)$^2$ = 16        | 15            | (15)$^2$ = 225      |
| **Sum** |               | **16 + 4 + 0 + 4 + 16 = 40** |               | **400 + 25 + 0 + 100 + 225 = 750** |

**Step 5: Plug the sums into the Pearson correlation formula.**

$$ r = \frac{170}{\sqrt{(40)(750)}} $$
$$ r = \frac{170}{\sqrt{30000}} $$
$$ r = \frac{170}{173.205} $$
$$ r \approx 0.981 $$

**Interpretation:**

The Pearson correlation coefficient is approximately 0.981. This indicates a very strong positive linear relationship between hours studied and exam score. As the number of hours studied increases, the exam score tends to increase as well.