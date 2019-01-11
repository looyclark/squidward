# Squidward

After working with gaussian processes (GPs) to build out robust reinforcement learning models in production for most of my early career as a machine learning engineer (MLE), I became frustrated with the packages available for building GPs. They often focus using the latest in optimization tools and are far from the elegant, efficient, and simple design that I believe a GP package should embody.

This is my attempt to create the product that I would want to use. Something simple and flexible that gives knowledgable data scientists the tools they need to do the research or production machine learning work that they need.

I'm open to all feedback, commentary, and suggestions as long as they are constructive and polite.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Installing

This is a step by step guide to installing squidward for your local environment.

I recommend installing squidward in a virtual environment for organized dependency control. Personally, I prefer conda environments. Create your environment and then go into it.

```
conda create --name squidward_env python=3.6
source activate squidward_env
```

To install the latest stable version, simply pip install from pypi!

```
pip install squidward
```

However, if you want the latest version git clone this repository to your local environment instead.

```
git clone https://github.com/looyclark/squidward.git
```

Change directory (cd) into the root of the squidward repository.

```
cd ./squidward
```

Install squidward using pip from the setup file.

```
pip install .
```

## Running the unit tests

To run the unit tests cd to `squidward/squidward` so that `/tests` is a subdirectory.

```
cd ./squidward/squidward
```

Use `nosetests` to run all unit tests for squidward. If you installed squidward in a virtual environment, please run the tests in that same environment.

```
source activate squidward_env
nosetests
```

You can also run the tests with coverage to see what code within the package is called in the tests.

```
nosetests --with-coverage --cover-package=squidward
```

## Running the style tests

I attempt to adhere to the [pep8](https://www.python.org/dev/peps/pep-0008/) style guide for the squidward project. To run the style tests cd to the root directory of the repository `squidward/` so that `/squidward` is a subdirectory. Use `pylint squidward` to run all style tests for squidward.

```
cd ./ squidward
pylint squidward
```

Some of the naming conventions I've chosen intentionally do not adhere to pep8 in order to better resemble mathematical conventions. For example, identity matrices may be named `I` even though this does not adhere to snake case conventions. You can run `pylint --disable=invalid-name` if you would like to ignore the resulting pylint warnings.

```
pylint --disable=invalid-name
```

## Deployment

For fastest performance, it is recommended to use numpy/scipy with MKL (Math Kernel Library).

## Continuing Improvement

This package started as a fever dream in response to a series of frustrations I had with currently implemented gaussian process (GP) packages. Many GP packages favor using the latest and greatest optimization packages rather than focusing on creating an efficient, simple, flexible tool for data scientists to use.

I hope to grow this package into a robust tool for use in research or production environments. It is far from a finished product.

Next Steps:
1. Polish core functionality and comment thoroughly
2. Build out robust unit test and integration tests
3. Add code quality and style guide checks
4. Posterior Predictive checks
5. Optimization and sampling functionality
6. Embedding optimization for efficient inversion at scale
7. Multiprocessing for parallelization
8. Robust examples for reinforcement learning and parameter optimization

## Authors

* **James Montgomery** - *Initial work* - [jamesmontgomery.us](http://jamesmontgomery.us)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* A big thanks to Keegan Hines and Josh Touyz who introduced me to Gaussian Processes
* Another thanks to Thanos Kintsakis who helped turn me from a data scientist into a machine learning engineer who can produce maintainable and efficient code.
* The core functionality of this code (gpr and gpc) is based on the book [Gaussian Processes for Machine Learning](http://www.gaussianprocess.org/gpml/) chapters 2 and 3.
* The native kernels supported by squidward are largely drawn from the [kernel cookbook](https://www.cs.toronto.edu/~duvenaud/cookbook/) by David Duvenaud.

## Alternative Gaussian Process Packages

This is hardly the only gaussian process package out there. Here are a few alternatives in case you dislike this package.

* [GPyTorch](https://gpytorch.ai/)
* [GPy](https://gpy.readthedocs.io/en/deploy/)
* [GPFlow](https://gpflow.readthedocs.io/en/develop/)
* [Sklearn](https://scikit-learn.org/stable/modules/gaussian_process.html)
* [George](https://george.readthedocs.io/en/latest/tutorials/first/)
* [Pymc3](https://docs.pymc.io/api/gp.html)
* [Stan](https://betanalpha.github.io/assets/case_studies/gp_part1/part1.html)