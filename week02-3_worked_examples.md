---
title: "Worked Examples"
kernelspec:
  name: python3
  display_name: Python 3
---

# 🛠️ Worked Examples
## 📝Describing a Set of Measurements

Imagine you take a polished metal sample, look at it under a microscope, and measure the **diameter of grains** you can see in one micrograph. You get these eight measurements (in micrometres, μm):

$$
2,\quad 4,\quad 4,\quad 4,\quad 5,\quad 5,\quad 7,\quad 9
$$

That is a *messy* list of numbers. The job of **descriptive statistics** is to summarise this list with a few simple numbers that tell us:

- where the measurements are *centred* (mean, median, mode), and
- how *spread out* they are (variance, standard deviation).

We will work through all five quantities using this **one** dataset, then use the same numbers to understand the difference between **sample** and **population** statistics.

```{tip}
Try each problem yourself first with a pen and paper. Then click **"Show solution"** to check your work.
```

---

## 1. The Mean (average)

The **mean** is what most people call the "average". You add up all the values and divide by how many there are.

$$
\bar{x} = \frac{1}{n}\sum_{i=1}^{n} x_i
$$

Here $\bar{x}$ (read *"x-bar"*) is the mean, $n$ is the number of measurements, and $x_i$ is the $i$-th measurement.

```{admonition} Problem
:class: note
Calculate the mean grain diameter for our eight measurements.
$$
2,\quad 4,\quad 4,\quad 4,\quad 5,\quad 5,\quad 7,\quad 9
$$
```

```{admonition} Show solution
:class: dropdown

There are n=8 measurements. First add them all up:

$$
2 + 4 + 4 + 4 + 5 + 5 + 7 + 9 = 40
$$

Then divide by n=8:

$$
\bar{x} = \frac{40}{8} = 5 \ \mu\text{m}
$$

**The average grain diameter is 5 μm.** Notice that *no single grain* is actually 5 μm - the mean is a summary, not necessarily a value that appears in the data.
```

---

## 2. The Median (the middle value)

The **median** is the value in the *middle* of the data once it is sorted from smallest to largest. Half the measurements are below it, half are above.

- If there is an **odd** number of values, the median is simply the middle one.
- If there is an **even** number of values, the median is the **average of the two middle values**.

```{admonition} Problem
:class: note
Find the median grain diameter.
$$
2,\quad 4,\quad 4,\quad 4,\quad 5,\quad 5,\quad 7,\quad 9
$$
```

```{admonition} Show solution
:class: dropdown

The data is already sorted:

$$
2,\ 4,\ 4,\ \underbrace{4,\ 5}_{\text{middle pair}},\ 5,\ 7,\ 9
$$

We have $n = 8$ values (an even number), so the two middle ones are the **4th** and **5th** values: $4$ and $5$.

$$
\text{median} = \frac{4 + 5}{2} = 4.5 \ \mu\text{m}
$$

**The median grain diameter is 4.5 μm.**
```

```{admonition} Why have both a mean and a median?
:class: tip
The median is **robust** to extreme values. If that single 9 μm grain had instead been a giant 90 μm grain, the **mean** would jump dramatically, but the **median** would not move at all. In materials data, one unusual outlier (a measurement error, a defect, a stray large grain) can pull the mean around - the median is often a safer "typical value".
```

---

## 3. The Mode (the most common value)

The **mode** is simply the value that appears **most often**.

```{admonition} Problem
:class: note
Find the mode of the grain diameters.
$$
2,\quad 4,\quad 4,\quad 4,\quad 5,\quad 5,\quad 7,\quad 9
$$
```

```{admonition} Show solution
:class: dropdown

Count how many times each value appears:

| Value (μm) | 2 | 4 | 5 | 7 | 9 |
|---|---|---|---|---|---|
| Count | 1 | **3** | 2 | 1 | 1 |

The value **4 μm** appears three times - more than any other.

**The mode is 4 μm.**
```

```{admonition} A few things to know about the mode
:class: tip
- A dataset can have **no mode** (if every value appears the same number of times).
- A dataset can have **two modes** (called *bimodal*) - common in materials when two distinct grain populations are present.
- The mode is the only one of these three that also works for **categories** (e.g. the most common crystal structure in a batch of samples).
```

