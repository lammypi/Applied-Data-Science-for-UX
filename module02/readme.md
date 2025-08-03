# Do Some Basic Stats

I want to open this module with a simple statement: Statistics aren't scary.

It's a specific way of thinking meant to help a researcher evaluate their observations. There are two schools of statistical thinking, Bayesian and Frequentist, that I provide some introductory detail on in [Statistical Thinking](/module02/statistical_thinking.ipynb). I'll sum it up here by saying: UX will use the Frequentist approach almost exclusively.

For now, let's focus on the distinction of non-Parametric vs. parametric statistics as this will back us into some important explanations. You'll notice the presence of the word 'parameter' in these labels. So first, what is a _parameter_? A parameter is a metric that describes a feature of a variable's distribution. Distributions are a collection of observations.

There are 3 key parameters:
1. __Measures of central tendency__- describes the typical value of a distribution
   - Mean ($\mu$)- average of all values in a data set. 
   - Median- when data is arranged in order, this is the true middle value.
   - Mode- most frequently occurring value.
3. __Measures of dispersion__- describes the spread of observations in a distribution.
   - Range- the spread of values starting with the minimum observed value thru the maximum observed value.
   - Variance ($\sigma^{2}$)- how far each value is from the mean.
   - Standard Deviation ($\sigma$)- square root of the variance.
5. __Measures of shape__- describes the shape of a distribution.
   - skew ($\hat{\mu}^{3}$)- what is the symmetry of a distribution?
   - kurtosis ($\kappa$)- where do the bulk of the observations lie within a distribution.

Parameters refer to an entire population of values, or the _population distribution_. This is often impossible for a researcher to get their hands on, so they estimate parameters via _sample statistics_. A sample statistic is an estimate of a population value. When using sample statistics and not population parameters, there are some changes in notation you will see:
- Mean, $\mu$ --> Sample Mean, $\bar{X}$
- Variance, $\sigma^{2}$ --> Sample Variance, $s^{2}$
- Standard Deviation, $\sigma$ --> Sample Standard Deviation, $s$

So, non-parametric statistical methods do not rely on parameters of population distributions (or estimates thereof) to test hypotheses. Parametric statistical methods do rely on parameters (or estimates) to test hypotheses. When I say "rely on," what I really mean is, they use the parameters of a distribution as assumptions for employing a method. You can think of assumptions as standards that have to be met for using a method. Assumptions will be discussed in more detail in the non-parametric and parametric methods sections of this module.

| Non-Parametric Methods | Parametric Methods |
|------------------------|--------------------|
| Chi-Square Tests | (No directly matching method) |
| Mann Whitney U Test | Independent Samples t Test |
| Wilcoxon Signed-Rank Test | Dependent Samples t Test |
| Kruskal Wallis Test | One-way ANOVA |
| Friedman's Test | Repeated Measures ANOVA |

Aside from the main methods called out above, there are diagnostic tests you can do to determine whether you should proceed down a non-parametric or parametric path. Those will be covered in their own section that is currently being written (03-Aug-2025).



