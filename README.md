<!-- Replace all instances of glitchsim in this file with your package name, then delete this line! -->
# glitchsim

[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
[![Tests status][tests-badge]][tests-link]
[![Linting status][linting-badge]][linting-link]
[![Documentation status][documentation-badge]][documentation-link]
[![License][license-badge]](./LICENSE.md)

<!-- prettier-ignore-start -->
[tests-badge]:              https://github.com/NSs-FLF-RHUL/glitchsim/actions/workflows/tests.yml/badge.svg
[tests-link]:               https://github.com/NSs-FLF-RHUL/glitchsim/actions/workflows/tests.yml
[linting-badge]:            https://github.com/NSs-FLF-RHUL/glitchsim/actions/workflows/linting.yml/badge.svg
[linting-link]:             https://github.com/NSs-FLF-RHUL/glitchsim/actions/workflows/linting.yml
[documentation-badge]:      https://github.com/NSs-FLF-RHUL/glitchsim/actions/workflows/docs.yml/badge.svg
[documentation-link]:       https://github.com/NSs-FLF-RHUL/glitchsim/actions/workflows/docs.yml
[license-badge]:            https://img.shields.io/badge/License-GPLv3-blue.svg
<!-- prettier-ignore-end -->

## About

:warning: This package is currently under construction and in pre-release.
The API and features may change suddenly without warning.

This repository provides two Jupyter notebooks and accompanying files to recreate the results and plots of [Graber et al. (2018)](http://arxiv.org/abs/1804.02706). Please cite Graber et al. (2018) as well as [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1324469.svg)](https://doi.org/10.5281/zenodo.1324469) when using this material

## Description

The Jupyter notebook `rapid_crust_coupling.ipynb` contains code to integrate the TOV equations for a specific neutron star crust model and calculate the mutual friction coefficients as a function of cylindrical radius and relative mass fraction. It subsequently allows numerical integration of a simple three-component neutron star toy model, providing the time evolution of the angular velocities, to determine the characteristic shape of the glitch rise of a Vela-like pulsar. A preliminary comparison between these theoretical predictions and the first single-pulse radio observations by [Palfreyman et al. (2018)](https://www.nature.com/articles/s41586-018-0001-x) as discussed in Section 5 of Graber et al. (2018) is provided in the Jupyter notebook `data_comparison.ipynb`.

The file `microscopic_parameters.txt` contains the microscopic parameters for the inner crust as given in Table 1 of Graber et al. (2018). Moreover, `41586_2018_1_MOESM1_ESM.csv` consists of the data for the observed glitch provided by Palfreyman et al. (2018), whereas the files `model_residuals_Bcore5e-5.txt` and `model_residuals_Bcore_comparison.txt` contain the corresponding predictions as obtained from theoretical models.

We also provide the environment file that has been used to create our results. It can be installed by running `conda env create -f environment.yaml`
and has been tested under Linux, Mac OS and Microsoft. Please contact the author if you have any problems.


### Project Team

Vanessa Graber ([vanessa.graber@rhul.ac.uk](mailto:vanessa.graber@rhul.ac.uk))
Gary Liu ([Gary.Liu@rhul.ac.uk](mailto:Gary.Liu@rhul.ac.uk))
<!-- TODO: how do we have an array of collaborators - steal from s2fft -->

## Getting Started

### Prerequisites

<!-- Any tools or versions of languages needed to run code. For example specific Python or Node versions. Minimum hardware requirements also go here. -->

`glitchsim` requires Python 3.11.

### Installation

<!-- How to build or install the application. -->

We recommend installing in a project specific virtual environment created using
a environment management tool such as
[Conda](https://docs.conda.io/projects/conda/en/stable/). To install the latest
development version of `glitchsim` using `pip` in the currently active
environment run

```sh
pip install git+https://github.com/NSs-FLF-RHUL/glitchsim.git
```

Alternatively create a local clone of the repository with

```sh
git clone https://github.com/NSs-FLF-RHUL/glitchsim.git
```

and then install in editable mode by running

```sh
pip install -e .
```

### Running Locally

### Running Tests

<!-- How to run tests on your local system. -->

Tests can be run across all compatible Python versions in isolated environments
using [`tox`](https://tox.wiki/en/latest/) by running

```sh
tox
```

To run tests manually in a Python environment with `pytest` installed run

```sh
pytest tests
```

again from the root of the repository.

### Building Documentation

The MkDocs HTML documentation can be built locally by running

```sh
tox -e docs
```

from the root of the repository. The built documentation will be written to
`site`.

Alternatively to build and preview the documentation locally, in a Python
environment with the optional `docs` dependencies installed, run

```sh
mkdocs serve
```
