# CMA-ES-Algorithm-for-PEMFC-Optimization

This repository contains the implementation of the Covariance Matrix Adaptation Evolution Strategy (CMA-ES) algorithm to optimize the seven parameters for the Proton Exchange Membrane Fuel Cell (PEMFC) problem as described in the [Chakraborty et al. paper in Energy(2012)](https://www.sciencedirect.com/science/article/abs/pii/S0360544212000448).

##
The objective of this project is to implement the CMA-ES algorithm to optimize seven parameters of the PEMFC model. The optimization aims to minimize the total loss in the fuel cell, thereby improving its efficiency. The parameters to be optimized include:
- x1, x2, x3, x4, l, RC, B

The project involves running the algorithm for 30 independent runs and summarizing the results in terms of the mean and variance of the optimized parameters.

### CMA-ES Algorithm

CMA-ES is an evolutionary algorithm for difficult non-linear non-convex optimization problems in the continuous domain. The algorithm adapts the covariance matrix of the Gaussian search distribution.

### Fitness Function

The fitness function calculates the total loss in the PEMFC based on the provided parameters and constants. The total loss is composed of activation loss, concentration loss, and ohmic loss.

## Summary of Results

The results are tabulated as follows:

| Parameter | Upper Bound | Lower Bound | Mean        | Std         | Variance    |
|-----------|-------------|-------------|-------------|-------------|-------------|
| x1        | -0.8532     | -1.19969    | -1.94402    | 0.00900848  | 8.11526e-05 |
| x2        | 0.005       | 0.001       | 0.00805079  | 0.00013131  | 1.72424e-08 |
| x3        | 9.8e-5      | 3.0e-5      | 0.000138878 | 1.11358e-05 | 1.24007e-10 |
| x4        | -9.54e-5    | -0.000198   | -0.000264333| 2.0857e-05  | 4.35016e-10 |
| l         | 24          | 14          | 39.008      | 7.10543e-15 | 5.04871e-29 |
| RC        | 0.0008      | 0.0001      | 0.000755376 | 0.000129441 | 1.67549e-08 |
| B         | 0.5         | 0.016       | 0.428602    | 0.104742    | 0.0109709   |

Additionally, the average best fitness across the 30 runs is:

Average Best Fitness across 30 runs: 0.0024654182223250915

### Key Insights

1. **Parameter Means and Variances:**
   - **x1**: The mean value is -1.94402 with a standard deviation of 0.00900848, indicating that this parameter is fairly stable across the runs, with low variance (8.11526e-05).
   - **x2**: The mean value is 0.00805079 with a very low standard deviation of 0.00013131, suggesting that the optimization converges to a similar value across different runs, with very low variance (1.72424e-08).
   - **x3**: The mean value is 0.000138878 with a low standard deviation of 1.11358e-05, also indicating stability and low variance (1.24007e-10).
   - **x4**: The mean value is -0.000264333 with a very low standard deviation of 2.0857e-05, showing stability and low variance (4.35016e-10).
   - **l**: The mean value is 39.008 with an extremely low standard deviation (7.10543e-15), indicating that this parameter is highly stable and consistent across runs, with almost zero variance (5.04871e-29).
   - **RC**: The mean value is 0.000755376 with a standard deviation of 0.000129441, indicating moderate stability and variance (1.67549e-08).
   - **B**: The mean value is 0.428602 with a higher standard deviation of 0.104742, suggesting more variability in this parameter compared to others, with higher variance (0.0109709).

2. **Parameter Stability:**
   - Parameters like **l**, **x2**, **x3**, and **x4** show very low variance and standard deviation, indicating that these parameters are highly stable and the optimization converges consistently to similar values.
   - **B** has the highest standard deviation and variance among the parameters, indicating more variability and less consistency in the optimization results for this parameter.

3. **Bound Constraints:**
   - The parameters are optimized within their specified bounds. The mean values lie within the given upper and lower bounds, showing that the optimization respects the constraints.

4. **Fitness Convergence:**
   - Although the summary table does not directly show the fitness values, the provided code snippet suggests tracking the best fitness across generations. If the average best fitness across the 30 runs (mentioned as `<average_best_fitness>`) is significantly improved compared to the initial generations, it indicates successful optimization.

### Important Observations

- The extremely low standard deviation and variance for **l** indicate that this parameter may have a significant impact on the model, and the algorithm converges strongly to an optimal value for it.
- The higher variability in **B** suggests that either this parameter has less influence on the optimization result, or the fitness landscape for **B** is more complex, leading to less consistent convergence.
- The low variances for other parameters indicate that the CMA-ES algorithm is effective in finding consistent solutions for these parameters across multiple runs.

### Practical Implications

- The stability in the parameters **x2**, **x3**, **x4**, and **l** suggests that these parameters are reliably optimized, and future work can focus on fine-tuning these values for improved model performance.
- The variability in **B** could warrant further investigation to understand its role in the model and explore if additional constraints or different initialization strategies could lead to more consistent optimization.
- The insights from these results can be used to improve the PEMFC model, potentially leading to better efficiency and performance of the fuel cell.


## Code Implementation
[Implement the code here](CMA_ES_Algorithm.ipynb)
