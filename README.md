# Covid19GermanyEstimates
Estimating the spread of Covid19 in Germany

# Model

Numerical model is based on the formulae suggested in this paper:
https://arxiv.org/ftp/arxiv/papers/1512/1512.01389.pdf

Parameters are then worked out using GRG nonlinear analysis in excel with multistart to find a global minimum for parameter convergence.
GRG Nonlinear is set to find a minimum for the sum of quadratic errors between the model estimates and the known data.
I then offset the estimated data by -7 days in order to get a glimpse on what the real number of infections might be.

