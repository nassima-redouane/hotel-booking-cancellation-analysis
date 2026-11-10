# Hotel Booking Cancellation Analysis

Exploratory data analysis of **119,390 hotel bookings**, built to answer one question:
**which factors are associated with a booking being cancelled?**

The target variable is `is_canceled`. Every explanatory variable is studied **one at a time
against the target** — its cancellation profile, a statistical test, and an effect size —
then all variables are ranked by the strength of their relationship with cancellation.

## Key findings

| Finding | Result |
|---|---|
| Overall cancellation rate | **37.0 %** |
| Deposit type | Bookings with a **non-refundable deposit** were cancelled **99.4 %** of the time |
| Hotel type | City Hotel **41.7 %** vs Resort Hotel **27.8 %** |
| Lead time (dose–response) | Cancellation rises steadily with booking anticipation, from **6.8 %** to **67.7 %** |

Deposit type is by far the strongest single predictor of cancellation in this dataset.

## Method

- **Categorical variables** — cancellation rate per level, chi-square test, and **Cramér's V**
  to measure association strength (with 119k rows, p-values alone are not informative).
- **Numerical variables** — **density plots** by group (cancelled / not cancelled) and
  **Student's t-test** comparing the two groups.
- **Univariate analysis** — full descriptive statistics and charts for every variable,
  including data-quality checks (`"NULL"` strings recoded as missing values).
- **Final ranking** — categorical variables ordered by effect size (Cramér's V) against the
  target; Student's t-test results reported alongside for numerical variables.

## Repository contents

| File | Description |
|---|---|
| `Projet UA2 EDA complet.ipynb` | Executed Jupyter notebook (R kernel): the complete analysis — data preparation, univariate analysis, target-vs-variable analyses and ranked summary — with charts and outputs, readable directly on GitHub. |

## Tools

R · tidyverse (dplyr, ggplot2, readr, tidyr, forcats)

## Dataset

Hotel Booking Demand dataset (Antonio, de Almeida & Nunes, 2019), publicly available on
[Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand).
The raw data file is not redistributed in this repository.

## Author

**Nassima Redouane** — Applied Data Science student, Collège La Cité (Ottawa, Canada).
Project completed as part of a data exploration course.