Notice that for this dataset, the three "centre" measures are all **different**:

$$
\text{mode} = 4, \qquad \text{median} = 4.5, \qquad \text{mean} = 5
$$

This is exactly why we keep all three around - they each tell us something slightly different about where the data sits.

---

## 4. The Variance (average spread)

The mean tells us the centre, but it says nothing about whether the grains are all *similar in size* or *wildly different*. **Variance** measures spread.

The idea is simple:

1. For each measurement, find how far it is from the mean. This is the **deviation**, $(x_i - \bar{x})$.
2. **Square** each deviation (so that being above or below the mean both count as "spread", and large deviations are penalised more).
3. **Average** those squared deviations.

$$
\sigma^2 = \frac{1}{n}\sum_{i=1}^{n}(x_i - \bar{x})^2
$$

```{admonition} Problem
:class: note
Using the mean $\bar{x} = 5$ μm we found earlier, calculate the variance.
```

```{admonition} Show solution
:class: dropdown

Build a small table of deviations and squared deviations (remember $\bar{x} = 5$):

| $x_i$ | $x_i - \bar{x}$ | $(x_i - \bar{x})^2$ |
|---|---|---|
| 2 | −3 | 9 |
| 4 | −1 | 1 |
| 4 | −1 | 1 |
| 4 | −1 | 1 |
| 5 | 0 | 0 |
| 5 | 0 | 0 |
| 7 | 2 | 4 |
| 9 | 4 | 16 |
| **Sum** | 0 | **32** |

(The deviations always add up to 0 - a useful check that you used the right mean.)

Now average the squared deviations over $n = 8$:

$$
\sigma^2 = \frac{32}{8} = 4 \ \mu\text{m}^2
$$

**The variance is 4 μm².**
```

```{admonition} Why are the units squared?
:class: tip
Because we squared the deviations, the units get squared too - here, μm². "4 square-micrometres of spread" is hard to picture. That awkwardness is exactly what the next quantity fixes.
```

---

## 5. The Standard Deviation (spread, in the original units)

The **standard deviation** is just the **square root of the variance**. Taking the square root undoes the squaring, so the result is back in the *same units as the original data* - which makes it much easier to interpret.

$$
\sigma = \sqrt{\sigma^2}
$$

```{admonition} Problem
:class: note
Calculate the standard deviation of the grain diameters.
```

```{admonition} Show solution
:class: dropdown

We found the variance $\sigma^2 = 4 \ \mu\text{m}^2$. So:

$$
\sigma = \sqrt{4} = 2 \ \mu\text{m}
$$

**The standard deviation is 2 μm.**

Now this number is easy to read: the grain diameters are *typically about 2 μm away* from the average of 5 μm. A small standard deviation would mean very uniform grains; a large one would mean a wide mix of grain sizes.
```

---

## 6. Sample Statistics vs Population Statistics 🎲

Here is the key question a materials scientist should always ask:

> **Did I measure *everything* I care about, or only a *sample* of it?**

- The **population** is the *entire* collection we actually care about - for example, **every grain in the whole batch of material**, possibly millions of them.
- A **sample** is the *small subset* we actually measured - for example, the **8 grains visible in one micrograph**.

In real materials work, we almost never measure the whole population. It would take forever. Instead we measure a sample and use it to **estimate** what the population is like. This is the bridge from *descriptive* statistics (describing what we measured) to *inferential* statistics (drawing conclusions about what we did **not** measure) — and it is the same logic behind machine learning, where we learn from a limited dataset and hope to **generalise** to new, unseen data.

### The notation changes

To keep track of which is which, we use different symbols:

| Quantity | Population (true, usually unknown) | Sample (what we compute from data) |
|---|---|---|
| Mean | $\mu$ ("mu") | $\bar{x}$ ("x-bar") |
| Variance | $\sigma^2$ ("sigma-squared") | $s^2$ |
| Standard deviation | $\sigma$ ("sigma") | $s$ |

### One important difference: dividing by $n-1$

