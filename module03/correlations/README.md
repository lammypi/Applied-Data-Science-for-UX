# Uncovering Relationships: Correlations

This section reviews the most common correlations you may encounter in the course of an analysis.
- [Pearson's r](/module03/correlations/pearsons_r.ipynb)
- [Spearman's $ρ$ (rho)](#spearman)
- [Kendall's $\tau$ (tau)](#kendall)
- [Point Biserial](#point-biserial)
- [Polyserial](#polyserial)
- [Polychoric](#polychoric)
- [Tetrachoric](#tetrachoric)   
- [Distance](#distance)


&#x1F386; __What is a correlation?__   
Correlation is a the relationship between variables. We easily see this from breaking the word down:
- Prefix: Co-
- Base word: relation

There are multiple ways of measuring correlations, but they are almost always within the range of -1 to 1. (The exception to this rule is the Distance Correlation, which is within the range 0 to 1.) This also means they are almost all described by strength and direction. 
- Strength refers to magnitude, the numeric value of the correlation.
- Direction refers to valence, whether it is positive or negative.
  - Positive correlations mean that the correlated variables change in the same direction. So, as variable A increases, so does variable B.
  - Negative correlations mean that the correlated variables change in opposite directions. So, as variable A increases, variable B decreases.

Now, I mentioned there are multiple ways of measuring correlations. The way you measure a correlation depends on the following:
1. The level of the data making up the variables in the relationship of interest.
  - Is it: Nominal, Ordinal, Interval, or Ratio?
2. The assumptions made about the construct underlying the measurement vs. the apparent level of measurement.
  - Is the measurement ordinal while the construct itself is on a continuous scale?


&#x1F386; __Partial Correlations__   
Something else to consider about correlations, especially from a UXR perspective, is that we are rarely (if ever) looking solely at two variables. More often than not we have many variables we are considering, and so it becomes a system of correlations that we are actually concerned with understanding. In this case, when we want to focus on two variables then we need to control for the effects of the others on them. This is where the concept of a partial correlation comes in. Imagine you have the following variables:
- Predictor variables
  - Time on task
  - Number of steps
  - Participant age
  - Participant education level
- Target variable
  - SUS score

A partial correlation would describe the relationship between time on task while controlling for the effects of number of steps, participant age, and participant education level on both time on task and SUS score.

&#x1F386; __Semi-Partial Correlations__   
Semi-partial correlations only control for the effect of other variables on a predictor variable of interest, but not the target variable. So, if we go back to the previous example, the semi-partial correlation of time on task with SUS score would control for the effects of number of steps, participant age, and participant education level on time on task but not on SUS score.
