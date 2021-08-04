[46_befd_KNN](46_befd_KNN.md)
# Local regression
Local regression is an alternative to KNN for local approximation of a noisy, unknown data generation process. It relies on the assumption that the original function to be approximated is smooth and differentiable at least one time. Indeed, the method uses the first-order Taylor approximation of the function in a given point. The gain in generalization w.r.t to the linear model is that we do not assume that the function is any kind of parametric function, but we only require minimal conditions to be satisfied.

Given the observation $x_0$, we want to estimate $y_0=f(x_0)$. It holds true that $f(x)=f(x_0)+f'(x_0)(x-x_0) + \epsilon$ (first order approximation). So, we can locally approximate neighboring points to our observations using the formula above. Of course, since we do not know $f$, $f(x_0)$ and $f'(x_0)$ are unknown. 

We can call the former $\alpha$ and the latter $\beta$, and define a procedure to estimate them for any given data point $x_k$:

$min_{\alpha, \beta} \sum_i [(y_i - \alpha - \beta(x_i - x_k))]^2 · w_h(x_i - x_k)$

where $(x_i, y_i)$ are the known data points, the function $w_h$ weights the terms in the sum of squares placing more weight when the distance $(x_i - x_k)$ is small. Then, having some estimates for $\alpha$ and $\beta$, we can build the first-order approximation of the function in the point $x_k$ and finally estimate $y_k$.

If we iterate over several values of $x_k$, we can build a whole estimate for the function in an interval of values (which necessarily will correspond to the one in which we have observations).

We have the possibility to choose:
- the **kernel**, i.e. the function $w_h$ which weights the terms of the sum. A usual choice for this is the density function of the normal distribution, but other choices can be the biquadratic or tricubic functions.
- the **smoothing parameter** $h$, which is the most important thing. As the name suggests, this will regulate the smoothness of the function estimate. This is also critical since it can be proved that the bias and variance of the estimator $\hat f$ will be respectively directly proportional to $h^2$ and inversely proportional to $h$. Therefore, when choosing $h$ we are making a trade-off between bias and variance. The choice of $h$ is not feasible analytically, so we usually rely on cross validation and information criteria.

It can also be proved that the estimate for a generic value $x_k$ has a **closed form**. Hence, we can write the estimate of a single value as a vector operation and the estimate for a batch of values as a matrix operation.

Finally, it can be proved that the expectation of the difference between the true and the estimated value of a function $f$ is $O(n ^{-4/5})$, which is bigger than $O(n^{-1})$ which holds for linear models when they are successful; hence, local regression models are intrinsically less efficient than successful linear models.

## Variable bandwidth
In some occasions, i.e. when data are very sparse, it might be useful to consider an interval of variable size in which samples of observation are taken to solve the local regression problem. In practice, we don't define a formula for a variable bandwidth, but rather we choose a *fraction* of samples which must be considered when solving the local regression problem for a given observation. Thus, the number of observations will always be the same, no matter how dense the neighborhood of our observation is. 

It is possible, in principle to build confidence intervals for the parameters in a similar way as it is done for parametric models, defining a *pivotal quantity* which is analogous to the $z$-points or $t$-points used in z-tests or t-tests. However, since the bias cannot be ignored in this case as it is commonly done in the parametric case, in practice we build intervals which give an indication of the variability of the estimation of the predictions, and consequently of the function $f$. These are built as
$(\hat f(x) - z_{\alpha/2} · SE(\hat f(x)),  \hat f(x) + z_{\alpha/2} · SE(\hat f(x)))$
and *are not* to be considered confidence intervals, due to the fact that the bias is not negligible, and therefore two different bandwidths are produced (for the positive and negative sides) when the formula is applied to every point on the x axis. Even if the bias were zero, it would still only be valid locally, and not for the whole function.

The local linear regression (with fixed bandwidth) can be applied also in the 2-dimensional setting. Here, the linear problem which could be solved analytically in the mono-dimensional case can now be solved with a matrix operation.

[46_befd_KNN](46_befd_KNN.md)