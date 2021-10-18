[59_befd_GAMs](59_befd_GAMs.md)

# Gradient boosting
*Gradient boosting = gradient descent + boosting.*

Boosting was a technique initially developed for classification in which badly classified examples were given more weight in the training process so that the learning algorithm "focused" more on those.

The core idea behind gradient boosting applied to regression problems is to, basically, model the residuals of a linear regression model using another model, e.g. a regression tree. The new model will be fitted on $(x_1, r_1), ..., (x_n,r_n)$ samples, where the $r_k$ are the errors of the linear regression model. We basically obtain a new model: $f_2(x)=f_1(x)+h_1(x)$. Ideally, however, we can do this iteratively and have a model refined $k+1$ times: $f_{k+1}(x)=f_k(x)+h_k(x)$.

The gradient part is basically just because residuals are the same as negative gradients for a regression problem with quadratic loss functions.

Alternatives to quadratic loss: absolute value loss, Huber loss.

We can deal with overfitting implementing the shrinkage regularization technique. We introduce a gate variable to control the impact of the update at each iteration of the Gradient Boosting:

$f_m(x)=f_{m-1}(x)+\nu·\sum^J_{j=i}\gamma_{jm}I(x \in R_{jm})$.

(Here the model fitted on residuals is a regression tree, hence a different value $\gamma_{jm}$ is fitted for each $x_{jm}$ in $J$ intervals.)