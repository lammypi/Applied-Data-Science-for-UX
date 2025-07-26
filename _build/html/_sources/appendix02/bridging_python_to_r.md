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
import pandas as pd 
import numpy as np 

# rpy2 Imports
import rpy2 #Your base import
import rpy2.robjects as ro #objects submodule. You need this to declare R objects in your workflow.
from rpy2.robjects.packages import importr, isinstalled #Helps you manage your R installations
from rpy2.robjects import pandas2ri #Facilitates interoperability between R and Python for dataframes.
from rpy2.robjects.conversion import localconverter #Assists with converting Python to R.
```

Now that you have all of the basics installed for your bridging work, you can write the code to install all of the R libraries you will need. In the scenario below, imagine that you want to install two libraries: ARTool and emmeans. The comments in the code snippet below will explain what is happening.

```
# Import all of the needed R libraries
utils = importr('utils')

# Checks to see if ARTool exists in the R environment. If not, it is installed. If it exists, moves on.
if not isinstalled('ARTool'):
  utils.install_packages('ARTool')

# Checks to see if emmeans exists in the R environment. If not, it is installed, but will skip it if it exists.
if not isinstalled('emmeans'):
  utils.install_packages('emmeans')

# Specifies the name of the ARTool package in the R environment.
artool = importr('ARTool')

# Specifies the name of the emmeans package in the R environment.
emmeans_pkg = importr('emmeans')
```

More than likely you're going to be manipulating datapoints captured in a dataframe. That means that you will want to convert your Python dataframe to an R dataframe:

```
# Convert to an R dataframe 
with localconverter(ro.default_converter + pandas2ri.converter):
  r_df = ro.conversion.py2rpy(df)
```

I want to take a moment and discuss conversions briefly. Converter objects, like you see above with default_converter, bundle together conversion rules. In rpy2, conversion of pandas objects into R objects can either be done automatically, or they can be controlled within a context. If you want the conversions to proceed automatically, you would use ```activate``` with something like pandas2ri:

```
# Allows for automatic conversion
pandas2ri.activate()

# Stops the automatic conversion
pandas2ri.dectivate()
```

If you want more control over the conversions, though, you would create a context. A context is a set of specific rules you can specify for interactions between Python and R, like conversions. I recommend using a context to control your conversions between Python and R to reduce the chance of throwing errors and having to waste time on debugging them. My original example using ```with localconverter(ro.default_converter + pandas2ri.converter``` has a context. 

Something else to consider when you're using R, especially if any columns in your dataframe will act as categories, is that you will need to do one of two things:
1. Convert the relevant columns to dtype of category in Python
2. Convert them to factors after converting your Python dataframe to an R dataframe.

I'll assume that you know how to do the first option, so here is how you would convert a column in an R dataframe to a factor datatype:

```
# Convert col to factor
  ro.r(f'{r_df_name}${col} <- as.factor({r_df_name}${col})')
```

In the above line of code, you may notice ```ro.r()``. This is a bridge to the interpreter. It alerts the interpreter that the string within the parentheses should be interpreted as R code. Using it enables you to define and access R variables, functions, and expressions within your Python environment. Let me show you a more detailed example where you would access a native R function.

```
# Define a vector of float objects
my_floats = ro.r(FloatVector([1.0, 1.75, 2.5, 3.25, 4.0]))

# Take the average using R's mean function - mean(x, trim=0, na.rm=FALSE)
mean_r_func = ro.r['mean']

# Apply mean_r_func
my_mean = mean_r_func(my_floats)
```

This covers the basics of bridging Python to R with rpy2. If you want to see an introduction with custom Python functions using rpy2, you can read my article on Medium: [A Brief Introduction to rpy2](https://medium.com/womenintechnology/a-brief-introduction-to-rpy2-f1b3be04a0d9)


