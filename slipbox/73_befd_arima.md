# ARIMA models
## Interpreting ARIMA models
How do we interpret an $\textrm{ARIMA}(p, d, q)(P, D, Q)_s$ model?
We know that:
- $p$ is the parameter of an auto-regressive model that predicts future values of the time series based on the past $p$ observations of the series itself;
- $q$ is the parameter of a moving average model, that predicts the next value of the series based on the previous $q$ prediction errors;
- $d$ is the degree of first-order differencing, i.e. how many timesteps before the current observations should the subtracted observation be.

The second ARIMA model with parameters $P, D, Q$ is in general used to model the seasonal behaviour of the series. But how? The main difference between the first and the second ARIMA model (the non-seasonal one and the seasonal one) is that the second one of order $s$ will include in the modeling (either in the AR, MA or differencing part of the model) directly the values at $s$ timesteps before the current one, rather than *all up to the one $s$ timesteps before*. Then, that value will be modeled considering the $P$ values before it, the $Q$ prediction errors before it and possibly differenced up to $D$ timesteps before it.

[45_befd_bias_variance](45_befd_bias_variance.md)