---
title: "What to expect this week"
---

# Week 4 — What to expect 🤔



This week we are going to talk about 2 things:
1. Data Cleaning 🧹
2. Clustering 🫧

**Data Cleaning**

Raw data that we gather - from experiments, databases or any other sources might not be ready to go into a machine learning model straightaway. 
We have to first see what our data looks like, then identify if there are any hidden problems within the dataset and then 'clean' it up so that only the best data is used for the model. 


:::{dropdown} 📢 Words to listen for
**The data itself**
- **Raw data** - the data as you first received it, before any cleaning.
- **Row / sample / observation** - one material or one measurement.
- **Column / feature / variable** - one property that was measured.
- **Data type (dtype)** - what kind of value a column holds: a number (`int`, `float`) or text (`object`, `str`).

**Missing values**
- **Missing value** - an empty cell; a value that is not there.
- **NaN** - "Not a Number"; how Python marks a missing value.
- **Null / N/A / '-'** - text markers that *look* missing to us, but Python does not recognise them.
- **Drop** - to remove a row or column.
- **Impute** - to fill in a missing value with a sensible estimate.
- **Placeholder** - a stand-in value (like 0 or -999) used to mean "missing". It can be dangerous if you forget it is there.

**Wrong values**
- **Incorrect data** - a value that is present but cannot be right (e.g. a negative temperature in Kelvin).
- **Outlier** - a value that sits far away from all the others.
- **IQR (interquartile range)** - the spread of the middle 50% of the data; used as a simple rule to flag outliers.
- **Duplicate** - an identical, repeated row.
- **Domain knowledge** - what you know as a materials scientist; your best tool for spotting wrong values.

**Doing the cleaning**
- **Coerce** - to force a conversion (e.g. turn text into numbers, marking failures as `NaN`).
- **Sanity check** - a quick look to confirm the numbers are believable.
- **Data leakage** - when information from the test set sneaks into training; avoid it by computing fill values from the training data only.
- **GIGO ("garbage in, garbage out")** - bad input data gives a bad model, no matter how good the model is.
:::



**Clustering**

Picture a scatter plot where the points are not spread out evenly, but fall into distinct groups - much like stars gather into galaxies, with empty space in between.
Points land close together because their measured features have similar values. Points in different groups have features that are more different.
Clustering is the machine-learning task of finding those groups automatically, and assigning every point to one.


:::{dropdown} 📢 Words to listen for
**The setting**
- **Unsupervised learning** - learning from data that has *no* labels.
- **Label** - the answer attached to a data point. In clustering, we do not have these.
- **Cluster** - a group of points that are similar to one another.
- **Feature space** - the "map" the data lives on, with one axis per feature.
- **Euclidean distance** - ordinary straight-line distance between two points.

**How k-means works**
- **k** - the number of clusters we ask for. We must choose it.
- **Centroid / cluster centre** - the *mean* position of a cluster's points. Usually not a real data point.
- **Seed / initialisation** - the starting centres the algorithm begins from.
- **Assignment step** - each point joins its nearest centre.
- **Update step** - each centre moves to the mean of its points.
- **Iteration** - one full round of assign + update.
- **Convergence** - the point where the assignments stop changing, so the algorithm stops.

**Judging and improving the result**
- **Inertia (WCSS)** - the total squared distance from points to their own centre. Smaller means tighter clusters.
- **Local optimum** - a good-but-not-best answer that depends on where the algorithm started.
- **k-means++** - a smarter way to pick starting centres that spreads them out.
- **Restarts (`n_init`)** - running the whole algorithm several times and keeping the best result.
- **Elbow method** - plot inertia against k and look for the bend.
- **Silhouette score** - a score from −1 to +1 for how well a point fits its cluster.

**Preparing the data**
- **Scaling / standardisation** - putting features on a comparable range so no single feature dominates the distance.
- **StandardScaler / MinMaxScaler** - two common tools for doing that.

**Other methods you will hear**
- **DBSCAN** - finds clusters of any shape by following dense regions; can label points as **noise**.
- **Hierarchical clustering** - builds a tree of merges (a **dendrogram**).
- **Gaussian Mixture Model (GMM)** - gives each point a *probability* of belonging to each cluster (a "soft" assignment).
- **Segmentation** - splitting an image into regions, e.g. the phases in a micrograph.
:::

**🐍 Python**

We will be using the the following functions from the [pandas](https://pandas.pydata.org/docs/) library

*describe()*, *info()*, *head()*, *tail()*

*len()* - from the base package, not a pandas function

From Scikit-learn

[KMeans](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)
[StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html)
[MinMaxScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html)


## 👇Datasets for In-class Problems

I will add the datasets within the week.

Download these datasets and add it into your MLE5217 folder - where your jupyter notebooks are also stored. 
If you are not sure where this is, open Anaconda Prompt activate your mle5217 environment (conda activate mle5217) - look at the path (C:xxx/xx..) this is where your location would be.



:::{admonition} By the end of this lesson you should be able to
:class: tip
- Explore a set of data and carry out data cleaning. 
- Understand how clustering is different from regression & identify whether a given problem is a clustering task
- Use the k-means clustering algorithm on data
- Standardize data 
:::