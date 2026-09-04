---
title: "What to expect this week"
---

# Week 5 — What to expect 🤔

**Featurization**

The big idea

Models can't read chemistry. They can only read numbers.

In other words, if your dataset has chemical formulas $TiO_2, GaAs, \dots$ - the model (computer) only sees them as a 'sample name' - the chemistry they carry is not understood.

Featurization is how we turn a material into a list of numbers a model can compute with - without losing the chemistry that made the material interesting in the first place.

So, featurization is a *translation*.

That's the whole lesson, really. Everything else is just "how."

:::{admonition} 📢 Words to listen for
:class: note

The following terms will come up frequently in the next few lectures. You don't need to memorise them now - just be aware that they exist:

| Term | Meaning |
|---|---|
| **Feature / descriptor** | A single number describing some aspect of a material |
| **Feature vector** | The ordered list of all features for one material - one row of your data table |
| **Featurization** | The process of producing that vector |
| **CBFV** | Composition-Based Feature Vector - features derived from the formula alone |
| **Fractional composition** | Element amounts normalized to sum to 1 |
| **One-hot encoding** | Presence/absence encoding with one slot per category; carries identity, no similarity |
| **Embedding** | A vector representation *learned* from data rather than hand-specified |
| **Polymorph** | Same composition, different crystal structure (diamond / graphite) |
:::


**🐍 Python**

We will be using the [CBFV package](https://github.com/Kaaiian/CBFV) for exercises, 

To use this, you will need to 
- Open Anaconda Prompt
- *Conda activate mle5217*
- *pip install CBFV*

Once the installation is complete, you can
- *start jupyter notebook*

When we are using the CBFV package we will import it to our notebook as
*from CBFV import composition*


Additionally, there are other featurizers such as [Automatminer](https://hackingmaterials.lbl.gov/automatminer/) which is good to know - but we will not be using it during our class. 


:::{note}


:::


:::{admonition} By the end of this lesson you should be able to
:class: tip
- Explain what 'featurization' is in the context of materials ML
- Apply featurization on materials dataset during data pre-processing
- Decide which featurization techniques work better for a given ML problem  
:::