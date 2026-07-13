# Homework: Regression on Materials Data

## Overview

In this homework you'll fit two regression models to materials datasets using Python - one straight line and one curve. The goal isn't just to get a good fit; it's to build the habit of asking **"is this model actually appropriate for this data?"** Both problems are designed to reward that kind of skepticism.

Work through the guided notebook [materials_regression_homework](./week03-7_HW_regression_template.ipynb), completing every **✏️ TODO** cell and answering every **🤔 Reflection** prompt in your own words.

You can simply download this file and upload it into your MLE5217 folder.
The [dataset 1](data/week03-HW_tensile_test.csv) and [dataset 2](data/week03-HW_thermal_expansion.csv)  are required for the problem and can also be downloaded and saved into the same folder as "tensile_test.csv" and "thermal_expansion.csv" respectively.

## Learning objectives

By the end, you should be able to:

- Fit a simple linear regression with `scikit-learn` and a polynomial regression with `numpy.polyfit`, and read off slope, intercept, and R².
- Use a **residual plot** to judge whether a model form is appropriate - not just R².
- Explain what a fitted slope *means physically* (Young's modulus; coefficient of thermal expansion).
- Recognise the **domain of validity** of a linear model, and why extrapolating beyond your data - especially with high-degree polynomials - is risky.

---

## Problem 1 — Young's modulus from a tensile test (linear)

When a metal specimen is pulled in tension, it stretches. In the *elastic* region the stress $\sigma$ and strain $\varepsilon$ obey Hooke's law, $\sigma = E\varepsilon$, a straight line whose slope $E$ is the material's **Young's modulus**. Past the yield point the metal deforms plastically and the relationship is no longer a straight line.

**Data:** `tensile_test.csv` - columns `strain` (dimensionless) and `stress_mpa` (MPa).

**What you'll do:**
1. Plot the data and fit a straight line to the *whole* dataset.
2. Inspect the residuals - and discover that a single line doesn't tell the whole story.
3. Restrict the fit to the elastic region, recover $E$, and identify the material by comparing with reference values.
4. Reflect on where the linear model is valid, and what would go wrong if you extrapolated it.

**The thinking point:** a model can have a respectable R² and still be the *wrong shape* for the data. Your residual plot is what reveals this.

---

## Problem 2 — Thermal expansion (polynomial)

Heat a metal and it expands. Over a narrow temperature range, thermal strain grows almost linearly with temperature - but over a wide range the curve bends upward, because the coefficient of thermal expansion itself increases with temperature. Engineering references commonly describe this behaviour with a low-order **polynomial** in temperature.

**Data:** `thermal_expansion.csv` - columns `temperature_c` (°C) and `thermal_strain_ppm` (microstrain, relative to 20 °C).

**What you'll do:**
1. Fit a degree-1 line and examine its residuals.
2. Fit degree-2 and degree-3 polynomials and compare.
3. Push the degree very high, extrapolate past the data, and watch the model misbehave.
4. Decide on a sensible degree and justify it.

**The thinking point:** more flexibility isn't automatically better. The best model is the simplest one that captures the real trend - and high-degree fits become wildly unreliable the moment you step outside your data.

---

## This is a self-learning exercise & You are not required to submit or send in your completed work.
** I will upload a worked-out solution for guidance later on, which you can use for comparison. **




## A note on the data

Both datasets are **synthetic** - generated from physically realistic models with added measurement-like scatter, so they behave like real tensile and dilatometry measurements without being any specific real specimen. The physics they're built on is genuine: Hooke's law and Young's modulus for the elastic region, and the temperature-dependent expansion of metals for Problem 2.
