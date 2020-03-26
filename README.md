# Covid19GermanyEstimates
Estimating the spread of Covid19 in Germany.

# How to interpret this model

## The basics
This is merely a mathematical prediction based on the number of reported cases and a model developed using outbreaks of other illnesses such as ebola. The biggest issue is that I'm fitting my model to the number of reported cases. This means the predictions are heavily influenced by the way cases are found through testing. Thus, unless germany is testing a sample size much larger than the actual outbreak, my prediction will not accurately predict the real number of infections and could be influenced by a number of factors. 
For example, my model (and the actual data) seems to predict around 3 days case doubling. While this matches what other countries are seeing in their screenings, it is not a reliable way to predict the actual growth of the outbreak. 
There have been a number of studies that are trying to simulate the outbreak using highly complex simulations and their finding usually amounts to a case doubling period of 5-7 days.
A shorter case doubling rate in germanys data might imply that we're catching up with the real number of cases or that due to societal factors the cases are actually doubling faster in germany currently or a number of other things. 
This model therefore should only be used as a rough estimate of "how bad will shit hit the fan?" and not for any other purposes.


# Model

## Current Formulae and Parameters

### Polynomial Model

![equation](https://latex.codecogs.com/gif.latex?Cases(t)=%20r\cdot%20[(\frac{r}{m}\cdot%20t%20+%20a)^m%20]%20^p%20)

![equationparameters](https://latex.codecogs.com/gif.latex?with:%20r=1;%20m=40;%20a=1,2704;%20p=0,4223;)

and with t being the day starting at 0. Model parameters were fitted with 28.02.2020 being day 0 (here, case number hit 50+ cases).

#### Sources for Model
Numerical model is based on the formulae suggested in this paper:
https://arxiv.org/ftp/arxiv/papers/1512/1512.01389.pdf

Parameters are then worked out using GRG nonlinear analysis in excel with multistart to find a global minimum for parameter convergence.
GRG Nonlinear is set to find a minimum for the sum of quadratic errors between the model estimates and the known data.
I then offset the estimated data by -7 days in order to get a glimpse on what the real number of infections might be.

Source for number of infections by date is:
https://interaktiv.morgenpost.de/corona-virus-karte-infektionen-deutschland-weltweit/

Currently, the situation in germany is difficult in that counting is decentralized, which means all reports are off by some degree. Berliner Morgenpost is trying to keep the time at which they count cases consistent and source their data from the local health authorities, which hopefully makes their data very close to reality.

### Logistic Model

This is the second model which better models the decline of the exponential phase of the epidemic. This is the model I'll keep updating from now on, as it converges better with actual data currently.
I also included a linear component into the logistic model in order to predict unknown cases which leads to a slightly lower r^2 error.

![equation](https://latex.codecogs.com/gif.latex?Cases(t)=%20a%20*%200,5%20/%20%20[0,5%20+%20(a%20-%200,5)%20*%20exp%20(-b%20*%20a%20*%20%20(x%20-c))]%20-%20(d%20*%20x%20+%20e))

![equationparameters](https://latex.codecogs.com/gif.latex?with%3A%20a%3D55884%2C12355%3B%20b%3D4%2C90955%20*%2010%7B%5E%7B-6%7D%7D%3B%20c%3D-19%3B%20d%20%3D%2026%2C72556%3B%20e%20%3D%202%2C50286*10%7B%5E%7B-7%7D%7D)


# Current Estimates

## Logistic Model

![Model vs Actual Data](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/Logistical%20Model.png)

## Polynomial Model

### Model vs Actual Data:

![Model vs Actual Data](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModelVsActualData.PNG)

### Model vs 3 Day Lag period

![Model vs 3 Day Lag period](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModeledInfectionsVs7DayLag.PNG)

### Model vs 3 Day Lag period with standard error

![Model vs 3 Day Lag period with standard error](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModeledInfectionsVs7DayLagWithStandardError.PNG)

### 3 Day Lag Model on calendar dates

![Model vs 7 Day Lag period with standard error](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/7DayLagModelCalendarDates.PNG)
