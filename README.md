# django-toxini

Boilerplate tox.ini file for Django projects. Drop a single file into your
repository to handle test running so you can start writing tests straight away.

Runs:
- [pytest](https://docs.pytest.org/en/latest/) for unit tests with [coverage](https://coverage.readthedocs.io/en/latest/).
- [flake8](https://flake8.pycqa.org/en/latest/) for linting.
- [mypy](https://mypy.readthedocs.io/en/stable/) for static type checking.

## Installation

Copy [tox.ini](tox.ini) into your Django project's root directory. You may want to
edit the `envlist` to be more restrictive as the default configuration will test
every valid version combination of Python 3 and Django.

Install [tox](https://tox.readthedocs.io/en/latest/install.html) e.g.:
```
python -m pip install tox
```

## Usage

```
tox
```
