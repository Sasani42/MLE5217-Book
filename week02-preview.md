---
title: "What to expect this week"
---

# Week 2 — What to expect 🤔

Next lecture is about **describing data**

Before we ever train a model, we need to describe and understand the data that we have. This lecture covers the
summary numbers - *mean, median, mode, variance, standard deviation* - the
shape of data through *distributions*, and how we gain an understanding of data through sampling.


**💡 You will meet these ideas:**

- *Descriptive and Inferential Statistics*
- *Mean, median, mode* - three ways to say “a typical value”.
- *Variance* and *standard deviation* - how spread out the values are.
-  As the amount of data increases, how discrete data start looking like a continuous distribution *(the central   limit theorem)*
- *Distributions*, how is our data distributed - and why we like to focus on the **normal** (“bell”) shape.
- *Sampling* - how the data we have relates to the data we don't.


**👂Words to listen for** (we will use these again in later weeks, so they
should start to feel familiar):

- **line of best fit** - first glimpse this week, hidden inside the normal
  distribution formula; we formalise it in Week 3.
- **mean squared error (MSE)** - also a first glimpse this week (the squared
  term $(x - \mu)^2$ in the bell curve); becomes the workhorse of regression
  in Week 3.
- **standard error** - how much the sample mean would jiggle if we redid
  the experiment; introduced this week alongside the CLT, then used whenever
  we need to say how confident we are in a number.
- **correlation** - the degree of agreement between two variables; from Week 3
  onwards.


**🐍 Python**

We won't be diving into heavy coding this week, but there will be some example codes 
using statistics, which will use some *numpy* functions.


:::{note}
There is no maths to prepare. Just skim this page so the words aren't brand new
when you hear them in class.
:::

:::{admonition} By the end of this lesson you should be able to
:class: tip
- explain mean, median and mode in plain words,
- say what variance and standard deviation tells you about a dataset,
- explain why one extreme value affects the mean more than the median.
- gain an intuitive feeling for distributions & the central limit theorem
- explain different sampling methods
:::