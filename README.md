# 🥟 Pyrhoqe 🥟

Pyrhoqe <!-- `/ˈpaɪ.ɹəʊkjuːiː/`--> (pierogi with a Q) is a small Python library for calculating Shaffer’s rho ($\rho$).  Shaffer’s $\rho$ is an empirical Monte-Carlo rejective method designed to warrant claims about the $\kappa$ for a population based on the $\kappa$ of a sample. Specifically, it allows for the researcher to control for Type I errors when making claims about the fairness of coded data with relation to inter-rater reliability.

Shaffer’s $\rho$ functions much like a $p$-value in a T-test. If it is below some critical value (e.g. $\alpha = 0.05$ or $0.01$) then we can conclude that $\kappa$ for all of the coded data is above some threshold. In other words, we use $\kappa$ and $\rho$ to warrant that the coding done by the raters is *fair* to the data in the sense that bounding uncertainty takes into account the fact that our measure was only on a sample of data. If the rate of agreement of over all of the data is warranted, then the coded data by a single rater can be treated as if it were coded by both raters with a rate of agreement at—or above—the specified threshold.

Calculation of $\rho$ involves the generation of a large number of simulated and fully-coded datasets—a sizeable collection of hypothetical populations all of which have a $\kappa$ value below a set threshold—which indicates unacceptable agreement. $\kappa$ is then calculated on sample from each of those sets in the collection to determine if it is equal to, or higher than the $\kappa$ in the real sample. Thus, if less than 5% of the distribution of samples from the simulated datasets is greater than actual observed $\kappa$, then the null hypothesis is rejected and one can conclude that if the two raters had coded the rest of the data, there would be an acceptable level of agreement (i.e. $\kappa$ above the threshold).

## Prerequisites

- [Python 3.10+](https://www.python.org/downloads/)
- [NumPy](https://numpy.org/install/)
- [SciPy](https://www.scipy.org/install.html)
- [sklearn](https://scikit-learn.org/stable/install.html)

## Installation

```py
pip install https://github.com/ponte-vecchio/pyrhoqe.git
```

## See also
- [RhoR](https://rhor.qe-libs.org): R library that transpired this Python implemention.

- [rENA](https://rdrr.io/cran/rENA/): R library for Epistemic Network Analysis (ENA), the full suite.

- [EpistemicNetworkAnalysis.jl](https://github.com/snotskie/EpistemicNetworkAnalysis.jl): Julia implementation of ENA.

- Shaffer, D.W.: Quantitative ethnography. Cathcart Press, Madison, WI (2017).