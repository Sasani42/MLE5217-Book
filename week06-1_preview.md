---
title: "What to expect this week"
---

# Week 6 — What to expect 🤔


This week we are going to talk about 2 related things:
1. Bias Vs Variance 
2. Cross-validation 

**Bias Vs Variance**

Imagine you're trying to predict how strong a new alloy will be, just from its composition.

One approach: a dead-simple rule - "more carbon = stronger, always." It's easy to state, but it ignores everything else going on (grain structure, heat treatment, you name it), so it's consistently a bit *off*, in the same direction, no matter what data you feed it. That's high **bias** - the model is too simple to capture what's really happening.

The opposite approach: a rule so complicated it perfectly matches every single alloy sample you've ever tested, quirks and noise included. It looks incredible on your existing data - and then falls apart the moment you test a new batch. That's high **variance** - the model is so sensitive to the exact data it saw that it can't generalise.

You don't want either of these in your model, but you can't kill both at once. Push bias down and variance tends to creep up, and vice versa. Week 6 is about learning to find that sweet spot where you balance between the two. 🎯

**Cross-validation**

So how do you know if a model has actually found that sweet spot, without waiting for it to fail in the real world?

Cross-validation is basically taste-testing your recipe before serving it to guests. Rather than cooking one dish and serving it straight to everyone hoping for the best, you hold back a few spoonfuls, taste-test yourself, adjust, and repeat - ideally across a few different "tasters," so you're confident it wasn't just one lucky batch.

In materials terms: instead of trusting a model just because it nailed the samples it was trained on, you rotate through different subsets of your data, test it on samples it's never seen, and check whether it still holds up. If it keeps performing well across all those held-out tests, you can trust it a lot more.

:::{admonition} 📢 Words to listen for
:class: note
- **Bias** - error from a model being *too simple* to capture the real pattern.
- **Variance** - how much the model's predictions *wobble* if you change the data.
- **Underfitting** - the model is too rigid; it misses the trend. (High bias.)
- **Overfitting** - the model memorises the noise; it won't generalise. (High variance.)
- **Generalisation** - how well a model does on data it has *never seen*.
- **Trade-off** - you can't minimise bias and variance at the same time; you balance them.
- **Residual** - the leftover: actual value minus predicted value.
- **MAE / RMSE / $R^2$** - numbers that score how good a fit is.
- **Hyperparameter** - a knob *you* set before training (not learned from data).
  
- **Hold-out set** - a chunk of data we keep aside and never train on.
- **Split** - one particular way of cutting the data into "train" and "test".
- **Fold** - one equal slice of the data in cross-validation.
- **K-fold cross-validation** - repeating the train/test game K times, so every point gets a turn as the test set.
- **LOOCV** - "leave-one-out": the extreme where each fold is a single sample.
- **Generalization error** - how wrong the model is on *new, unseen* data. This is what we truly care about.
- **CV score** - the average error (or accuracy) across all the folds.
- **Spread / standard deviation** - how much the folds disagree with each other.
- **p-hacking** - trying lots of things and reporting only the lucky-looking one.
- **Researcher degrees of freedom** - all the little choices we make that quietly let us fool ourselves.
:::


**🐍 Python**

We will be using the the following functions 

from the sklearn.model_selection package we will use [cross_val_score](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.cross_val_score.html)
and [KFold](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.KFold.html)

Whenever we have to run a complex series of operations, such as in KFold cross-validation with standardization, we will use something called a [Pipeline](https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html) from the sklearn.pipeline package

As an example model we will also use [LogisticRegression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html) from sklearn.linear model 

Funnily enough, although it is called 'Regression', logistic regression is actually a classification algorithm.



:::{admonition} By the end of this lesson you should be able to
:class: tip
- Explain **bias** and **variance** in plain words (and with darts 🎯).
- Recognise **underfitting** and **overfitting** by looking at a plot.
- Understand *why* you can't drive both to zero - the **trade-off**.
- Read the metrics that reveal the problem: **MAE**, **RMSE**, $R^2$, and **residual plots**.
- See how the same idea shows up in regression, clustering, and every model with **hyperparameters**.
- explain, in plain words, why a single train/test split can fool you;
- describe **K-fold cross-validation** and read a CV score with its spread;
- use CV to choose model complexity (the sweet spot from last week);
- explain why reporting CV scores honestly protects science from **p-hacking**.

:::