# Contributor Guide

Thank you for your interest in improving this project.
This project is open-source under the [{{cookiecutter.license.replace("-", " ")}} license] and
welcomes contributions in the form of bug reports, feature requests, and pull requests.

Here is a list of important resources for contributors:

- [Source Code]
- [Documentation]
- [Issue Tracker]
- [Code of Conduct]

[{{cookiecutter.license.replace("-", " ").lower()}} license]: https://opensource.org/licenses/{{cookiecutter.license}}
[source code]: https://github.com/{{cookiecutter.github_user}}/{{cookiecutter.project_name}}
[documentation]: https://{{cookiecutter.project_name}}.readthedocs.io/
[issue tracker]: https://github.com/{{cookiecutter.github_user}}/{{cookiecutter.project_name}}/issues

## How to report a bug

Report bugs on the [Issue Tracker].

When filing an issue, make sure to answer these questions:

- Which operating system and Python version are you using?
- Which version of this project are you using?
- What did you do?
- What did you expect to see?
- What did you see instead?

The best way to get your bug fixed is to provide a test case,
and/or steps to reproduce the issue.

## How to request a feature

Request features on the [Issue Tracker].

## How to set up your development environment

_Recommended_: [Install `uv` package manager](https://docs.astral.sh/uv/guides/install-python/),
then setup your environment - `uv` installs all Python dependencies (if required Python version isn't available, it will be auto-downloaded):

```bash
$ uv sync
```

_Alternative_: Make sure `python --version` is 3.9+ and install using only standard library
(useful if `uv` can't be used, for example due to corporate firewall policies):

```bash
$ python -m venv .venv/
$ source .venv/bin/activate
$ pip install --editable .
```

## How to test the project

Run the full test suite:

```bash
$ uv run --dev pytest
```

Optionally, test for all supported Python versions:

```bash
$ uv run --dev tox
```

### Test Github Actions locally

Optionally test that Github Actions work by running [`act`](https://nektosact.com) command locally.

Install latest `act` version:

```bash
$ sudo dnf install golang          # on RedHat Linux based systems; check Go language install methods for all platform: https://go.dev/doc/install
$ git clone https://github.com:nektos/act.git
$ cd act
$ PREFIX=~/.local/ make install    # installs at ~/.local/bin/act ; default (without PREFIX specified) is to installs /usr/local/bin/act which requires root permission
```

Now locally test all Github Actions that _push_ to `main` branch:

```bash
$ act push
```

## How to Build Documentation locally

Build _docs/_ locally using [Sphinx](https://www.sphinx-doc.org/en/master/usage/quickstart.html): `make html`.

## How to submit changes

Open a [pull request] to submit changes to this project.

Your pull request needs to meet the following guidelines for acceptance:

- The Tox test suite must pass without errors and warnings.
- Include unit tests. This project maintains 100% code coverage.
- If your changes add functionality, update the documentation accordingly.

Feel free to submit early, though — we can always iterate on this.

Please ensure to install [pre-commit](https://pre-commit.com/) git hooks so that linting & type checking runs before every commit:

```bash
$ uv run --dev pre-commit install
```

You can optionally run pre-commit checks any other time also: `uv run --dev pre-commit run`.

It is recommended to open an issue before starting work on anything.
This will allow a chance to talk it over with the owners and validate your approach.

[pull request]: https://github.com/{{cookiecutter.github_user}}/{{cookiecutter.project_name}}/pulls

<!-- github-only -->

[code of conduct]: CODE_OF_CONDUCT.md
