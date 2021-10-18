[51_befd_local_regression](51_befd_local_regression.md)

# Splines

Splines are composite functions made up of pieces of polynomials of some chosen degree $d$. Given a spline $f$ and dividing the x-axis into $n+1$ intervals $[\xi_{k},  \xi_{k+1}]$, for $k=1,...,n$, the value of $f$ will be defined by a different polynomial in each interval. It is required that $f(\xi_k) = y_k$, for any $k$. It is further required that the functions which share a knot $\xi_k$  have equal values of the derivative up to the $d-1$-th degree in those points where they are contiguous. 

We can use in practice the mathematical tool of splines to design a function to interpolate a set of data points. Given some observations $(x_i, y_i), i=1,...,n$, we can divide the x-axis into $k$ intervals, defined by $k-1$ knots. Commonly, we will chose to interpolate the points with $k-1$ polynomials of degree 3. These polynomials will be defined by $4(k-1)$ parameters (the bias and three coefficients, for each interval); the constraints regarding the value of the derivatives in the knots and the value of the functions in the knots are not enough to uniquely determine the functions which will compose the spline. Thus, two more constraints are added, namely that the second derivative of the first and last polynomials in the first and last knots is 0, determining in this way *natural cubic splines*.

## Basis functions
It can be proven that the spline can be written in a convenient polynomial form using *basis functions*. Indeed, the spline can be written as $f(x, \beta) = \sum_{j} \beta_j h_j(x), j=1,...,k+4$, where $k$ is the number of knots. This means that for a spline defined using $k$ knots we will require $k+4$ auxiliary basis functions. These are defined in the following way: the first 4 basis functions correspond to $x$ elevated to the 0-th to 3rd power. The rest of the basis functions are defined as $h_k(x)=(x-\xi_k)^3_+$, where $(x)_+ := \max(0, x)$. 

Writing splines in this convenient polynomial form allows to solve the system of equations with OLS finding the parameters $\beta$ that minimize the distance between the $y$ predicted by the spline and the observed value. Furthermore, writing the equation in matrix form, we can also define the problem for a whole set of points:
$\arg \min_{\beta} = {||y - H\beta||^2_2}$,
where $\beta$ is a vector of coefficients, $y$ is a vector of observations and $H$ is the matrix of all basis function values for each observation $x_i$.
Finally, we can define a linear estimator using the analytical solution to the OLS problem $\hat \beta = (H^T H)^{-1}H^T y$ and noticing we can further multiply by $H$ and obtain the estimates: $\hat y = H (H^T H)^{-1}H^Ty$


## Smoothing splines
We can also define another criterion to choose the parameters of a spline, introducing a penalty for the "roughness" of the spline, defined as the integral of the second derivative of the spline itself. So, to the squared difference between prediction and observation, we add also the term $\lambda \int^{+\infty}_{-\infty} {f''(t)}^2 dt$, where $\lambda$ is a positive parameter controlling the impact of the smoothness penalty (smoothing parameter). 

Importantly, a solution to the problem of minimizing this more complex constraint is provided by natural cubic splines: $f(x) = \sum^{n_0}_{j=1} \theta_j N_j(x)$, where $n_0$ is the number of knots. In this case, differently from regression splines, the number of constraints is equal to the number of knots, given the criteria used to define natural cubic splines.

So, the OLS criterion enhanced with the smoothing penalty can be rewritten considering that the function solving the condition is the natural cubic spline:
$(y-N\theta)^T(y-N\theta) + \lambda \theta^T\Omega\theta$,
where $N$ is the matrix of basis function values corresponding to all observations and $\Omega$ is the matrix containing elements $\int N_j''(t) N_k''(t) dt$. Once again, the solution of this problem can be written in a linear form as $\hat \theta = (N^T N + \lambda \Omega)^{-1} N^Ty$, providing a linear estimator also for the problem with the smoothing penalty.

The solution to the problem depends of course on the parameter $\lambda$, which can be selected using $k$-fold CV or information criteria.

[56_befd_effective_dof](56_befd_effective_dof.md)