For the **mean**, the formula is the same whether you think of your data as a population or a sample - you still add up and divide by $n$.

But for the **variance and standard deviation of a sample**, we divide by $n-1$ instead of $n$:

$$
s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i - \bar{x})^2
\qquad\text{(sample variance)}
$$

```{admonition} Problem
:class: note
Treat our eight grains as a **sample** drawn from a much larger batch. Recalculate the variance and standard deviation using $n-1$.
```

```{admonition} Show solution
:class: dropdown

The sum of squared deviations is unchanged: **32** (from the table in Section 4). Only the divisor changes, from $n = 8$ to $n - 1 = 7$:

$$
s^2 = \frac{32}{7} \approx 4.57 \ \mu\text{m}^2
$$

$$
s = \sqrt{4.57} \approx 2.14 \ \mu\text{m}
$$

So the **sample** standard deviation (≈ 2.14 μm) is slightly **larger** than the **population** standard deviation (2.00 μm) we found earlier, because we divided by a smaller number.
```

```{admonition} Why divide by n − 1? (the intuition)
:class: tip
When we measure only a sample, we don't know the true population mean $\mu$ - so we use our **sample mean** $\bar{x}$ instead. But $\bar{x}$ is calculated to sit right in the *middle of our sample*, which means the measurements are, on average, a little *closer* to $\bar{x}$ than they would be to the true $\mu$.

The effect: dividing by $n$ would **slightly underestimate** the true spread. Dividing by $n-1$ nudges the estimate up just enough to correct for this. This correction is called **Bessel's correction**.

Notice it matters **more** when $n$ is small (8 vs 7 is a noticeable change) and barely matters when $n$ is large (10000 vs 9999 is almost nothing) - which makes sense, because with lots of data our sample mean is already a very good stand-in for the true mean.
```

---

## 7. Summary 📋

Everything we computed for the grain-diameter dataset $\{2, 4, 4, 4, 5, 5, 7, 9\}$:

| Quantity | Symbol | Value |
|---|---|---|
| Mean | $\bar{x}$ | 5 μm |
| Median | — | 4.5 μm |
| Mode | — | 4 μm |
| Variance (population, ÷ $n$) | $\sigma^2$ | 4 μm² |
| Standard deviation (population) | $\sigma$ | 2 μm |
| Variance (sample, ÷ $n-1$) | $s^2$ | ≈ 4.57 μm² |
| Standard deviation (sample) | $s$ | ≈ 2.14 μm |

```{admonition} The big picture for this course
:class: note
Almost all data in machine learning is a **sample** - a finite set of measurements standing in for a much larger reality we cannot fully observe. Mean and standard deviation will reappear constantly: when we **scale features** before training a model, when we **describe errors**, and when we ask whether a result is **real or just noise**. Getting comfortable with these five quantities now pays off in every lecture that follows.
```

---

## 8. Check it with Python 🐍 

You never *have* to compute these by hand again - Python's `numpy` library does it in one line each. The important thing is that you now understand what each number **means**, and that is important for making conclusions on what the data is telling you (interpretation).

```{code-cell} python3
import numpy as np

grain_diameters = np.array([2, 4, 4, 4, 5, 5, 7, 9])

print("Mean             :", np.mean(grain_diameters))
print("Median           :", np.median(grain_diameters))
print("Population var    :", np.var(grain_diameters))            # divides by n
print("Population std    :", np.std(grain_diameters))            # divides by n
print("Sample var (n-1)  :", np.var(grain_diameters, ddof=1))    # divides by n-1
print("Sample std (n-1)  :", np.std(grain_diameters, ddof=1))    # divides by n-1
```

```{admonition} Watch out for this!
:class: warning

By default, `numpy`'s `np.var()` and `np.std()` divide by $n$ (the **population** formula). To get the **sample** version that divides by $n-1$, you must pass **`ddof=1`**. This is a very common source of confusion - when in doubt, check which one your tool is using.

`numpy` has no built-in mode

For the **mode**, use `from scipy import stats` and then `stats.mode(grain_diameters)`, since `numpy` doesn't include a mode function directly.
```


