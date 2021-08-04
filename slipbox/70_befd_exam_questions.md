1. *Describe the problem of multicollinearity in a linear regression model and explain how it may be detected.*
Multicollinearity is an issue that arises in linear regression models when two or more predictor variables are correlated. This is an issue because the amount of variance explained by one variable will be covered by the other collinear variables. ==In particular, the precision of the estimate of correlated variables will be low; consequently, the SE of the estimation will be high and the $t$ statistic will be low. Since we consider this statistic to establish the significance of a predictor by taking the associated estimated coefficient into account, we may fail to reject the null hypothesis that a variable is actually significant.==
The problem of correlation between two predictors can be detected by computing some correlation measures between every pair of predictors (e.g. Pearson's correlation coefficient). ==When more than two variables are correlated, we may use the Variance Inflation Factor measure: this can be computed for each predictor in the MLR model and measures the ability to predict the values of a variable using the others as predictors: $1 \over {1 - R^2_j}$, where $R^2_j$ is the $R^2$ of the model fitted on all predictors but the j-th to predict it.==

2. *What is the autocorrelation function and how it may be used?*
The autocorrelation function measures the correlation between the values of a time series at various intervals of distance (i.e. the correlation between values that are 1,2,..,$k$ time steps apart).
The autocorrelation function is very useful when trying to model a time series using a simple linear regression model. In this setting, we will try to predict the value of the time series simply knowing its timestep. Therefore, measuring the ACF of the model's residuals, we can easily see if there is a seasonal pattern in the series that our model is not able to capture. Ideally, the ACF of the residuals should be similar to white noise; if it's not, something more is left to be explained.
==The ACF can also be plotted for clearer interpretation in the correlogram. The plot shows the auto-correlation function value of the time series for each value of lag $k$. The plot includes two horizontal bands in correspondence of the interval of values of the ACF in which the autocorrelation is not considered to be significant. If we observe ACF values above the significance threshold consistently at timesteps that are multiples of some quantity, we can detect a case of seasonal behaviour in the series. The general trend of the series is also reflected in the correlogram, as trending values will generally be correlated with their predecessors. Ideally, the correlogram of residuals of a model should show no significant values of the ACF at any time lag, meaning that the residuals are totally random and all the variance left to be explained is caused by the random variability of the residuals.==
==Autocorrelation of residuals can even be formally tested using the Durbin-Watson test. The test assumes that the residuals follow a structure that involves a random component and a correlation component with other residuals at distance k. If the residuals are not autocorrelated, the correlation coefficient term should be zero - and this is indeed the null hypothesis of the test.==
	
3. *What are the elements to consider in evaluating the performance of an innovation diffusion model?*
Modeling the diffusion of an innovation is a task with very important practical outcomes, due to its applicability to a wide range of scenarios. Assuming to have a dataset of past observation of the innovation diffusion process which we can use to fit a model, we can firstly evaluate the model based on how well it explains the values it was fitted to. Taking into account the ACF of residuals of the model, we can first check that they are randomly distributed. Then, if we must compare the model with other possible models, we might take into account information criteria such as BIC or AIC, or other model selection techniques such as k-fold or leave-one-out cross validation.
However, the most reliable evaluation of the model is its ability to actually predict future values of the time series. Therefore, when the future values will be available (if they are not at the moment of model fitting), we can compare the model's forecasts in a future interval of time with the observed values in the same period, computing some error metric such as MSE between predictions and observations.
Depending on the real world situation which we will use the model in, we may also prefer a class of model over others, e.g. due to its interpretability qualities or to its ability to model time series in the particular area of application considered.

4. *What is the role of effective degrees of freedom in a non-parametric regression context?*
[56_befd_effective_dof](56_befd_effective_dof.md)
In linear regression models, we can compute the confidence interval ~~of a variable's coefficient~~ of the ==predicted response== relying on the assumption that the ~~coefficient~~ ==total variability of the predicted response can be decomposed in a sum of two terms: the variability of the estimator and the variability of errors.== We also know that both terms will follow a chi-squared distribution under the assumption of normality of residuals. ==The degrees of freedom of the chi-squared distribution exactly depend on the number of predictors used in the model and on the number of samples used to fit the model.==
Due to the non-linear behaviour of the non-parametric regression models, the assumption of chi-squared distribution ~~of the coefficients~~ ==of the variance of the error term and of the predictor== is not guaranteed anymore. ==However, most non-parametric models are linear estimators of the response, and it is evident empirically that the variance of both terms approximately follows a chi-squared distribution. The role of *effective degrees of freedom* is precisely that of estimating the degrees of freedom of the approximate chi-squared distribution of the variance of the predictor and error terms.==
The main result we use to compute the effective degrees of freedom for the chi-square distributions of predictor and error term is that the expectation of a chi-squared random variable is equal to its degrees of freedom. Therefore, if we compute the expectation of the sum of squared errors we will get a proxy for the degrees of freedom of their distribution.
Knowing the effective degrees of freedom, we can build something similar to confidence intervals for inference about the value of the response of a non-parametric model. However, this interval in which the true response will fall with a given probability $p$, cannot be considered a proper confidence interval. Indeed,  differently from confidence intervals, two bandwidths (a positive and negative one) will be created around the prediction, of two different sizes, due to the fact that the hypothesis of normality of the residuals is not guaranteed to hold. in any case, even if it did, the interval computed with effective degrees of freedom could only be considered a confidence interval locally, for the point where it was computed for, and not valid for the whole interval of values that the model gives an estimate for. 

5. *Describe advantages and drawbacks of the KNN approach for a regression problem.*
[46_befd_KNN](46_befd_KNN.md)
==Assume to choose to model a function using the mean of the possible values that the function can have in a given point $x$. This approach is reasonable if we consider that using an error metric that averages the errors (such as MSE), the mean value of the predictions corresponding to a given point is the best result we can get.==
The KNN approach to solve a regression problem does not require to actually train or fit a model to data. Indeed, this can be called a memory-based approach, since it consists in estimating the value of a function $f(x)$ computing the mean of the known function values of the $k$ closest points to $x$ in the dataset. 
The approach is certainly very simple and does not require to spend training time. If the known samples are many, however, this method can become very memory demanding. The method can work poorly if the data are very sparse, or if we want to compute an estimate in an interval where we don't have any known value, since the "closest" known values would probably be completely misleading and the estimate would be strongly influenced by that.
==Naturally, we need to choose $k$ taking into account that the choice of the parameter is a trade-off between bias and variance of the model (the former will grow with $k$ while the latter, intuitively, will decrease with it).==

6. *How can you evaluate the fitness and significance of parameters in a linear regression model?*
In a linear regression model we want to estimate the values of a function assuming that it may be modeled with an approximator of the form $\hat y = f(x)=\beta_0 + \beta_1 x_1 + ... + \beta_n x_n + \epsilon$. We can estimate the values of the beta coefficients in the linear regression model using the Ordinary Least Squares method, which consists in finding the values of the coefficients that minimize the sum of squared difference between predictions and observations. Assuming that the errors are homoschedastic, independent and normally distributed, we may also use a t-test to evaluate the significance of the model's parameters. A value of the statistic above 2 will indicate poor significance of the parameter in the model. Furthermore, we may compute the standard error of the estimate, which will inform us about the precision of the parameter estimate. ==The t statistic is defined as $t = {\beta_j \over SE(\beta_j)}$==
==We can also test a more general significance of the model using a Fisher's F test, having as null hypothesis that all beta coefficients are zero; in this case, a value of the statistic above 4 tells us that at least one variable is significant. The F test is a sort of signal vs noise ratio test, since we have at the numerator the ESS and at the denominator the RSS.==

7. *Explain how local regression is structured.*
[51_befd_local_regression](51_befd_local_regression.md)
The idea behind local regression is to build a local estimator of a function building on the first order Taylor approximation of the function in a given point: $f(x) = f(x_0) + f'(x_0)(x-x_0) + \epsilon$.
Building on this result, the basic idea is to compute *local approximations* of the function $f$, computing the Taylor approximation of the function centered in each $x_k$ point we have in the dataset. Since we don't know the function, we will need to estimate the value of the terms $f(x_0) := \alpha$ and $f'(x_0) := \beta$, where $x_0$ is the value which we want to estimate the corresponding function value of. We will thus want to minimize the sum of squared difference between the estimate of the function computed with the Taylor approximation centered in the point $x_0$ and the one we know, for every point $x_k$ in our dataset. Furthermore, every squared difference will be weighted by a function $w_h(x_k-x_0)$, called kernel, which will assign more weight to approximations computed with points closer to $x_0$ (they will be likely provide a more reliable estimate). A common choice for the $w$ function is the Gaussian, although the most important choice is the parameter $h$ that regulates the *width* of the interval around the point $x_0$ that will receive higher weights. A big value of the $h$ parameter increases the bias, whereas smaller values increase the variance of the local regression estimator.

8. *What are the variables that compose a BASS model?*
An innovation diffusion process can be described using a biological metaphor as having a life cycle composed of four stages: introduction, growth, maturity and decline.
The BASS model is built on the assumption that the life cycle of an innovation diffusion process can be explained taking into account only the actions of two kinds of individuals: innovators and imitators. The former are the ones that are responsible for the early adoption of the innovation, and thus of the introduction phase. Their actions are then less and less important in describing the evolution of the innovation diffusion as the imitators grow, making the process go into the growth, maturity and, eventually, decline stages.
The BASS model describes this dynamics using a simple nonlinear model that involves only three parameters ($p, q, m$), estimated from the data:
==$z'(t) = {(p + q{z(t) \over m})(m - z(t))}$,==
where $z(t)$ is the number individuals affected by the innovation diffusion (or, practically, the number of items sold in business scenario) at time $t$, and $m$ is the market potential, i.e. the maximum number of individuals that can be involved in the process.
==The interpretation of this differential equation is that the growth of the diffusion in a given moment in time $t$ depends on the residual market $(m - z(t))$, namely the number of people still left untouched by the innovation, and is driven by innovators at initial stages of the process (${z(t) \over m} \simeq 0$), while their impact is more limited at more advanced stages (${z(t) \over m} \simeq 1$). Common initial quantities for the $p$ and $q$ parameters are 0.001 or 0.01 for the former and 0.1 for the latter.==
One of the main assumptions of the BASS model is that the market potential is a fixed quantity. This can be a limitation of the model, which is the motivation for the development of GGM.

9. *Which are the parameters that compose an Auto-regressive Integrated Moving Average (ARIMA) model?*
ARIMA models combine three modeling elements: Auto-regressive models, moving average models and differencing (integration). 
Auto-regressive models are linear models of time series that are based on the hypothesis that future values of the time series depend on the past values ==of the series itself== according to a linear regression model:
==$y_t=\beta_{t-1} y_{t-1} + ... + \beta_1 y_1 + \beta_0 + \epsilon_t$==.
~~This kind of models effectively explains the trend of a series, since the relationship between past and current values is taken into account~~. ==In general, it is useful if a strong autocorrelation is observed in the correlogram, since the model can flexibly take into account past values up to p values before the current ones and learn the correct importance given to each of them with the parameters==.
Moving average models ==use instead the multiple linear regression framework to model the dependency between future values of the time series and past prediction errors:
$y_t=\beta_{t-1} \epsilon_{t-1} + ... + \beta_1 \epsilon_1 + \beta_0 + \epsilon_t$==.
==These kind of models allow to take into account the effect of unobserved shocks, reflected in the past prediction errors, on the current values of the series.==
The most important thing to keep in mind when working with ARMA models is that they deal with stationary time series, therefore the series is made stationary if it's not through differencing. The third ingredient of ARIMA models is thus integration of the values of the series, i.e. subtracting to each value of the time series the past value distant k steps from it: $y'_t = y_t - y_{t-k}$. The integration can also be applied more than once, in which case we talk about second order integration of the series. This is an alternative strategy to deal with ~~seasonal~~ trending behaviour of time series.
An additional ARIMA model can be used to deal with seasonality [73_befd_arima](73_befd_arima.md).

10. *Describe the structure of the GAM model and how is it fit.*
[59_befd_GAMs](59_befd_GAMs.md)
- generalization multiple linear regression model
- procedure updating smoothers 
- maintaining additivity

---
 
The general additive model is a generalization of a multiple linear regression model that flexibly allows to model nonlinear dependencies between the predictors and the response variable. The GAM has the structure:

$y = f_1(x_1) + f_2(x_2) + ... + f_n(x_n) + \epsilon$,

where the functions $f_1, ..., f_n$ can be freely chosen and are usually non-parametric models such as regression splines or smoothing splines or local regression models. The flexibility of this class of models is a consequence of the fact that the *specific form* of the functions (i.e. their parameters) is found through an iterative procedure called ==backfitting== minimizing a loss function on a training set.

The procedure exploit the fact that the value of each function in a point $x_k$ depends on that of the the other ones in $x_k$ and on the value of the response variable corresponding to $x_k$. Therefore, the values of the functions' parameters are iteratively approximated by first computing the value of 

$f_k(x_k) = S[y - \sum_{j \neq k} f_j(x_j)]$

for each known value of $x_k$ (where $x_k$ represents the k-th variable, not the k-th example), ==and where $S$ represents the smoother chosen to approximate the function==. ==The second step would then be to update the function value subtracting to the current value all the values computed in the step before, averaged.==

11. *General overview of the method used to evaluate well a model (train-test, Cross validation).*

Model selection is a critical part of any modeling enterprise. There exist two main kind of model evaluation methods: cross validation and information criteria. 

The former method relies on prior selection of some evaluation metrics that are different from the loss function that we optimize in model training. An example for these metrics could be accuracy, precision or recall; we choose these metrics depending on what is the goal we want to accomplish when building the model. Then, we split the training data into k folds, and we train each model k times: each time we use k-1 splits of the data to train the model and the remaining one to test it, using the metrics we have selected in advance. In the end, we can average the value of the metrics on the k folds and compare the averaged values computed for each model.

The second class of methods attempts to take into account model complexity and assesses the model quality more indirectly. Information criteria rely on the computation of the log-likelihood function for the model's parameter on the observations. Then, depending on the specific criterion, a complexity penalty term is added, usually considering the number of variables in the model as a proxy for its complexity. For example, the Bayes information criterion (BIC) uses the term $2log(n)$ as a complexity penalty.

12. *Which are the indicators that help us to select the model with the best performance? If we are in the case of two nested model?*
- $R^2$
	- analysis of residuals
- Durbin-Watson test
- $R^2_{adj} = 1 - {(1-R^2)(n-1) \over (n-k-1)}$
- $\tilde R^2 = {{SSE_1 - SSE_2} \over SSE_1}$  for nested models.

13. *Explain why it is necessary to find a trade-off between bias and variance.*

As model complexity grows, the ability of the model to fit the training data increases. The typical example of this phenomenon is the comparison of polynomial models with increasing degrees. As the polynomials get more complex, they fit the data better (the bias decreases) but the predictions vary a lot in the range of values of the training data (variance increases).

The fitted model should be able to capture the true data generating process, which created the specific set of data that the model was trained on. As the model gets better and better at predicting training data, it also gets farther away from the true shape of the data generation process, in a process called *overfitting*. When the model will be tested on the true data, its ability to generalize will be hindered by the fact that it was overfitted to the training data. Therefore, it is necessary to find a trade-off between bias and variance to allow the model to generalize on unseen data of the original data generation process.

==MSE = bias^2 + variance==

14. *What are the reasons why is better to evaluate a model with AIC than Deviance and which are the differences?*

Deviance is a measure of goodness of fit of a model that generalizes the idea to use sum of squared residuals (SSE) to evaluate the model fitting in OLS fitted models to models fitted using log-likelihood.

As deviance includes a measure of the log-likelihood of the model's parameter given the observations, it can be considered a way to estimate the goodness of fit of the model which is included in information criteria, and particularly in AIC. AIC and other information criteria also have the advantage to take the model's complexity into account, thus helping to prevent overfitting and penalizing bigger models.

15. *Describe the structure of the interpolating splines.*

[54_befd_splines](54_befd_splines.md)

Splines are composite functions made up of fragments of continuously differentiable functions that are connected in specific points of the domain called *knots*. Splines can be used to flexibly model an unknown function, usually choosing polynomials as basic components of the spline.

In particular, it is common to use third-degree polynomials, that must satisfy the following conditions:
- the value of their derivatives in the knots where they connect to one another should be the same, up to the ==2nd== degree;
- they should have the same, defined values in the knots;
- the derivatives of the leftmost and rightmost splines should be equal to zero.

The last condition characterizes ==natural cubic== splines, and is needed to completely determine the form of the spline according to just the former conditions. The actual parameters of the third-degree polynomials are then chosen by fitting them to the training data with the OLS method.

16. *Explain the intuition behind the Gradient Boosting.*

[64_befd_gradient_boosting](64_befd_gradient_boosting.md)

- Gradient Boosting = gradient descent + boosting

Boosting is a technique that builds on a simple idea: given a linear model, we will always have residual, i.e. the prediction errors of the model on the training samples. We can then always fit a new model that, for each sample, tries to predict the error that the previous linear model was making on that sample. ==Typically, the model fitted on the residuals is a regression tree.== Furthermore, this process can be iteratively repeated up to whatever "deepness" we desire. We will then have, formally:

$f_1(x) = \beta_0 + \beta_1 x +\epsilon_1$
$f_2(x) = \beta_0 + \beta_1 x + \epsilon_2 = \epsilon_1$
...

Thus the final estimation of the function will be given by

$f(x)= f_1(x) + f_2(x) + ... + f_n(x)$

However, since we are using the prediction errors to adjust the function's parameters, we can see that the Boosting method is analogous to the gradient descent technique, that optimizes the parameters of a function based on the value and direction of its negative gradient. Indeed, in the case of linear models, the negative gradient is exactly the negative of the prediction error.

17. *Why do we add an exponential or rectangular shock in a BASS model, and how do we do that?*
The standard bass model allows us to interpret a time series related to an innovation diffusion process starting from some assumptions: fixed size of the market potential, involvement of two kinds of actors in the diffusion process - innovators and imitators.

However, the model assumes a "natural" course of events, which presumes that the diffusion process is only influenced by the action of the actors mentioned above. In reality, it often happens that external factors to the diffusion process affect the process itself: the entrance of a competitor in the market, the approval of some legal provision, the outbreak of a pandemic...

This is exactly the reason why we include exponential or rectangular (or other kinds of) shocks to the Bass model. The former are better suited to model economic factors, such as the entrance or default of a competitor, while the latter are good tools to model the effect of legislative initiatives.

In practice, adding a shock to the standard Bass model consists in adding a ~~term~~ ==factor== to the model of the form $x(t)$, where the function $x$ can either be an indicator function or an exponential function (depending on the kind of shock) ~~and the parameter $\alpha$ indicates the significance of the shock~~. ==The exponential function has three parameters: sign and magnitude of the shock $c$, memory parameter $b$ and starting point of the shock $a$. If the parameter $a$ is not significant, it means that probably the introduction of a shock is not justified. The indicator function has three parameters as well: sign and magnitude of the shock, starting and ending time.== One important thing is that the interval of time where the shock might have occurred should initially be specified by the modeler.
==The two shocks can be used together.==

18. *Brief explanation of the reasons that lead to the creation of the GGM bass model*
The standard bass model allows us to interpret a time series related to an innovation diffusion process starting from some assumptions: fixed size of the market potential, involvement of two kinds of actors in the diffusion process - innovators and imitators.

However, in real scenarios, the assumption of fixed market potential is often a limiting one. This is the issue that the GGM was designed to deal with. The model is build on a further assumption that the diffusion process can be divided into two sub-phases: ~~incubation~~ ==communication== and ==adoption==. The first phase is the one that occurs earliest in time and corresponds to the phase of spreading of the innovation. The second phase is the one in which the innovation diffusion reaches its peak and declines. ==The key intuition is, therefore: *the size of the market potential depends on the communication phase*. This is translated into model form since we have that $m(t)=k \sqrt{F^*(t)}$, i.e. the market potential now depends on time and is modeled according to a new Bass model, with its own $q$ and $p$ parameters.==

The GGM, building on this idea, fits two separate Bass models for the two stages of the diffusion process.

19. *Explain how the parameter $h$ in local regression is related to the bias/variance trade-off dilemma, and how it is possible to chose it.*
Local regression consists in approximating a function in a range of values building on the Taylor approximation of the function computed in several points of the interval. The loss function used to approximate the parameters that specify the Taylor approximation of the function includes a weighting term that consists of a function, with parameter $h$, that assigns a weight to the distance between the point where the function is being evaluated ($x$) and the center of the Taylor approximation of the function itself ($x_k$).

The parameter $h$, also called the smoothing parameter, regulates how much weight will receive the evaluation points that are further from the center $x_k$. Since the further the points, the less accurate the function approximation, the choice of the parameter $h$ represents a trade-off between bias (more accurate local estimates) and variance (less regular function) of the final function approximation.

The most common way to choose the parameter is via k-fold cross validation comparing some error metric, since we want to improve the generalization of the model on unseen samples during training.

20. *What is loess?*
Loess is a technique that modifies local regression introducing the idea of constant number of points considered for smoothing.

Whereas in local regression the $h$ parameters specified an interval of values around the center of the approximation that were considered "close enough" to receive a consistent weight (and therefore depend on the density of data points in each particular region of the domain), in loess we define a *fraction* of the samples that must be considered when weighting the loss function of the local regression.

This of course poses the problem of very sparse domain intervals, for which a large the fraction of values to be considered could lead to put too much weight on very far values.

> One key difference from ==linear regression==, though, is that it's not possible to actually compute confidence intervals for the model's predictions, but only something like ==estimation of the variability of the predictions==, that give some information about the accuracy of the predictions but are not symmetric around the points (errors are not Gaussian) and are not of fixed size for the whole interval of predictions (we don't have $z$ or $t$ points).

21. *How is it possible to smooth a spline?*
Regression splines can become very "bumpy" when they are fit with many knots. This can cause a similar situation as fitting a high-degree polynomial to a set of points: overfitting. Indeed, the function will be allow to take a more and more complex form that better fits the observed samples, but this will probably hinder the model's ability to generalize on unseen data.

Smoothing splines are simply regression splines where a smoothing (or regularization) term is added to the loss function solved with the OLS method. The regularization term is one that tries to capture the *smoothness* of the function by computing the value of its ==squared second ~~integral~~ derivative==. The term is also multiplied by a parameter $\lambda$, that is called smoothing parameter and controls how much weight is given to the regularization term. The smoothing parameter is usually selected with k-fold CV.

22. *Which are the similarity and differences of degrees of freedom and effective degrees of freedom*
Degrees of freedom are a key parameter that define the shape of chi-squared distributions and its derivatives (Fisher's F). In linear regression models, we know that the total variance of the responses can be decomposed in variance of the predictions plus variance of the error term. Furthermore, we know that both terms follow a chi-squared distribution with $p$ and $n-p-1$ degrees of freedom, respectively. This allows us to fill the ANOVA table of the MLR model and to compute the Fisher's F exact test on the significance of the parameters.

Although most non-parametric models have a linear form (they can be expressed as matrix operators on the dependent variable, called smoothers), it is not possible to decompose the variance of the response in terms of predictions and errors of the models in the same way as we do with MLR models. In particular, it's not formally true that the two terms follow chi-squared distributions. However, empirically it can be shown that they do *approximately* follow one, in practice. To assign to these distributions their degrees of freedom we compute then the effective degrees of freedom for the smoother.

The main intuition that we used to do so is that $\mathbb{E}[Q] = p, Q \sim \chi^2_p$. Therefore, we can compute the expectation of the value of the smoother and obtain from it the effective degrees of freedom for both the response and error terms of the model.

