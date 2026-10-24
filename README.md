# econ3916-lab10-causal-logic

# Correlation & Causality: Confounders, Colliders and the Limits of Controls

## Objective

The objective of this lab was to understand how causation, confounding, and selection bias can produce similar correlations, and how controlling for different variables can influence estimates of causal effects.

## Methodology

- Simulated three different scenarios involving causation, confounding, and selection bias to compare their correlations and true causal effects.
- Used NetworkX to create directed acyclic graphs (DAGs) illustrating confounders, colliders, and mediators.
- Ran OLS regressions to examine how controlling for confounders and colliders changes estimated treatment effects.
- Simulated M-bias to demonstrate how controlling for a pre-treatment variable can introduce bias.
- Created a function called `coef_on_d()` to estimate the coefficient on treatment while controlling for different variables.
- Compared experimental and observational estimates using the LaLonde job-training dataset and examined how adding covariates changed the results.

## Key Findings

The three simulated scenarios produced correlations of 0.654, 0.664, and 0.632, even though their true causal effects were 2.0, 0, and 0, respectively. This demonstrated that correlation alone cannot establish causation, even when the relationship is statistically significant.

Controlling for a confounder helped recover the true causal effect, while controlling for a collider introduced a negative relationship between two variables that were originally independent. The estimated coefficient was -0.592, even though the true effect was zero.

The M-bias simulation showed that controlling for a variable measured before treatment does not necessarily eliminate bias. Controlling for W produced a coefficient of -0.191, but adding u1 as another control brought the coefficient back to 0.006, which was close to the true effect of zero.

In the LaLonde job-training analysis, the randomized experimental benchmark was $1,794, while the naive observational estimate using the CPS comparison group was -$8,498. After controlling for observed characteristics, the estimate increased to $699, closing approximately 89% of the gap between the observational estimate and the experimental benchmark.

Overall, this lab demonstrated that adding more control variables does not always improve causal estimates. It is important to understand the causal relationships between variables before deciding which ones to control for.
