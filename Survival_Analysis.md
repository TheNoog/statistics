# Survival Analysis

Survival analysis is a branch of statistics that deals with the analysis of the expected duration of time until one or more events happen, such as death in biological organisms and failure in mechanical systems. More generally, survival analysis involves the modeling of time-to-event data.

Key concepts in survival analysis include:

*   **Survival Time:** The time from a defined starting point to the occurrence of the event of interest.
*   **Event:** The occurrence that marks the end of the survival time (e.g., death, failure, recovery).
*   **Censoring:** Occurs when the event of interest has not occurred by the end of the study or when the subject is lost to follow-up.

Common methods in survival analysis include:

*   **Kaplan-Meier Estimator:** A non-parametric statistic used to estimate the survival function from lifetime data.
*   **Cox Proportional Hazards Model:** A semi-parametric model used to examine the relationship between survival time and one or more predictor variables.

## Worked Example: Kaplan-Meier Estimator

Let's consider a simple example of estimating the survival function for patients after a certain medical treatment.

Suppose we have the following survival data for 5 patients (time in months):

| Patient | Survival Time (months) | Event (1 = Died, 0 = Survived) |
| :------ | :--------------------- | :----------------------------- |
| 1       | 3                      | 1                              |
| 2       | 5                      | 1                              |
| 3       | 7                      | 0 (Censored)                   |
| 4       | 9                      | 1                              |
| 5       | 10                     | 0 (Censored)                   |

To calculate the Kaplan-Meier estimate of the survival function, we follow these steps:

1.  **Order the unique event times:** 3, 5, 9
2.  **Calculate the number of individuals at risk just before each event time:**
    *   At time 3: 5 patients are at risk.
    *   At time 5: 4 patients are at risk (Patient 1 had the event).
    *   At time 9: 2 patients are at risk (Patients 1 and 2 had the event, Patient 3 was censored).
3.  **Calculate the number of events at each event time:**
    *   At time 3: 1 event.
    *   At time 5: 1 event.
    *   At time 9: 1 event.
4.  **Calculate the survival probability at each event time:**
    *   $S(t) = S(t_{i-1}) * \left(1 - \frac{\text{Number of events at } t_i}{\text{Number at risk at } t_i}\right)$
    *   $S(0) = 1$ (By definition)
    *   $S(3) = S(0) * (1 - 1/5) = 1 * 0.8 = 0.8$
    *   $S(5) = S(3) * (1 - 1/4) = 0.8 * 0.75 = 0.6$
    *   $S(9) = S(5) * (1 - 1/2) = 0.6 * 0.5 = 0.3$

So, the Kaplan-Meier estimated survival probabilities are:

*   At time 3 months, the probability of survival is 0.8.
*   At time 5 months, the probability of survival is 0.6.
*   At time 9 months, the probability of survival is 0.3.

For censored times (7 and 10 months), the survival function remains constant at the value calculated at the previous event time.

This example demonstrates how the Kaplan-Meier estimator provides a step-wise function that estimates the probability of surviving past certain time points.