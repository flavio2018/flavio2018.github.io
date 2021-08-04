[56_befd_effective_dof](56_befd_effective_dof.md)

# Generalized Additive Models
GAMs allow to generalize the non-parametric, non-linear approximation of unknown function to the case of more than one (or two) predictors. The core idea behind GAMs is to approximate the value $y=f(x), x \in \mathbb{R}^n$ with a function that is composed by a sum of non-linear functions applied to each predictor $x_k$:

$y = \alpha + \sum_j f_j(x_j)$

This allows to introduce non-linear effects on each predictor flexibly, without having to manually introduce them and specify them in advance, letting the fitting process find the non-linear form which is more suitable for the data. 
Another advantage of GAMs is that since they are additive we can still inspect and formally evaluate the impact of a single predictor on the estimation, keeping the other predictors fixed.

The functions $f_j$ are indeed initially unknown, but they can be estimated using any kind of smoother such as splines or local regression. The estimation process for the functions $f_j$ builds on the fact that

$f_j(x_{ji})=y_i - \alpha - \sum_{k \neq j} f_k(x_{ki})$

The algorithm used for the estimation procedure is called *backfitting* and repeats the following two steps to estimate any function $f_j$:

$f_j(x_{ji}) ← y_i - \alpha - \sum_{k \neq j} f_k(x_{ki}), \forall i=1,...,n$
$f_j(x_j) ← S_j · f_j(x_j), x_j \in \mathbb{R}^n$
$f_j(x_j) ← f_j(x_j) - {1 \over n} \sum^n_{i=0} f_i(x_{ji})$

$S_j$ is a smoother that can be different for each predictor $x_j$ and its relative function $f_j$.