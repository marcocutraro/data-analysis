# Survival Analysis on Unemployment Duration

## Research question & Motivation

Assess which demographic variables most influence the duration of unemployment.
Knowing the factors that influence re-entry into the labor market can have much impact for social and economic purposes.

## Data

Our sample consists of 3343 observations, containing information from unemployed or formerly unemployed individuals in the United States: https://docs.google.com/file/d/0BwogTI8d6EEiM2stZzdFNXdxM00/edit?resourcekey=0-hgX60ZrsGu05yZO4vuMfDA

The demographic variables of most interest were retained in the dataset: gender, earnings, unemployment insurance, marital status, and parental status.

## Hypotesis

The main hypothesis to be tested is whether the demographic factors that most influence the timing of re-entry into the labor market are: marital status, parental status, gender, and whether or not one has unemployment insurance (ui).

## Methods

Having a dataset with a variable that identifies the duration and a variable that identifies whether the event (re-employed at full time job) occurs or not we can do a Survival Analysis using STATA, software for processing statistical data.
Through the Survival Analysis we intend to analyze the time to the occurrence of a given event. In this case the quantitative variable spell indicates the duration of the period of unemployment, while event is a dummy variable that expresses value 1 if the individual has been reemployed and 0 if he is still unemployed.

![methods](https://github.com/marcocutraro/data-analysis/blob/main/methods.png)

### Cox Proportional-Hazards Model
The purpose of the model is to simultaneously assess the effect of multiple factors on survival. In other words, it allows us to examine how specific factors affect the frequency with which a particular event occurs (e.g., infection, death, or in our case, finding a job) at a given time.
Probability is commonly referred to as the hazard rate (hazard ratio). Predictive variables, or factors, are usually called covariates in the survival analysis literature.

## Results

Cox regression can be interpreted as follows:

![results7](https://github.com/marcocutraro/data-analysis/blob/main/results7.png) ![results6](https://github.com/marcocutraro/data-analysis/blob/main/results6.png)

  - The column "z" lists the Wald statistical value, corresponds ratio between coefficient and standard deviation (z = Coef / Std Err)
  - The positive sign of the coefficients indicates greater risk for individuals with high values of that variable and viceversa. In our case the term "risk" can be misleading because an increase in it represents a greater probability that the     event "re-employed at full time job" occurs.
  - The Hazard ratio (Haz. Ratio) in survival analysis represents the effect of an explanatory variable (e.g. having or not having unemployment insurance) on the danger or risk of an event (e.g. finding a job or remaining unemployed).
  - The confidence interval represents the interval within which the 'true' effect of the hazard ratio that would be observed in the population is likely to be included.
  
It is possible to visualize the expected survival proportion at a given point in time for a particular at-risk group (in our case, individuals with and without unemployment insurance, ui) using a Kaplan-Meier estimation plot, i.e., a series of horizontal steps of decreasing magnitude that approximates the true survival function for that population.
![results1](https://github.com/marcocutraro/data-analysis/blob/main/results1.png) ![results2](https://github.com/marcocutraro/data-analysis/blob/main/results2.png)

The images below show Nelson-Aalen plots, the Nelson-Aalen estimator is a non-parametric estimator of the cumulative hazard ratio function, it is used in survival analysis to estimate the cumulative number of expected events.
![results3](https://github.com/marcocutraro/data-analysis/blob/main/results3.png)
![results4](https://github.com/marcocutraro/data-analysis/blob/main/results4.png)

## Conclusion

Using the Survival Analysis method, in particular the Cox regression (Cox Proportional Hazards Model), we can see that of all the covariates, the one that most affects the duration of unemployment is the possession of unemployment insurance (ui), a type of state insurance that pays people money on a weekly basis when they lose their jobs and meet certain eligibility requirements.
