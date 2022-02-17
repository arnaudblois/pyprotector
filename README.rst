===============
Pyprotector
===============

Python package designed to perform sanity-checks and gate-keeping on the packages produced internally by an organisation. Handles internal structure, naming conventions and namespaces, etc


How to install
==============

You can install it via `pip` in a venv, or even better, if your project dependencies
are managed by Poetry: `poetry add pyprotector`


How to contribute
=================

To set up this project locally to contribute:


.. code-block::

    # Clone the project and create a new feature branch
    git clone
    cd pyprotector
    git checkout -b <feature-branch-name>

    # This installs the required dependencies
    poetry install

    # Activate your virtualenv
    poetry shell

    # Here we add a few pre-commit hooks to make sure the files
    # are formatted correctly (isort, flake8, black). It also add
    # checks to enforce conventional commits
    # these steps are defined in .pre-commit-config.yaml
    pre-commit install && pre-commit install --hook-type commit-msg

    # at this point, the tests can be run with:
    flake8
    pylint_runner
    pytest


Checks before releasing to Pypi repo
====================================

1. Update the CHANGELOG. We can use the output of `gitchangelog` for this.

.. code-block:: bash

  poetry run gitchangelog


2. Make sure the versions in :code:`pyproject.toml`, :code:`src/<package-name>/__init__.py`
and :code:`docs/conf.py` are updated to the version to release, please follow semantic versioning convention.
3. Make sure everything is committed and merged to `main`.
4. Create a release tag in GitHub, this will run the python-publish action.


Credits
=========

The boilerplate of this project was generated from the
template `here <https://github.com/arnaudblois/pypi-package-template/>`_
using `PyTemplator <https://pypi.org/project/pytemplator/>`_ v0.1.0a2.
