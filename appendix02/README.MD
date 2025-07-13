# Bridging Python to R

If you've been through my section on correlations, you've likely come across at least one instance of me bridging from Python to R. This is the act of pulling R into a Python environment and using R objects and R libraries. I commonly use bridging for certain types of correlations (polychoric) and statistical tests (ART ANOVA and its post hoc tests). Now, I don't expect bridging will be a common activity for most people reading this, but all the same it's worth understanding how to do it. 

In general, the steps of bridging include:
1. Installing (if necessary) a bridging package, like [rpy2](https://rpy2.github.io/doc/v3.6.x/html/index.html), and importing it.
2. Install and then import R packages for use.
3. Create data structures and pass them back and forth as needed.
4. Perform analyses not easily performed in Python.

As you can see, it really is __using Python and R seamlessly in the same workflow__.

Since my preferred tool for this is rpy2, I want to walk through some of the basics of setting up for bridging with it. If you're working primarily in Python, you may find that you don't have R installed. If that's the case, go here: [R Project for Statistical Computing](https://www.r-project.org/). You'll have to choose a download mirror, but it's very easy to find everything you need on the site.

If you have both Python and R installed, move onto the easiest part of it all: Installation.

```
# Installation via pip
pip install rpy2

# Installation via conda
conda install conda-forge::rpy2
```
If you run into problems during your installation, confirm the following:
- Your Python version is 3.7 or higher.
- Your R version is 4.0 or higher.

Next you can import the most basic modules. See the comments embedded within the code snippets for explanations of their purpose.
```
# Supporting Python imports
import pandas as pd #This is for importing data and creating Python dataframes and Series
import numpy as np #This is for dealing with arrays and performing basic functions with them. Analogous to vectors and matrices.

# rpy2 Imports
import rpy2 #Your base import
import rpy2.robjects as ro #objects submodule. You need this to declare R objects in your workflow.
from rpy2.robjects.packages import importr, isinstalled
from rpy2.robjects import pandas2ri
```






