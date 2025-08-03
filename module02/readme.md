# Do Some Basic Stats

I want to open this module with a simple statement: Statistics aren't scary.

It's a specific way of thinking meant to help a researcher evaluate their observations. There are two schools of statistical thinking, Bayesian and Frequentist, that I provide some introductory detail on in (Statistical Thinking)[module02/statistical_thinking.ipynb]. I'll sum it up here by saying: UX will use the Frequentist approach almost exclusively.

For now, let's focus on the distinction of Non-Parametric vs. Parametric statistics. You'll notice the presence of the word 'parameter' in these labels. So first, what is a _parameter_? A parameter is a metric that describes a feature of a variable's distribution. There are 3 key parameters:
1. __Measures of central tendency__- describes the typical value of a distribution
   - Mean ($\mu$)- average of all values in a data set. 
   - Median- when data is arranged in order, this is the true middle value.
   - Mode- most frequently occurring value.
3. __Measures of dispersion__- describes the spread of observations in a distribution.
   - Range- the spread of values starting with the minimum observed value thru the maximum observed value.
   - Variance ($\sigma^{2}$)- how far each value is from the mean.
   - Standard Deviation ($\sigma$)- square root of the variance.
5. __Measures of shape__- describes the shape of a distribution.
   - skew- what is the symmetry of a distribution?
   - kurtosis- where do the bulk of the observations lie within a distribution.

Parameters refer to an entire population of values. This is often impossible for a researcher to get their hands on, so they estimate parameters via _sample statistics_. As part of this, there is a change in notation as follows:
- Mean, $\mu$ --> Sample Mean, $\bar{X}$
- Variance, $\sigma^{2}$ --> Sample Variance, $s^{2}$
- Standard Deviation, $\sigma$ --> Sample Standard Deviation, $s$



