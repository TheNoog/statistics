# Kaplan-Meier Estimator

The Kaplan-Meier estimator is a non-parametric statistic used to estimate the survival function from lifetime data. In medical research, it's often used to estimate the fraction of patients living for a certain amount of time after treatment. In reliability engineering, it's used to estimate the probability of a component surviving for a certain duration.

The survival function, S(t), is the probability that a subject survives beyond time t. The Kaplan-Meier estimator calculates this probability at each time point where an event (like death or failure) occurs.

The formula for the Kaplan-Meier estimator at time $t_i$ is:

$$S(t_i) = S(t_{i-1}) \times \left( \frac{n_i - d_i}{n_i} \right)$$

Where:
*   $S(t_i)$ is the estimated survival probability at time $t_i$.
*   $S(t_{i-1})$ is the estimated survival probability at the previous time point $t_{i-1}$ (with $S(t_0) = 1$ at time 0).
*   $n_i$ is the number of individuals at risk just before time $t_i$.
*   $d_i$ is the number of events (deaths, failures, etc.) that occur at time $t_i$.

Censored data (where the event did not occur during the observation period) are handled by being included in the number at risk ($n_i$) up to the point of censoring, but they do not contribute to the number of events ($d_i$).

## Worked Example

Let's consider a small study tracking the survival of 10 patients after a new treatment. The survival times in months are: 3, 5, 7, 8, 10, 12+, 13, 15+, 16, 18+. The '+' indicates censored data (the patient was still alive at that time).

First, we order the distinct event times and note the number at risk and the number of events at each time point.

| Time (t) | Number at Risk ($n_i$) | Number of Events ($d_i$) |
|---|---|---|
| 3 | 10 | 1 |
| 5 | 9 | 1 |
| 7 | 8 | 1 |
| 8 | 7 | 1 |
| 10 | 6 | 1 |
| 12+ (Censored) | 5 | 0 |
| 13 | 5 | 1 |
| 15+ (Censored) | 4 | 0 |
| 16 | 4 | 1 |
| 18+ (Censored) | 3 | 0 |

Now, we calculate the survival probability at each event time using the formula:

*   **At t = 3:**
    $S(3) = S(0) \times \left( \frac{10 - 1}{10} \right) = 1 \times \frac{9}{10} = 0.9$

*   **At t = 5:**
    $S(5) = S(3) \times \left( \frac{9 - 1}{9} \right) = 0.9 \times \frac{8}{9} \approx 0.8$

*   **At t = 7:**
    $S(7) = S(5) \times \left( \frac{8 - 1}{8} \right) = 0.8 \times \frac{7}{8} = 0.7$

*   **At t = 8:**
    $S(8) = S(7) \times \left( \frac{7 - 1}{7} \right) = 0.7 \times \frac{6}{7} = 0.6$

*   **At t = 10:**
    $S(10) = S(8) \times \left( \frac{6 - 1}{6} \right) = 0.6 \times \frac{5}{6} = 0.5$

*   **At t = 12+ (Censored):** No event occurs, survival probability does not change. $S(12) = S(10) = 0.5$. The number at risk for the next event time is updated.

*   **At t = 13:**
    $S(13) = S(10) \times \left( \frac{5 - 1}{5} \right) = 0.5 \times \frac{4}{5} = 0.4$

*   **At t = 15+ (Censored):** No event occurs, survival probability does not change. $S(15) = S(13) = 0.4$. The number at risk for the next event time is updated.

*   **At t = 16:**
    $S(16) = S(13) \times \left( \frac{4 - 1}{4} \right) = 0.4 \times \frac{3}{4} = 0.3$

*   **At t = 18+ (Censored):** No event occurs, survival probability does not change. $S(18) = S(16) = 0.3$.

The Kaplan-Meier survival estimates at the event times are:

| Time (t) | Estimated Survival Probability (S(t)) |
|---|---|
| 3 | 0.9 |
| 5 | 0.8 |
| 7 | 0.7 |
| 8 | 0.6 |
| 10 | 0.5 |
| 13 | 0.4 |
| 16 | 0.3 |

This gives us a step-wise estimate of the survival function over time. A Kaplan-Meier survival curve is typically plotted with time on the x-axis and the survival probability on the y-axis, showing the probability of survival decreasing over time.