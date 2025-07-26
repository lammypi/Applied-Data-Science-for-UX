# Important Python Libraries

The most important libraries you will need when using Python for data science work fall into the following categories:
- Data handling, so you can load data sets and interact with them.
- Analysis, enabling you to extract necessary information from the data.
- Visualization, for diagnosing features and communicating findings.

There are libraries for reporting and automation, but those are more advanced and will be easier to pick up once you have more experience with Python and running analyses. Until then, below are the recommended Python libraries you should consider using as part of your workflows.

## Data Handling

Data handling is a very broad category that covers everything from loading data (CSV files, parquet files) to manipulating the data in some way (cleaning data, one hot encoding). The basic libraries for this are:
- [Pandas](https://pandas.pydata.org/)
- [Polars](https://docs.pola.rs/api/python/stable/reference/index.html)

Both of these will get the data loaded and allow you to perform basic data manipulation, like handling missing values and creating one hot encoded or dummy variables. 

One library that does both data handling and helps with analysis is [NumPy](https://numpy.org/learn/). NumPy handles arrays and scalars, but also offers functions for changing the shape of your data, all activities that are important for certain types of analyses. For example:
- ```asarray()``` converts input into an array.
- ```flatten()``` collapses an array into one dimension.
- ```hstack()``` concatenates data horizontally.
- ```reshape()``` gives an array a new shape without changing the data in it.

It bridges into the analysis domain by offering functions that perform basic mathematical and statistical operations:
- ```sum()``` sums an array of elements over a specified axis.
- ```exp()``` calculates element-wise exponentiation ($base^{exp}$) for array elements.
- ```mean()``` finds the average of elements in an array along a specified axis.

NumPy also helps find minimum and maximum values (```argmin()``` and ```argmax()```, respectively). This is all only a small preview of what NumPy offers, but it is one of the most useful libraries in Python, so I recommend getting familiar with it.


## Analysis

Data analysis is all about working with data to extract information from it in some way. There are a lot of libraries that fall into this category, and some are more useful than others depending on the type of work you wish to do. 
- [SciPy](https://docs.scipy.org/doc/scipy/tutorial/index.html#user-guide) is good for extending the functionality of NumPy, but also offers a lot of useful statistics functions in [scipy.stats](https://docs.scipy.org/doc/scipy/tutorial/stats.html).
- [statsmodels](https://www.statsmodels.org/stable/index.html) is another very complete, very statistics-focused python module. I would say this module reminds me a bit of how R approaches statistics, so if you already have some familiarity with R, then this package should be easy for you to grasp.
- [Scikit Learn](https://scikit-learn.org/stable/) offers a wide range of machine learning methods that you can apply to UX problems. It offers a formulaic way of applying data transformations and analyses, and will enable you to build flexible pipelines for your data analysis.


## Visualization

Visualization covers mainly the creation of charts and graphs, but also the creation of dashboards. For simplicity's sake, I'll break these out into separate sub-sections.

As a sidenote, if you want some insights on what visualization to use when, check out [The Python Graph Gallery](https://python-graph-gallery.com/).

__Visualization__
- [matplotlib](https://matplotlib.org/) is the foundation of Python data viz. To get the best handle on creating visualizations for your Python-based analyses, take the time to learn the very basics of matplotlib.
- [Seaborn](https://seaborn.pydata.org/) is another excellent data viz library that correctly sells itself for statistical data visualization. A lot of seaborn's visualizations are handy for exploratory data analysis.
- [Plotly](https://plotly.com/python/) is based on d3.js, and honestly it is pretty slick. That being said, it's most applicable for analyses where you need interactive visuazliations or really complex visualizations that you can't pull off with seaborn. It's worth learning once you are more comfortable with Python and data viz basics.

__Dashboarding__
- [Streamlit](https://streamlit.io/) is an easy-to-learn Python-based dashboard framework. I use it for dashboarding, and depending on your needs, it can be a useful prototyping tool for data app prototyping.
- [Dash](https://dash.plotly.com/) is a free low-code dashboarding framework. I'll be honest in that I find it very clunky, but some people really love it.
- [Shiny for Python](https://shiny.posit.co/py/) is a more advanced dashboarding tool than the others listed above. It started out in R, and learning it for R I recommend as a key task. My experience with it in Python has been more clunky, but it's still an excellent more advanced tool.

Another dashboarding tool that comes highly recommend, but that I personally have no experience with (yet), is [taipy](https://taipy.io/). So, if you're interested, also check that one out.