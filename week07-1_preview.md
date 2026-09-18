---
title: "What to expect this week"
---

# Week 7 — What to expect 🤔

In the regression chapter we found the "line of best fit." It worked well.
But a best fit on your training data is not always a best fit on *new* (unseen) data.

This chapter is the story of that problem, and three clever fixes for it:
**Ridge**, **Lasso**, and **Elastic Net**.

👋 It is best if you could revise (even better to run the codes) the [home-work exercise in week 05](week05-5_CBFV_problem_solutions).
We will be using the same dataset this week.


:::{admonition} 📢 Words to listen for
:class: note
- **Coefficient** — the number in front of a feature. It says how much that feature pushes the answer.
- **Overfitting** — when a model learns the training data *too* well, including its noise.
- **Generalization** — how well a model does on data it has never seen.
- **Penalty** — an extra cost we add on purpose, to keep coefficients small.
- **Regularization** — the general name for "adding a penalty to keep the model simple."
- **Multicollinearity** — when two or more features carry almost the same information.
- **Shrinkage** — pulling coefficients *toward* zero.
- **Feature selection** — dropping features the model does not need.
- **λ (lambda) / alpha** — how *strong* the penalty is.
- **α (alpha, mixing) / l1_ratio** — the *blend* between Ridge and Lasso.
- **Cross-validation** — a fair way to try different settings and pick the best.
:::


**🐍 Python**

We will be using the the following functions 

[Ridge Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html)

[Lasso Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html)

[ElasticNet](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNet.html)

Cross-validation enabled models

[RidgeCV](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.RidgeCV.html)

[LassoCV](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LassoCV.html)

[ElasticNetCV](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNetCV.html)



:::{admonition} By the end of this lesson you should be able to
:class: tip
- Explain why regularization is needed
- Describe the mathematical difference between Ridge (L2) and Lasso (L1) penalties
- Interpret the geometric intuition behind L1 vs. L2 penalties
- Explain the role of the regularization strength (λ / alpha)
- Connect regularization to feature scaling and cross-validation
- Describe what ElasticNet adds
- Implement and compare the three models in scikit-learn

:::