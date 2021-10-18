[45_befd_bias_variance](45_befd_bias_variance.md)

# Non-parametric models
- non-parametric models: we still rely on the general formulation $\hat y = f(x) + \epsilon$, but we don't think that $f(x)$ is a polynomial anymore.
- however, different approaches to non-parametric modeling carry different assumptions; so, $f(x)$ is not chosen *completely* freely

## K-Nearest Neighbours
The technique is the practical solution to the theoretical problem of building an estimation function which is the average of the points $y_k$ corresponding to a value $x_k$. We would like to do so because, theoretically, if we choose to measure errors using a quadratic loss function such as the mean squared error, the best possible predictor will be the mean of the predictions corresponding to a data point.

However, a data point could never be present in our observations, hence we rely on its *$k$ nearest neighbours*. The modeling function is thus never *fit* to the data, but simply applied to each new data point to obtain the prediction.

In this case, the smallest the $k$, the greater the variance of the predictions (the resulting function will be less smooth, since we average few values).

$k$ --> $+\infty$
*Bias* --> $+\infty$
*Variance* --> $0$

k-NN is good when:
- the true relationship is highly non-linear: we have better performances w.r.t polynomial models measured with MSE (possibly overfitting).
- there dimensionality is not too big: space is bigger, data is sparser and finding the neighbours becomes more difficult

### Evaluation
We can still evaluate the model's performance with k-fold CV trying to find the best trade-off between bias and variance. We can measure the MSE.