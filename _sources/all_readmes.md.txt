# Sample Binder Repositories

Below we list several sample Binder repositories that
demonstrate how to compose build files in order to create
Binders with varying environments.

## [julia-python](https://github.com/binder-examples/julia-python)


Files:
* `REQUIRE`
* `environment.yml`
* `julia.ipynb`
* `python-and-julia.ipynb`
* `python.ipynb`


### Julia and Python environments
This example shows how you can install a Julia and Python environment side-by-side.
In this repository are *both* an `environment.yml` file as well as a `REQURE` file.
The former corresponds to an anaconda python environment, and the latter corresponds
to a Julia environment. Both kernels will be available to you in a built Binder
environment.

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/julia_python/master)




## [requirements](https://github.com/binder-examples/requirements)


Files:
* `index.ipynb`
* `requirements.txt`


### Example Binder with requirements.txt

A Binder-compatible repo with a `requirements.txt` file.

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/requirements/master)

Access this Binder at the following URL: 

http://beta.mybinder.org/v2/gh/binder-examples/requirements/master

### Notes
The `requirements.txt` file should list all Python libraries that your notebooks
depend on, and they will be installed using:

```
pip install -r requirements.txt
```

The base Binder image contains no extra dependencies, so be as
explicit as possible in defining the packages that you need. This includes
specifying explict versions wherever possible.

In this example we include the library `seaborn`, and our notebook uses it
to plot a figure. 



## [conda](https://github.com/binder-examples/conda)


Files:
* `environment.yml`
* `index.ipynb`


### Example Binder with environment.yml

A Binder-compatible repo with an `environment.yml` file.

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/conda_environment/v1.0?filepath=index.ipynb)

Access this Binder at the following URL:

http://beta.mybinder.org/v2/gh/binder-examples/conda_environment/v1.0?filepath=index.ipynb

### Notes
The `environment.yml` file should list all Python libraries on which your notebooks
depend, specified as though they were created using the following `conda` commands:

```
source activate example-environment
conda env export > environment.yml
```

Note that the only libraries available to you will be the ones specified in
the `environment.yml`, so be sure to include everything that you need!



## [remote_storage](https://github.com/binder-examples/remote_storage)


Files:
* `index.ipynb`
* `requirements.txt`


### Example Binder using remote storage

A Binder-compatible repo that shows accessing data from remote sources.

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/remote_storage/master)

Access this Binder at the following URL:

http://beta.mybinder.org/v2/gh/binder-examples/remote_storage/master


### Notes
The notebooks use `boto` and `requests` to load both images and tables from S3.
The image loading makes use of `PIL` and the table loading
makes use of `pandas`.



## [latex](https://github.com/binder-examples/latex)


Files:
* `apt.txt`
* `index.ipynb`
* `postBuild`
* `requirements.txt`


### Using latex with Binder
This repository demonstrates how to install latex alongside matplotlib
for Binder. This requires a few different build components:

* `apt.txt` for apt-installing the latex components
* `requirements.txt` for installing the python dependencies
* `postBuild` for forcing matplotlib to build the font cache

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/latex/master)

Thanks to @m-weigand for giving
[inspiration for this repo](https://github.com/m-weigand/binder-example-latex-mpl/blob/master/index.ipynb)!



## [jupyterlab](https://github.com/binder-examples/jupyterlab)


Files:
* `binder`
* `geojson-extension.geojson`
* `index.ipynb`


### JupyterLab + Binder

Demonstrating how to get JupyterLab working with Binder.

Currently, you may enable JupyterLab in Binder with the following steps:

1. Launch a Binder instance (e.g., by clicking the Binder badge below).
2. Replace `tree` at the end of your URL with `lab`.
3. That's it!

This repository installs several JupyterLab extensions via a `postBuild` script, allowing
you to use JupyterLab's extensions and widgets functionality.

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/jupyterlab/master)




## [dockerfile-r](https://github.com/binder-examples/dockerfile-r)


Files:
* `Dockerfile`
* `index.ipynb`


##[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/dockerfile-r/master?filepath=index.ipynb)

### Specifying an R environment with Binder using a Dockerfile

While Python and Julia are the only two languages natively supported with
build files, it's possible to create R Kernels for use with Binder as well.

This repository shows how you can use a Dockerfile to install R and
connect it with Jupyter. This lets you run R code from within the Jupyter Notebooks.



## [dockerfile-rstudio](https://github.com/binder-examples/dockerfile-rstudio)


Files:
* `Dockerfile`
* `index.R`


### RStudio in Binder using a Dockerfile

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/dockerfile-rstudio/master)

This is a proof-of-concept to deploy a Binder that exposes the
RStudio UI instead of a Jupyter Notebook. It also installs
several packages from the tidyverse, and includes a demo
script to show off functionality.

To start your RStudio session, click on "new", and at the bottom will
be `RStudio Session`. Click that and you're ready to go!

*Special thanks to Ryan Lovett (@ryanlovett) for figuring out
RStudio support with JupyterHub*



## [python2_runtime](https://github.com/binder-examples/python2_runtime)


Files:
* `index.ipynb`
* `requirements.txt`
* `runtime.txt`


### Python 2 with `runtime.txt`

We can specify various runtime parameters with a `runtime.txt` file. In this
repository, we demonstrate how to install python 2 with this environment.

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/python2_runtime/master)



## [jupyter-extension](https://github.com/binder-examples/jupyter-extension)


Files:
* `index.ipynb`
* `postBuild`
* `requirements.txt`


### Jupyter Extensions with Binder

[![Binder](https://beta.mybinder.org/badge.svg)](https://beta.mybinder.org/v2/gh/binder-examples/jupyter-extension/master?filepath=index.ipynb)

This example demonstrates how to enable Jupyter extensions with Binder. We'll
cover a few in this repo because some are idiosyncratic in how they're enabled.

We accomplish each using a `requirements.txt` file to install the extensions,
then a `postBuild` file to enable them.

### ipywidgets

Ipywidgets lets you create interactive widgets in your notebook.
Installation is fairly straightforward. You install the python package,
then enable the extension.

### python-markdown
The `python-markdown` extension is useful for interweaving computational
cells (e.g., python cells) and markdown cells. As this extension automatically
runs code in the notebook, you need to be sure to "trust" the notebooks in your
`postBuild` script (see the script in this repo for example).



## [python-conda_pip](https://github.com/binder-examples/python-conda_pip)


Files:
* `environment.yml`


### Using anaconda with pip in the same build

[![Binder](http://mybinder.org/badge.svg)](http://beta.mybinder.org/v2/gh/binder-examples/python-conda_pip/master?filepath=index.ipynb)

If you use `environment.yml`, then Binder will use a Miniconda distribution
to install your packages. However, you may still want to use `pip`. In
this case, you should **not** use a `requirements.txt` file, but instead use
a `- pip` section in `environment.yml`. This repository is an example of how
to construct your `environment.yml` file to accomplish this.

Access this Binder at the following URL:

http://beta.mybinder.org/v2/gh/binder-examples/python-conda_pip/master?filepath=index.ipynb



