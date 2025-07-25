# Language Selection

Data science can be done in a variety of languages, but the examples in this repository focus primarily on Python and R. If you're completely new to data science I recommend starting with one of these languages as they're relatively simple to learn and have many easy-to-use, well documented libraries. Also, it may turn out that if you're coming to this from a UX research background that you have experience in one or both of these languages already. In that case, this section might not be very useful for you. 


## Python vs. R   

The selection of language for your data science journey is important as it may impact your perceptions of what is and is not possible. That's not to say that you can only do certain types of work in one language versus another--there is a lot of overlap in libraries between both languages, and you can even use Python in R via [reticulate](https://rstudio.github.io/reticulate/), or R in Python via [rpy2](https://rpy2.github.io/). Rather, it's easier to do some things in Python than R and vice versa.

Here is a very high-level comparison of the two languages to aid your decision:

| Consideration | Python | R |
|---------------|--------|---|
| Open-source   | ✅     | ✅ | 
| Community support | Strong | Strong |
| Opportunities for Use | Data science | Data science |
|            | Data visualization / dashboarding | Data visualization / dashboarding|
|            | ML/AI | Statistics|
|            | Software development | Diverse report documentation|
|            | Task automation | |
|            | Web development |  |
|            | Game development | |
| Domains    | Virtually all domains within tech-backed industries | Academia, Healthcare, Finance |

Obviously this is not an exhaustive list, but hopefully it is enough to help you choose between the two languages. From my own experience, it was easier for me to learn Python than R overall. To summarize my experience with both:
- R starts out easy, but as you progress to more advanced types of analyses, the syntax sometimes becomes more difficult.
- Visualization in R is much easier than in Python. This is due in part to the 'language' of creating visualizations and tables that you find in packages like [ggplot2](https://ggplot2.tidyverse.org/) and [gt](https://gt.rstudio.com/).
- Dashboarding in R via [Shiny](https://shiny.posit.co/) can seem slow, but it is far more flexible in many ways than the popular [Streamlit](https://streamlit.io/) for Python.
  - Shiny for Python is kind of meh for me, as of writing this in May 2025.
- Python is easier to do more with. I can scrape text data, set up a website via Django, and do nearly all of my most important data analysis tasks.
  - I say almost because to do polychoric correlations, the best way in Python is to use rpy2 to access polycor.
- Python frameworks and ecosystems for machine learning seem better supported ([scikit-learn](https://scikit-learn.org/stable/), [TensorFlow](https://www.tensorflow.org/), [PyTorch](https://pytorch.org/)).

I use both Python and R, but I use Python as much as possible because it allows me to do more than just analytics work.



