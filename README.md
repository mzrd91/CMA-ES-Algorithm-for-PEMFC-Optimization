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

Average Best Fitness across 30 runs: <0.0024654182223250915>


## Code Implementation
[Implement the code here](CMA_ES_Algorithm.ipynb)
