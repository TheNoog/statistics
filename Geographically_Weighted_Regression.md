# Geographically Weighted Regression (GWR)

Geographically Weighted Regression (GWR) is a local spatial regression technique used to model relationships that may vary across geographic space. Unlike traditional global regression models that assume relationships are constant everywhere, GWR allows the parameters of the model to vary spatially. This is particularly useful when analyzing phenomena influenced by local factors that differ from place to place.

GWR works by fitting a separate regression equation at every location in the dataset. The observations are weighted according to their proximity to the location where the equation is being fitted. Observations closer to the location receive higher weights, while those further away receive lower weights. The "bandwidth" of the weighting function determines the extent of the local neighborhood.

The basic GWR model at a location \(i\) is:

\[ y_i = \sum_{k=0}^{p} \beta_k(u_i, v_i) x_{ik} + \epsilon_i \]

Where:
* \(y_i\) is the dependent variable at location \(i\).
* \((u_i, v_i)\) are the geographic coordinates of location \(i\).
* \(\beta_k(u_i, v_i)\) is the locally estimated regression coefficient for the \(k\)-th independent variable at location \(i\). These coefficients are estimated using weighted least squares.
* \(x_{ik}\) is the value of the \(k\)-th independent variable at location \(i\).
* \(p\) is the number of independent variables.
* \(\epsilon_i\) is the random error term at location \(i\).

The coefficients \(\beta_k(u_i, v_i)\) are estimated by minimizing the weighted sum of squared errors:

\[ \sum_{j=1}^{n} w_{ij} (y_j - \sum_{k=0}^{p} \beta_k(u_i, v_i) x_{jk})^2 \]

Where \(w_{ij}\) is the spatial weight between observation location \(j\) and calibration location \(i\).

**Advantages of GWR:**

*   Identifies spatial non-stationarity (how relationships vary across space).
*   Provides local insights and predictions.
*   Can reveal spatial patterns in relationships that global models would miss.

**Disadvantages of GWR:**

*   Can be computationally intensive.
*   Requires careful selection of bandwidth and weighting function.
*   Interpretation can be more complex due to spatially varying coefficients.

## Worked Example

Let's consider a hypothetical example where we want to model the relationship between house prices and the number of bedrooms in a city. We suspect that this relationship might not be constant across the entire city due to varying neighborhood characteristics (e.g., proximity to schools, parks, amenities).

**Data:**

Assume we have a dataset of houses with their location (latitude and longitude), price, and number of bedrooms.

| House ID | Latitude | Longitude | Price (\$) | Bedrooms |
|----------|----------|-----------|------------|----------|
| 1        | 34.05    | -118.25   | 500,000    | 3        |
| 2        | 34.06    | -118.26   | 520,000    | 4        |
| 3        | 34.10    | -118.30   | 650,000    | 4        |
| 4        | 34.11    | -118.31   | 680,000    | 5        |
| 5        | 34.03    | -118.20   | 400,000    | 2        |
| ...      | ...      | ...       | ...        | ...      |

**Steps to perform GWR:**

1.  **Choose a dependent variable:** House Price.
2.  **Choose independent variables:** Number of Bedrooms (and potentially other variables like square footage, age of house).
3.  **Define spatial weights:** Select a weighting function (e.g., Gaussian, Epanechnikov) and a bandwidth. The bandwidth can be fixed (a constant distance) or adaptive (based on a fixed number of neighbors). Cross-validation is often used to find an optimal bandwidth.
4.  **Perform the GWR analysis:** Using statistical software with GWR capabilities (e.g., ArcGIS Pro, R with the `spgwr` package), run the GWR model. The software will fit a separate weighted regression at each location.
5.  **Analyze the results:** Examine the spatially varying coefficients for each independent variable. You can create maps of the coefficients to visualize how the relationship between the independent variable (Bedrooms) and the dependent variable (Price) changes across the city.

**Interpreting the results:**

Suppose the GWR analysis reveals that the coefficient for "Bedrooms" is higher in certain areas of the city (e.g., downtown or areas with good schools) compared to other areas. This indicates that in those high-coefficient areas, an additional bedroom has a larger positive impact on the house price than in areas with lower coefficients. This spatial variation in the relationship would not be captured by a global regression model, which would provide a single coefficient for "Bedrooms" for the entire city.

By examining the spatially varying coefficients, we can gain a deeper understanding of the local factors that influence house prices and the relationships between variables. This can inform more targeted interventions or policies related to housing development or urban planning.