# Covid19GermanyEstimates
Estimating the spread of Covid19 in Germany

# Model

Numerical model is based on the formulae suggested in this paper:
https://arxiv.org/ftp/arxiv/papers/1512/1512.01389.pdf

Parameters are then worked out using GRG nonlinear analysis in excel with multistart to find a global minimum for parameter convergence.
GRG Nonlinear is set to find a minimum for the sum of quadratic errors between the model estimates and the known data.
I then offset the estimated data by -7 days in order to get a glimpse on what the real number of infections might be.

# Current Estimates

## Model vs Actual Data:

![Model vs Actual Data](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModelVsActualData.PNG)

## Model vs 7 Day Lag period

![Model vs 7 Day Lag period](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModeledInfectionsVs7DayLag.PNG)

## Model vs 7 Day Lag period with standard error

![Model vs 7 Day Lag period with standard error](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/ModeledInfectionsVs7DayLagWithStandardError.PNG)

## 7 Day Lag Model on calendar dates

![Model vs 7 Day Lag period with standard error](https://github.com/BenK-XOA/Covid19GermanyEstimates/blob/master/Covid19_Germany_Estimates/Graph_Pictures_08-03-2020/7DayLagModelCalendarDates.PNG)
