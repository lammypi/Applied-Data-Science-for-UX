# Getting Started with Python

Important links:
- [Python](https://www.python.org/) - download the language.
- [Jupyter](https://jupyter.org/) - popular software for data science.
- [Anaconda](https://anaconda.org/) - platform containing multiple Python IDEs.
  - If you're completely new to this, Anaconda is a good way to start. Just be sure to have JupyterLab available in your Anaconda install.
- [Google Colab](https://colab.google/) - free online Jupyter Notebook service

If you're more advanced, you can use [Visual Studio Code](https://code.visualstudio.com/) to run Jupyter notebooks or operate entirely out of Python scripts (.py files).

## Creating Virtual Environments

An excellent habit to develop when working in python is to always create a new virtual environment whenever you start a new project or study. This helps you avoid the nasty surprise of incompatibilities in your base environment that can make it difficult or impossible for you to complete your work.

__Note__: If you're using Google Colab, you won't need to create a virtual environment. You can go straight to installing whatever you need via pip.

If you're using JupyterLab in Anaconda, the easiest way to do this is via [conda](https://github.com/conda/conda).

__Creating a Virtual Environment in Conda__

The code snippet below shows you how to create a new environment with a specific python version.

```
conda create -n <env-name> python=3.x
```

Let's break this down:
- 'conda create' tells conda it will be creating something
- '-n' is an argument that is short for '--name', and it indicates you will be providing a name for what you're creating.
- '\<env-name>\' is what you will name your environment. Just replace the whole argument with your environment name. 
- 'python=3.x' specifies which version of python you want to use in your new environment. Replace the 'x' with something like 10. (I usually operate in 3.10 because as of writing this guide it's the most stable release for all of the modules and frameworks I use.)

If that's successful, then you can activate your environment using the command below:
```
conda activate env-name
```

At this point you're ready to install all of the packages you need for your work. Since you've just set up a new conda environment, you should use conda to install all of your packages unless the package isn't on conda or [conda-forge](https://conda-forge.org/).

Let me show you a sample command for each.

1. Install ipykernel via conda. (Actually do this so your notebook file will find the environment you just created.)
```
conda install ipykernel
```

2. Install [missingno](https://github.com/ResidentMario/missingno) via conda-forge. (This is an easy way to visualize missing data in your data set.)
```
conda install conda-forge::missingno
```

At some point you may wish to shut down your environment. That's very easy in conda:
```
conda deactivate
```
This command will close out the environment you're working in and take you back to your base environment.

__Creating a New Environment with pip and venv__

_Disclaimer:_ I work on a mac most of the time, so my knowledge for PC here is very sparse.

Another way to create a new python environment is via [pip](https://github.com/pypa/pip) and [venv](https://docs.python.org/3/library/venv.html). To briefly explain each:
- pip is Python's package installer.
- venv is a module for creating virtual environments.

You can use pip and venv in:
- Anaconda
- VSCode

Steps:
1. Open a command line window.
2. Navigate to your project folder.
3. Run the command below if you're on a PC:
```
py -m venv .venv
```
If you're on a Mac:
```
python3 -m venv .venv
```

The most important parts to understand are:
- 'py' or 'python3' specifies the type of virtual environment.

- '.venv' is the environment's name. Replace it with your choice of name.

Now you can activate your environment.
1. On PC
```
.venv\Scripts\activate
```

2. On Mac
```
.venv/bin/python
```

With an activated environment you can install packages via pip. See the examples below.

```
pip install ipykernel
```

As you can see, with pip there is one standard command: ```pip install```.

The line above installs only one module, but you can install multiple at once, too.
```
pip install missingno tabulate diptest
```

The line above installs 3 modules at once:
- missingno, for visualizing missing data
- tabulate, for creating nicer tables
- diptest, for performing Hartigan's Dip test that checks for multi-modality.

Finally, when you're ready to stop working on your project, close out your virtual environment:
```
deactivate
```

Also note that if you're working in a command line window or terminal shell, you can close it and it will also close your virtual environment.
