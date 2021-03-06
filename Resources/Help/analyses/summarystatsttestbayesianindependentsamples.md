Summary Statistics - Bayes factor from t-value
==========================

Independent Samples
==========================

This function allows you to compute Bayes factor corresponding to an independent groups t-test using the classical *t* statistic. (Null hypothesis states that the population means of two independent groups are equal) It can be used when you don't have access to full data set, but you do have the t statistic.

Assumptions
-----------
- The observations in both groups are a random sample from the population
- The dependent variable is normally distributed in both populations
- The population variances in the two groups are homogeneous

Default Options
-------
### Hypothesis:
- Group 1 &ne; Group 2: Two-sided alternative hypothesis that the population means are equal
- Group 1 &gt; Group 2: One-sided alternative hypothesis that the population mean of Group one is larger than the population mean of Group two
- Group 1 &lt; Group 2: One-sided alternative hypothesis that the population mean of Group one is smaller than the population mean of Group two 

### Bayes Factor:
- BF10: Bayes factor to quantify evidence for the alternative hypothesis relative to the null hypothesis
- BF01: Bayes factor to quantify evidence for the null hypothesis relative to the alternative hypothesis
- Log(BF10): Natural logarithm of BF10

### Prior:
- Cauchy prior width: Scale of the Cauchy prior density on effect size under the alternative hypothesis; the default is 0.707

 
Default Output
-------

### Bayes factor for Independent Samples T-Test:
- BF10 (or BF01): Bayes factor. If one-sided test is requested: 
  - BF+0: Bayes factor that quantifies evidence for the one-sided alternative hypothesis that Group one > Group two
  - BF-0: Bayes factor that quantifies evidence for the one-sided alternative hypothesis that Group one < Group two
  - BF0+: Bayes factor that quantifies evidence for the null hypothesis relative to the one-sided alternative hypothesis that Group one > Group two
  - BF0-: Bayes factor that quantifies evidence for the null hypothesis relative to the one-sided alternative hypothesis that Group one < Group two
- error %: The error of the Gaussian quadrature integration routine used for the computation of the Bayes factor.

Additional Options
-------

### Plots:
- Prior and posterior: Displays the prior and posterior density of the effect size under the alternative hypothesis
  - Additional info: Adds the Bayes factor computed with the user-defined prior; adds a pizza plot depicting the odds of the data under the null vs. alternative hypothesis; adds the median and the 95% credible interval of the posterior density of the effect size
- Bayes factor robustness check: Displays the Bayes factor as a function of the width of the Cauchy prior on effect size. The scale of the Cauchy prior is varied between 0 and 1.5 (0 - 2 if user prior width is greater than 1.5), creating progressively more uninformative priors

 
Additional Output
-------

### Plots:
- Prior and posterior: Displays the prior (dashed line) and posterior (solid line) density of the effect size under the alternative hypothesis; the gray circles represent the height of the prior and the posterior density at effect size delta = 0. The horizontal solid line represents the width of the 95% credible interval of the posterior
 - Additional info: Displays the Bayes factor computed with the user-defined prior; displays a pizza plot depicting the odds of the data under the null vs. alternative hypothesis; displays the median and 95% credible interval of the posterior density
- Bayes factor robustness check: Displays the Bayes factor as a function of the width of the Cauchy prior on effect size. The black circle represents the Bayes factor computed with a wide prior; the white circle represents the Bayes factor computed with an ultrawide prior; the gray circle represents the Bayes factor computed with the user-defined prior


References
-------
- Jeffreys, H. (1961). *Theory of probability (3rd ed.)*. Oxford, UK: Oxford University Press.
- Rouder, J. N., Speckman, P. L., Sun, D., Morey, R. D., & Iverson, G. (2009). Bayesian t-tests for accepting and rejecting the null hypothesis. *Psychonomic Bulletin & Review, 16*, 225-237.
- Morey, R. D. & Rouder, J. N. (2011). Bayes Factor Approaches for Testing Interval Null Hypotheses. *Psychological Methods, 16*, 406-419
