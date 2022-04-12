# KCE: How to install

```
# create virtual environment
conda create -n limix python=3.9
conda activate limix

# download repo
git clone https://github.com/KennethEnevoldsen/limix/tree/master
cd limix
git checkout 2.0.x  # change to version 2.0.x (to get access to struct LMM)


# update package manager to get new dependency resolver
pip install pip --upgrade

# install package in editable model (to allow for changes after installation. If you don't care simply remove the -e)
pip install -e .
# this takes a short while as it tries to resolve all the dependencies.
```

From here they argue you should test it using:
```
python -c "import limix; limix.test()"
```

Which throws an error. However the error simply states that two arrays which are essentially the same have a different nth decimal.
```
    -array([[1.764052],
    -       [0.400157],
    -       [0.978738],
    -       [2.240893]])
    +array([[1.76405235],
    +       [0.40015721],
    +       [0.97873798],
    +       [2.2408932 ]])
```

Instead what I do to test that everything is working is running the struct-lmm.ipynb tutorial.

Here everything seems to work as intended. (at least I get the same results as he do in his notebook)


# limix

[![Travis](https://img.shields.io/travis/com/limix/limix/2.0.x.svg?style=flat-square&label=linux%20%2F%20macos%20build)](https://travis-ci.com/limix/limix) [![AppVeyor](https://img.shields.io/appveyor/ci/Horta/limix/2.0.x.svg?style=flat-square&label=windows%20build)](https://ci.appveyor.com/project/Horta/limix) [![Documentation](https://readthedocs.org/projects/limix/badge/?version=2.0.x&style=flat-square)](https://limix.readthedocs.io/en/2.0.x/)

Genomic analyses require flexible models that can be adapted to the needs of the user.

Limix is a flexible and efficient linear mixed model library with interfaces to Python.
It includes methods for

- Single-variant association and interaction testing
- Variance decompostion analysis with linear mixed models
- Association and interaction set tests
- Different utils for statistical analysis, basic i/o, and plotting.

The documentation can be found at https://limix.readthedocs.io.

## Install

Installation is easy and works on macOS, Linux, and Windows:

```bash
pip install limix
```

If you already have Limix but want to upgrade it to the latest version:

```bash
pip install limix --upgrade
```

## Running tests

After installation, you can test it

```bash
python -c "import limix; limix.test()"
```

as long as you have [pytest](https://docs.pytest.org/en/latest/).

## Authors

* [Christoph Lippert](https://github.com/clippert)
* [Danilo Horta](https://github.com/horta)
* [Francesco Paolo Casale](https://github.com/fpcasale)
* [Oliver Stegle](https://github.com/ostegle)

## License

This project is licensed under the [Apache License License](https://raw.githubusercontent.com/limix/limix/2.0.0/LICENSE.md).
