The section Opt_part1 include solutions with numerical methods to problems which will be valuable for the Opt_part2.
## Univariate Problems
**a)** When are gradient-free methods better? Why?
1. Optimization of black-box functions: When the objective function is a black-box, meaning that it is a function with unknown mathematical structure, gradient-free methods can be more appropriate. For instance, in evolutionary algorithms or swarm intelligence methods, the objective function is evaluated using a fitness function, which is not necessarily differentiable.

2. Discontinuous functions: When the objective function is discontinuous, gradient-based methods may not be applicable. For example, the Rosenbrock function is a continuous but non-differentiable function that has been used as a benchmark in optimization. In this case, gradient-free methods such as the Nelder-Mead method or the simulated annealing method can be used to find the global minimum.

3. High-dimensional optimization problems: As the number of dimensions of the optimization problem increases, gradient-based methods may become less efficient due to the computational cost of computing gradients in high-dimensional spaces. Gradient-free methods such as particle swarm optimization or genetic algorithms can be more efficient in such cases.

4. Noisy functions: In some cases, the objective function may be affected by stochastic noise, making gradient-based methods less effective. Gradient-free methods such as the Bayesian optimization or the covariance matrix adaptation evolutionary strategy (CMA-ES) can be used to optimize noisy functions.

5. Optimization with constraints: In optimization problems with constraints, gradient-free methods can be more suitable than gradient-based methods because they do not require the computation of gradients of the constraint functions. For instance, in constrained optimization problems such as in engineering design or finance, genetic algorithms or pattern search methods are often used.
**b)** Which of these cases can reliably be solved with gradient-based methods, which ones with gradient-free methods?
combination = ['aaa', 'abc', 'bbc', 'cbc']
We need to consider the differentiability of the profit function with respect to price p. If the function is differentiable, gradient-based methods can be used to find the maximum or minimum.
After plotting for the cases 'aaa', 'abc', and 'bbc', the profit function is differentiable with respect to p, and therefore gradient-based methods can be used to find the maximum or minimum. However, for the case 'cbc', the profit function is not differentiable at p=0, and therefore gradient-free methods may be more appropriate.

**c)** The objective is to maximize the profit by finding the optimal price.  
->**1) the Bisection method with initial range [0.1, 20]**
-> **2) Newton’s method with starting point x0 = 1**  
-> **3) Nelder-Mead with starting point x0=1.**  

**Are all methods able to find the maximum?** <br>  

The Bisection, Newton and Nelder-Mead methods are not specifically designed to
find the maximum of a function, but in general to find the root or minimum of a
function. However, they can be adapted to find the maximum by minimising the
negative of the function, depending of the specifications and characteristics of the
problem and functions

**What are potential shortcomings?**<br>
Bisection method: requires a function that is continuous and changes sign over the interval, which may not be the case. It can be considered a slow method for finding
the root or minimum.<br>
<br>
Newton's method: Requires a function to be differentiable. May converge slowly or
not at all if the initial guess is not close enough to the root or minimum.<br>
<br>
Nelder-Mead method: Heuristic method, does not make use of derivatives, which can
be an advantage in some cases. Although it can converge slowly, i.e. get stuck in
local optima, especially in high-dimensional problems.
