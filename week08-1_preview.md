---
title: "What to expect this week"
---

# Week 8 — What to expect 🤔


<img src="images/lec08_uncertainty.png" width="400">


So far, every model we've built - linear regression, Ridge, Lasso, Elastic Net -
each returns one curve, and from that curve, it predicts one number for any new input.
You can feed in a composition, and it gives you *one* predicted value, with great confidence. 

But, it never tells you how much to trust that number.

In real materials discovery, "how confident are you?" often matters as much
as the prediction itself. 

If there are several possible candidate alloys to actually synthesize or run through DFT next - which one do you pick?
Each one is time consuming - and you'd probably want to start from a material which is likely to give you a promising result! Something that you can compare with the theoretically expected outcomes and interpret your results. Whereas there could also be  candidates that have a high degree of uncertainty associated with it. And if you picked one of those for synthesis, you might end up spending a long time trying to interpret your results.

That means you'd want a model that not only predicts the candidate materials that can be tested, but also one that says "I'm fairly sure about this one" or "I have no idea about that one, we've never tested anything like it."

This week is about a model that does exactly that (**Gaussian Process
Regression**), and a method that puts that honesty to work, deciding what to
try next so you waste as few expensive experiments as possible
(**Bayesian Optimization**).

:::{admonition} 📢 Words to listen for
:class: note
- **Gaussian Process (GP)** — instead of fitting one function, a GP represents a whole family of plausible functions that could explain your data.
- **Prior** — what the model believes about the function *before* it has seen any data.
- **Posterior** — the updated belief about the function *after* seeing data.
- **Mean function** — the model's central, "best guess" prediction at any point.
- **Kernel (covariance function)** — a rule for how similar two inputs are; it controls how smooth or wiggly the model's guesses are.
- **Length scale** — a kernel setting: how far apart two points can be before the model treats them as unrelated.
- **Uncertainty (confidence interval)** — how sure, or unsure, the model is at a given point — this is what OLS/Ridge/Lasso never gave you.
- **Surrogate model** — a cheap, fast stand-in for an expensive real experiment or simulation.
- **Acquisition function** — a rule that turns "mean + uncertainty" into a decision: where should I look next?
- **Expected Improvement (EI)** — a common acquisition function that estimates how much better the next point is likely to be.
- **Exploration vs. exploitation** — trying an uncertain region to learn more, versus trying a region you already think is good.
- **Bayesian Optimization (BO)** — using a surrogate model and an acquisition function together to find a good answer in as few expensive evaluations as possible.
- **Marginal likelihood** — the score GPR uses to tune its own settings.

:::

**🐍 Python**

We will be using the following functions

[GaussianProcessRegressor](https://scikit-learn.org/stable/modules/generated/sklearn.gaussian_process.GaussianProcessRegressor.html)
[Kernels for Gaussian Processes](https://scikit-learn.org/stable/modules/gaussian_process.html)

For Bayesian Optimization

[gp_minimize](https://scikit-optimize.github.io/stable/modules/generated/skopt.gp_minimize.html)
[Real (search space dimension)](https://scikit-optimize.github.io/stable/modules/generated/skopt.space.space.Real.html)

:::{admonition} By the end of this lesson you should be able to
:class: tip
- Explain why a single point-estimate prediction is not always enough, and why an uncertainty estimate matters
- Describe what a Gaussian Process is: a distribution over functions, defined by a mean function and a kernel
- Interpret the role of the kernel and its hyperparameters (e.g. length scale) in controlling smoothness and flexibility
- Explain how GPR produces both a prediction and an uncertainty estimate at every point
- Describe the motivation for Bayesian Optimization: using a cheap surrogate model to decide which expensive experiment or simulation to run next
- Explain the exploration–exploitation trade-off and how an acquisition function (e.g. Expected Improvement) balances it
- Implement Gaussian Process Regression and a basic Bayesian Optimization loop in Python (scikit-learn + scikit-optimize)

:::
