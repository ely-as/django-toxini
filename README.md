# django-toxini

Boilerplate [tox.ini](tox.ini) file for Django projects. Drop a single
pre-configured file into your repository to handle test running so you can start
writing tests straight away.

Runs:
- [pytest](https://docs.pytest.org/en/latest/) for unit tests with
  [coverage](https://coverage.readthedocs.io/en/latest/). pytest's
  [django](https://github.com/pytest-dev/pytest-django/) and
  [mock](https://github.com/pytest-dev/pytest-mock/) plugins are included by
  default.
- [flake8](https://flake8.pycqa.org/en/latest/) for linting.
- [mypy](https://mypy.readthedocs.io/en/stable/) for static type checking.

Supports:
- [black](https://black.readthedocs.io/en/stable/) for code formatting
  (runs check only).

## Installation

Install [tox](https://tox.readthedocs.io/en/latest/install.html) e.g.:
```sh
python -m pip install tox
```

Copy [tox.ini](tox.ini) into your Django project's root directory. Edit:
- The [`skipsdist` option](tox.ini#L2), if needed.
- The [`isolated_build` option](tox.ini#L4), if needed.
- The `envlist`, if needed. See the [available testenv's](#available-testenvs).

## Usage
```sh
tox
```

To run a single [testenv](#available-testenvs):
```sh
tox -e flake8
```

## Available testenv's

A pytest testenv can be generated by combining multiple _factors_:
- `pyNM`: to use a specific Python versions i.e. `py36`, `py37`, `py38`,
  `py39`, `py310` or `py311`
- `django` to install the latest Django version
- `pyNM-djangoNM` to install a specific Django version and use with a specific
  Python interpreter e.g. `py36-django20`, `py38-django22`
- `requirements` to install dependencies defined in `requirements.txt` (if
  present)
- `pytest` to run tests

_Factors_ are delimited by hyphens. Examples:
```sh
tox -e py39-django32-pytest
tox -e requirements-pytest
```

The following
[generative envlist](https://tox.wiki/en/latest/config.html#generating-environments-conditional-settings)
represents all valid combinations of Python 3 (up to 3.11) and Django (up to
4.1):
```ini
py36-django{111,20,21,22,30,31,32}-pytest
py38-django{22,30,31,32,40,41}-pytest
py39-django{22,30,31,32,40,41}-pytest
py310-django{32,40,41}-pytest
py311-django41-pytest
```

A flake8, mypy or black testenv can be generated using:
- `flake8`
- `mypy`
- `black`

These may also be combined with a Python version e.g. `py36-flake8`.

## Continuous Integration

### GitHub Actions

You may wish to copy and adapt the [.github](.github) directory (or the
[test.yml]( .github/workflows/test.yml) workflow specifically) to run the test
suite automatically using GitHub Actions after each push update. See the
documentation for
[ymyzk/tox-gh-actions](https://github.com/ymyzk/tox-gh-actions) for more
information on configuration.

### GitLab CI/CD

You may wish to copy and adapt the [.gitlab-ci.yml](.gitlab-ci.yml) file to run
the test suite automatically using GitLab CI/CD after each push update.

## Tools used

- [tox automation project](https://tox.readthedocs.io/en/latest/index.html)
- [pytest](https://docs.pytest.org/en/latest/)
  - [pytest-dev/pytest-cov](https://github.com/pytest-dev/pytest-cov)
  - [pytest-dev/pytest-django](https://github.com/pytest-dev/pytest-django/)
  - [pytest-dev/pytest-mock](https://github.com/pytest-dev/pytest-mock/)
- [coverage](https://coverage.readthedocs.io/en/latest/)
- [flake8](https://flake8.pycqa.org/en/latest/)
- [mypy](https://mypy.readthedocs.io/en/stable/)
- [black](https://black.readthedocs.io/en/stable/)
- [ymyzk/tox-gh-actions](https://github.com/ymyzk/tox-gh-actions)
