The section Opt_part1 include solutions with numerical methods to problems which will be valuable for the Opt_part2.
## Univariate Problems
**a)** When are gradient-free methods better? Why?
1. Optimization of black-box functions: When the objective function is a black-box, meaning that it is a function with unknown mathematical structure, gradient-free methods can be more appropriate. For instance, in evolutionary algorithms or swarm intelligence methods, the objective function is evaluated using a fitness function, which is not necessarily differentiable.

2. Discontinuous functions: When the objective function is discontinuous, gradient-based methods may not be applicable. For example, the Rosenbrock function is a continuous but non-differentiable function that has been used as a benchmark in optimization. In this case, gradient-free methods such as the Nelder-Mead method or the simulated annealing method can be used to find the global minimum.

3. High-dimensional optimization problems: As the number of dimensions of the optimization problem increases, gradient-based methods may become less efficient due to the computational cost of computing gradients in high-dimensional spaces. Gradient-free methods such as particle swarm optimization or genetic algorithms can be more efficient in such cases.

4. Noisy functions: In some cases, the objective function may be affected by stochastic noise, making gradient-based methods less effective. Gradient-free methods such as the Bayesian optimization or the covariance matrix adaptation evolutionary strategy (CMA-ES) can be used to optimize noisy functions.

5. Optimization with constraints: In optimization problems with constraints, gradient-free methods can be more suitable than gradient-based methods because they do not require the computation of gradients of the constraint functions. For instance, in constrained optimization problems such as in engineering design or finance, genetic algorithms or pattern search methods are often used.
