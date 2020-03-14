# Covid19GermanyEstimates
Estimating the spread of Covid19 in Germany.

# How to interpret this model

This is simply a mathematical prediction based on the number of reported cases and a model developed using outbreaks of other illnesses such as ebola. The biggest issue is that I'm fitting my model to the number of reported cases. This means the predictions are heavily influenced by the way cases are found through testing. This means unless germany is testing a sample size much larger than the actual outbreak, my prediction will not accurately predict the real number of infections and could be influenced by a number of factors. 
For example, my model (and the actual data) seems to predict around 3 days case doubling. While this matches what other countries are seeing in their screenings, it is not a reliable way to predict the actual growth of the outbreak. 
There have been a number of studies that are trying to simulate the outbreak using highly complex simulations and their finding usually amounts to a case doubling period of 5-7 days.
A shorter case doubling rate in germanys data might imply that we're catching up with the real number of cases or that due to societal factors the cases are actually doubling faster in germany currently or a number of other things. 
This model therefore should only be used as a rough estimate of "how bad will shit hit the fan?" and not for any other purposes.

# Model

Numerical model is based on the formulae suggested in this paper:
https://arxiv.org/ftp/arxiv/papers/1512/1512.01389.pdf

Parameters are then worked out using GRG nonlinear analysis in excel with multistart to find a global minimum for parameter convergence.
GRG Nonlinear is set to find a minimum for the sum of quadratic errors between the model estimates and the known data.
I then offset the estimated data by -7 days in order to get a glimpse on what the real number of infections might be.

Source for number of infections by date is:
https://interaktiv.morgenpost.de/corona-virus-karte-infektionen-deutschland-weltweit/

Currently, the situation in germany is difficult in that counting is decentralized, which means all reports are off by some degree. Berliner Morgenpost is trying to keep the time at which they count cases consistent and source their data from the local health authorities, which hopefully makes their data very close to reality.

# Current Estimates

## Model vs Actual Data:

![Model vs Actual Data](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModelVsActualData.PNG)

## Model vs 3 Day Lag period

![Model vs 3 Day Lag period](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModeledInfectionsVs7DayLag.PNG)

## Model vs 3 Day Lag period with standard error

![Model vs 3 Day Lag period with standard error](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModeledInfectionsVs7DayLagWithStandardError.PNG)

## 3 Day Lag Model on calendar dates

![Model vs 7 Day Lag period with standard error](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/7DayLagModelCalendarDates.PNG)
