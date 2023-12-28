The section Opt_part1 include solutions with numerical methods to problems which will be valuable for the Opt_part2.
## OPT_PART1
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
- **1) the Bisection method with initial range [0.1, 20]**
- **2) Newton’s method with starting point x0 = 1**  
- **3) Nelder-Mead with starting point x0=1.**  

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

**d) For Newton and Nelder-Mead: Does the starting point make a difference? What, if x0=3 or x0=15?**
#NEWTON
Replacing in a very simple way X0, the values change in both methods, so that means the starting point can make a difference in both. In Newton's method x0 can affect the convergence rate and maybe lead to non-converging solution. Normally, starting too close to the optimal value will result in faster convergence, while starting too far away from it may result in divergent or slower convergence. For example, starting at x0=3 and x0=15 may result in converging to different optimal values or not converging at all if the initial estimates are too far from the actual optimal values.

Also in the Nelder-Meade method, the starting point can affect the speed of convergence and the quality of the solution. If the starting point is not chosen carefully, the algorithm may converge to a local optimum instead of a global optimum. In general, it is recommended to check several starting points and compare the results to find the global optimum; starting at x0=3 or x0=15 may give different optimum values depending on the function to be optimised and the shape of the optimisation.
<br>
<br>
With price 1 and 3 is the same, but with 15 them change in all the variation starting points.
It changes with 1, 3 and 15 respectively in each case.  
Also this part has:
## Linear Programming
## Linear Problems 
In this section there are solutions for:
**a) Solving the problem for 𝜇 = 0 with the linprog function from the scipy.optimize module.**
**b) Solving the problem for 𝜇 = 1 with linprog(..., method=’simplex’) and then
with linprog(..., method=’interior−point’). Compare the results.**
**c) Solve the problem for u = 0.0, 0.1, 0.2, ..., 2.0 and analyse how 𝑓 and 𝑥1, 𝑥2
change for increasing values of u.**

## OPT_PART2
This section consists on:  
### Problem 1
**a)** Using Monte Carlo search (MCS), how do the results improve when the number of function evaluations is increased from 1’000 to 2’000, 4’000, 8’000, and 16’000?
When using MCS to optimize the Ackley function, increasing the number of function evaluations will generally improve the quality of the solution found. This is because
increasing the number of evaluations provides more opportunities for the algorithm to explore the search space and discover better solutions.<br>
So, when the number of function evaluations is increased the accurate of the model is improving.
**b)**  Using Differential Evolution (DE) with function evaluations as above and “typical” settings
for the remaining hyperparameters (popSize=15, pXO=0.5, F=0.7), how to the reported
results compare to those from MCS?
**c)** For DE with 2’000 function evaluations, 𝐹 = 0.7, and a population size of 5, 10, 15, and
20, respectively: how does the cross-over probability affect the (typical) reported results?

### Problem 2
**a)** Assuming the items are not divisible and selection problem is binary, i.e., an item can be
included or not, 𝑥𝑖 ∈ {0, 1}. What is the optimal combination for 𝑁 = 10? And for 𝑁 = 20?
**b)**  Assume items are divisible and 𝑥𝑖 can be real-valued, yet within limits 0 ≤ 𝑥𝑖 ≤ 1. What are now the optimal solutions for 𝑁 = 10 and 𝑁 = 20?  
The goal is to maximize the total value of the items selected while not exceeding the budget.The budget is set at N*0.3, hence the maximum combined weight of the chosen
items cannot be greater than N*0.3.<br>
Following that, the function determines the value per weight for each item and arranges them in decreasing weight. Once the money is spent, it continues to choose goods in decreasing value per weight order. In cases where an item's cost prevents full selection, a portion of the item is chosen based on the amount of budget that is still available.<br>
The function returns the combined weight and value of the chosen items.<br>
The program executes the knapsack_fractional function for two different values of N (10 and 20) and outputs the best result for each case.

**Why?**
Choosing one of the methods depends on the problem and the constraints because in practice, the capacity of the backpack is often determined by the physical limitations of the container or vehicle that will transport the items, the capacity depending on the weight and so on. Certain problems may accept the partial inclusion of certain objects but not other problems would accept complete units, that is why in general it depends on the conditions of the problem.  
In the case of the binary knapsack problem, this is automatically satisfied since each item either has weight 0 or weight greater than 0. In the case of the fractional knapsack problem, we can include fractions of items if an item cannot be fully included to ensure that the weight constraint is satisfied.
For knapsack_binary. The list comprehension method used to get the total value and total weight for every conceivable combination of items, however, implicitly applies E{0,1}
it. By only adding the values and weights of items where xi = 1, the expression if c[i] in the list comprehension is used to filter out things that are not selected (i.e., where xi = 0).<br>
The constraint that each item can only be selected (xi = 1) or not selected (xi = 0) is the same as what is being imposed in this case. As a result, in the lines of code where the list comprehension is used to calculate the total value and total weight for each conceivable combination of items, the constraint xi 0, 1 is implicitly applied. The
constraint is applied in the expressions if c[i] used to filter out items that are not selected.
0 ≤ 𝑥𝑖 ≤ 1 is implicitly applied in the fraction calculation when a fraction of an item that fits within the budget is taken.














