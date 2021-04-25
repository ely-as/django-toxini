# django-toxini

Boilerplate tox.ini file for Django projects. Drop a single file into your
repository to handle test running so you can start writing tests straight away.

Runs:
- [pytest](https://docs.pytest.org/en/latest/) for unit tests with
  [coverage](https://coverage.readthedocs.io/en/latest/).
- [flake8](https://flake8.pycqa.org/en/latest/) for linting.
- [mypy](https://mypy.readthedocs.io/en/stable/) for static type checking.

## Installation

Install [tox](https://tox.readthedocs.io/en/latest/install.html) e.g.:
```
python -m pip install tox
```

Copy [tox.ini](tox.ini) into your Django project's root directory. Edit:
- The [`skipsdist` option](tox.ini#L2), if needed.
- The [`envlist`], if needed.

## Usage

```
tox
```

## GitHub Actions

Optionally you may also copy the [.github](.github) directory (or the
[test.yml]( .github/workflows/test.yml) workflow specifically) to run the test
suite automatically using GitHub Actions after each push update.

## Tools used

- [tox automation project](https://tox.readthedocs.io/en/latest/index.html)
- [pytest](https://docs.pytest.org/en/latest/)
  - [pytest-dev/pytest-mock](https://github.com/pytest-dev/pytest-mock/)
  - [pytest-dev/pytest-cov](https://github.com/pytest-dev/pytest-cov)
- [coverage](https://coverage.readthedocs.io/en/latest/)
- [flake8](https://flake8.pycqa.org/en/latest/)
- [mypy](https://mypy.readthedocs.io/en/stable/)
- [ymyzk/tox-gh-actions](https://github.com/ymyzk/tox-gh-actions)
