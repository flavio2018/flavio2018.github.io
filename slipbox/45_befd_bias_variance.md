## Bias-variance trade-off
- polynomial functions models: as the degree increases the fitting gets better
- R² and residual deviance: they always increase and decrease, respectively, when the modeling function fits data better; that can be a sign of *overfitting*.
- mean squared error
	- decomposition of MSE in bias² + variance terms: $\mathbb{E}[\hat y - f(x')]² + var(\hat y)$. Clearly, as the modeling function approximates better and better the data points, the bias decreases - at expense of the variance (think of a super complex polynomial).
- testing the goodness of fit on training data is not reliable → we need to evaluate the models using:
	1. training & test sets (+ validation set); (ok if we have enough data left for training)
	2. cross-validation folds (leave-one-out c.v.)
	3. information criteria
- the rationale behind information criteria is to correct the residual deviance (sum of squared residuals), which is an overly optimistic measure of model quality. We do so introducing a penalty for the model's complexity. Depending on what penalty we introduce we have a different criterion, usually either BIC ($p·\log{n}$) or AIC ($2p$). 
	- The choice of the penalty function is based on the following reasoning: provided that we use the number of parameters $p$ of the model as an indicator of its complexity, and that the expected increase in the log-likelihood of the model when an additional parameter is introduced is $1$, then the penalty must be at least $p$, i.e. the information criterion is a value which has a linear increase in the number of parameters. This remains true for AIC, while is not anymore true for BIC.

[46_befd_KNN](46_befd_KNN.md)