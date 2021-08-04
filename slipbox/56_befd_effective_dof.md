[54_befd_splines](54_befd_splines.md)

# Effective degrees of freedom
The problem we are trying to solve is that of finding a way to build inference tools also for non-parametric models. With linear models, we have that the variance of the response can be completely decomposed into the sum of error variance and estimator variance. Furthermore, we know that under the hypothesis of Gaussian errors, both of these terms follow a $\chi^2$-ish distribution, with degrees of freedom and other factors depending on the model.

This doesn't hold for non-parametric models. However, most of the non parametric models ([54_befd_splines](54_befd_splines.md), [54_befd_splines](54_befd_splines.md)) can be expressed as a linear transformation of the response. Although the variance of the error terms does not follow exactly a $\chi^2$ distribution, we can observe empirically that it gets close to one (and the same goes for the variance of the prediction); of what degrees of freedom, though?

The fact we want to exploit is that for an $X ~\sim \chi^2_p$, it holds that $\mathbb{E}[X]=p$. So, if we compute the expectation of the sum of squared errors we can use that value as a proxy for the degrees of freedom of the distribution that empirically resembles a $\chi^2$. To compute the expected value we use this lemma [54_befd_splines](54_befd_splines.md), and the decomposition of the error as $\epsilon = (I_n - S)y$, where $I_n$ is the identity matrix of order $n$ and $S$ is any smoother we use to build predictions.

Thus we have that 
$\mathbb{E}[Q]=\mu^T(I_n - S)^T(I_n - S)\mu + \sigma^2\textrm{tr}(I_n - S)^T(I_n - S)$, 
where $Q$ is the sum of squared errors. By introducing some approximations, we have that $\mathbb{E}[Q]=\sigma^2[n-\textrm{tr}(S)]$, where $\textrm{tr}(S)$ will be the effective degrees of freedom for the smoother.