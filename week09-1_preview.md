---
title: "What to expect this week"
---

# Week 7 — What to expect 🤔

**Classification!**

So far almost all the models that we have handled deal primarily with regression problems - trying to find exact answers that correspond to a given input.
Another important type of task in machine learning is *Classification* - trying to assign each data point to a specific class or category.

Note: Classification is different from clustering.

Classification sorts data into *predefined categories* using *labeled* examples, whereas clustering groups unlabeled data based on natural similarities.

In classification we are concerned about one thing:

*Drawing the best possible line between two groups - and when drawing a simple line becomes tricky, we use some clever tricks to get around that*

:::{admonition} What the next two chapters are about
:class: tip
So far we have mostly **predicted a number**: a hardness, a formation energy, a property with error bars. This chapter does something different - it puts each sample into a **class** ("this is a metal", "this is a ceramic", "this is a defect").

**Support Vector Machines (SVM)** are a group of models which can do either regression - **Support vector regressors (SVR)** or classification - **Support Vector Classifiers (SVC)**. This does so by drawing a boundary in-between the data groups. And it doesn't just draw *a* boundary - it finds the one with the *widest safety gap*. When a straight boundary won't fit, a trick called the **kernel** comes to the rescue. Let's look through it one step at a time.
:::


:::{admonition} 📢 Words to listen for
:class: note
- **Classification** — sorting samples into groups (classes), instead of predicting a number.
- **Hyperplane** — the boundary. A line in 2-D, a plane in 3-D, a "flat sheet" in higher dimensions.
- **Margin** — the empty gap on each side of the boundary. Wider is safer.
- **Support vectors** — the few points closest to the boundary. They alone decide where it goes.
- **Maximal margin** — the boundary with the widest possible gap.
- **Soft margin** — a margin that tolerates a few mistakes to stay wide and robust.
- **Kernel** — a function that (in effect) lifts data into a higher dimension so a straight boundary can separate it.
- **Kernel trick** — doing this without ever building the high-dimensional coordinates. Cheap and clever.
- **Precision / Recall / F1** — ways to measure how good a classifier really is.
:::

**🐍 Python**

We will be using the the following functions from the pandas library

[Support Vector Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html)

And the following metrics from scikit-learn

[accuracy_score](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html)

[classification_report](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.classification_report.html)

[confusion_matrix](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.confusion_matrix.html)


And the **dataset** from the below link :

You can copy and paste the following snippet into your notebook

#------------------------------
# Load the dataset
url = 'https://archive.ics.uci.edu/ml/machine-learning-databases/glass/glass.data'

columns = ['Id', 'RI', 'Na', 'Mg', 'Al', 'Si', 'K', 'Ca', 'Ba', 'Fe', 'Type']

data = pd.read_csv(url, names=columns, index_col='Id')

#------------------------------
