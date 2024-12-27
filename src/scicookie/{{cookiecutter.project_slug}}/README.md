{% set is_open_source = cookiecutter.project_license != 'Other' -%}
# {{ cookiecutter.project_name }}

{{ cookiecutter.project_short_description }}

{% if is_open_source -%}

- Software License: {{ cookiecutter.project_license }}
{%- endif %}
- Documentation: https://{{ cookiecutter.project_slug }}.github.io

## Features

{% if cookiecutter.project_layout == "src" %}
- **Structure of the project**: this project uses the _src (Source) layout_, a
  common approach where the source code files are organized within a dedicated
  "src" directory.
{%- elif cookiecutter.project_layout == "flat" %}
- **Structure of the project**: this project uses the _flat layout_, involves
  placing all the project's source code files directly in the project's root
  directory.
{%+ endif %}
{% if cookiecutter.build_system == "poetry" %}
- **Build system**: [_Poetry_](https://python-poetry.org/) with Poetry, you can
  easily install, update, and remove dependencies, and it automatically handles
  conflicts and resolution between packages.
{%- elif cookiecutter.build_system == "flit" %}
- **Build system**: [_Flit_](https://flit.pypa.io) it's a Python package and a
  lightweight tool for creating and distributing Python packages. It automates
  the processes involved in packaging and submitting a project to PyPI.
{%- elif cookiecutter.build_system == "mesonpy" %}
- **Build system**:
  [_Meson-python_](https://meson-python.readthedocs.io/en/latest/index.html) with
  meson-python, we can easily define project dependencies, specify build
  options, generate configuration files and build scripts, among other things.
{%- elif cookiecutter.build_system == "setuptools" %}
- **Build system**: [_Setuptools_](https://setuptools.pypa.io/en/latest/)
  provides a way to define metadata about your project. It also provides
  functionality for building and distributing packages, creating distribution
  archives, and installing packages with their dependencies.
{%- elif cookiecutter.build_system == "pdm" %}
- **Build system**: [_PDM_](https://pdm.fming.dev/) it has very
  powerful features, including easy and fast dependency resolution, especially
  for large binary distributions, a PEP 517 compilation backend, PEP 621
  project metadata, a flexible and powerful plugin system.
{%- elif cookiecutter.build_system == "hatch" %}
- **Build system**: [_Hatch_](https://hatch.pypa.io) it provides a standardized
  build system with reproducible builds by default, robust environment
  management with support for custom scripts, easy publishing to PyPI or other
  indexes, version management, and configurable project generation with sane
  defaults.
{%- elif cookiecutter.build_system == "maturin" %}
- **Build system**: [_Maturin_](https://pypi.org/project/maturin/0.8.2/) it's
  build system designed to create Python bindings from Rust projects. It allows
  Rust code to be seamlessly integrated into Python applications, providing
  efficient builds and cross-platform support for various Python versions.
{%- elif cookiecutter.build_system == "scikit-build-core" %}
- **Build system**:
  [_scikit-build-core_](https://scikit-build-core.readthedocs.io/en/latest/) it's
  build system designed for Python packaging tool, serving as an enhanced build
  system generator for CPython C extensions greatly improves package management
  within the scientific Python ecosystem.
{%- elif cookiecutter.build_system == "pybind11" %}
- **Build system**: [_setuptools +
  pybind11_](https://pybind11.readthedocs.io/en/stable/) it's build system
  designed for C++ library that simplifies the creation of Python bindings for
  C++ code, enabling easy integration of C++ functions and classes into Python
  scripts.
{%- elif cookiecutter.build_system == "pixi" %}
- **Build system**: [_Pixi_](https://pixi.sh/latest/) is a package manager
  designed to simplify dependency management by creating reproducible
  development environments.
{%+ endif %}
{% if cookiecutter.command_line_interface == "Click" %}
- **Command-line interface (CLI)**: this project uses
  [_Click_](https://click.palletsprojects.com/en/8.1.x/) a Python package that
  allows you to create beautiful command line interfaces in a composable way
  with as little code as necessary.
{%- elif cookiecutter.command_line_interface == "Argparse" %}
- **Command-line interface (CLI)**: this project uses
  [_Argparse_](https://docs.python.org/3/library/argparse.html), the
  recommended command line parsing module in the Python standard library.
  Provides an easy way to create command line interfaces with custom arguments
  and options.
{%+ endif %}
{% if cookiecutter.documentation_engine == "mkdocs" %}
- **Documentation engine**: [_mkdocs_](https://www.mkdocs.org/) is a fast,
  simple, and downright gorgeous static site generator for creating project
  documentation.
  The _Theme_ used is {{ cookiecutter.mkdocs_theme }}
{%- elif cookiecutter.documentation_engine == "sphinx(rst)" %}
- **Documentation engine**: [_Sphinx_](https://www.sphinx-doc.org/en/master/)
   _Sphinx-rst_ uses the _reStructuredText_ markup language
  by default. The _Theme_ used is: {{ cookiecutter.sphinx_theme }}
{%- elif cookiecutter.documentation_engine == "sphinx(myst)" %}
- **Documentation engine**: [_Sphinx_](https://www.sphinx-doc.org/en/master/)
   _Sphinx-myst_(Markedly Structured Text - Parser) is a
  Sphinx and Docutils extension to parse MyST.
  The _Theme_ used is: {{ cookiecutter.sphinx_theme }}
{%- elif cookiecutter.documentation_engine == "jupyter-book" %}
- **Documentation engine**:
[_JupyterBook_](https://jupyterbook.org/en/stable/intro.html) uses Jupyter
notebooks as the basis for creating interactive content.
The _Theme_ used is: {{ cookiecutter.jupyter_book_theme }}
{%- elif cookiecutter.documentation_engine == "quarto" %}
- **Documentation engine**: [_Quarto_](https://quarto.org/) it offers the
  unique feature of embedding Python code directly into your documentation,
  enabling interactive and dynamic content creation.
  The _Theme_ used is: {{ cookiecutter.quarto_theme }}
{%+ endif %}
{% if cookiecutter.use_conda == "yes" %}
- **Virtual environment**: this project uses
  [_Conda_](https://docs.conda.io/en/latest/) an open source package and
  environment management system that quickly installs, runs and updates
  packages and their dependencies.
{%- else %}
- **Virtual environment**: this project uses
  [_virtualenv_](https://virtualenv.pypa.io/en/latest/) a tool to create
  isolated Python environments.
{%+ endif %}
{% if cookiecutter.use_black == "yes" %}
- **Code formatter**: we use [_Black_](https://black.readthedocs.io), a
  popular code formatter tool for Python that automatically formats code to
  conform to PEP 8 guidelines.
{%- elif cookiecutter.use_ruff_formatter == "yes" %}
- **Code formatter**: we use [_Ruff_](https://docs.astral.sh/ruff/), a versatile
  tool for Python that offers both linting and auto-formatting capabilities. As
  an auto-formatter, Ruff ensures consistent code formatting, fixes import
  sorting, and adheres to best practices.
{%- elif cookiecutter.use_prettier == "yes" %}
- **Code formatter**: we use [_Prettier_](https://prettier.io/docs/en/), an
  opinionated code formatter that removes all original styling and ensures that
  all output code conforms to a consistent style.
{%+ endif %}
{%- if cookiecutter.use_bandit == "yes" %}
- **The security of our code**:
  [_Bandit_](https://bandit.readthedocs.io/en/latest/) is a powerful tool that
  analyzes the code and detects potential vulnerabilities.
{%+ endif -%}
{%- if cookiecutter.use_coverage == "yes" %}
- **Code coverage testing**: [_Coverage_](https://coverage.readthedocs.io/)
  it's an open source tool for measuring the code coverage of a program. This
  means that it measures what percentage of the program code was executed when
  the tests were run.
{%+ endif -%}
{%- if cookiecutter.use_flake8 == "yes" %}
- **Code style**: we use [_Flake8_](https://flake8.pycqa.org/), a tool that
  helps you find potential performance issues in your code. Flake8 can detect
  errors in syntax, indentation, naming conventions, and other types of style
  errors.
{%+ endif -%}
{%- if cookiecutter.use_ruff_linter == "yes" %}
- This project uses [_Ruff_](https://docs.astral.sh/ruff/), an extremely fast
  Python _linter_ written in Rust. Ruff is designed to perform the process of
  inspecting code for potential bugs or style problems quickly and efficiently.
{%+ endif -%}
{%- if cookiecutter.use_isort == "yes" %}
- **Code separation**: we use [_isort_](https://pycqa.github.io/isort/) a
  Python utility/library for automatically sorting imports alphabetically and
  separating them into sections and by type.
{%+ endif -%}
{%- if cookiecutter.use_pydocstyle == "yes" %}
- This package uses [_pydocstyle_](http://www.pydocstyle.org/en/stable/) for
  checking compliance with Python documentation conventions.
{%+ endif -%}
{%- if cookiecutter.use_vulture == "yes" %}
- **Finds unused code**: [_Vulture_](https://github.com/jendrikseipp/vulture) is
  useful for cleaning up and finding errors in large code bases in Python.
{%+ endif -%}
{%- if cookiecutter.use_mccabe == "yes" %}
- **Complexity of functions and modules**: We use
[_McCabe_](https://github.com/PyCQA/mccabe) to identify the complexity in our
Python code that may be difficult to maintain or understand. This tool is
included with [Flake8](https://flake8.pycqa.org/en/latest/).
{%+ endif -%}
{%- if cookiecutter.use_mypy == "yes" %}
- This package uses [_mypy_](https://mypy.readthedocs.io/en/stable/) as a
  _static type checker_ in the code. It helps to ensure that we are using variables and
  functions correctly in the code.
{%+ endif -%}
{%- if cookiecutter.use_pytest == "yes" %}
- **Test library**: in this project we performed the test with
  [_Pytest_](https://docs.pytest.org/en/),  a popular testing framework that
  discovers and collects test cases, allows you to configure tests, manage
  resources, and write test functions.
{%- elif cookiecutter.use_hypothesis == "yes" %}
- **Test library**: in this project we performed the test with
  [_Hypothesis_](https://hypothesis.readthedocs.io/) a property-based testing
  library for Python. It focuses on generating diverse input data and exploring
  different scenarios to thoroughly test code.
{%+ endif -%}
{%- if cookiecutter.use_shellcheck == "yes" %}
- **Static analysis of shell scripts**: we use
  [_ShellCheck_](https://github.com/koalaman/shellcheck). It checks shell
  scripts for common errors and potential bugs, such as syntax errors, variable
  misuse, and command substitution issues.
{%+ endif -%}
{%- if cookiecutter.use_pre_commit == "yes" %}
- **Pre-commit verification**: this project uses
  [_pre-commit_](https://pre-commit.com/) a framework for managing and
  maintaining multi-language pre-commit hooks.
{%+ endif -%}
{%- if cookiecutter.use_containers == 'Docker' %}
- **Integration with DevOps tools**: we use _Docker_ because it allows you to
  easily share our application with others and deploy it in different
  environments. This streamlines our development, testing, deployment and
  collaboration workflows, making the whole process more efficient.

  **Note**
  [**Podman**](https://podman.io/) is supported via
  [`docker-compose`](https://docs.docker.com/compose/).
{%+ endif %}
{%- if cookiecutter.use_makim == "yes" %}
- **Automation tools**: this project uses
  [_Makim_](https://osl-incubator.github.io/makim) an innovative tool inspired
  by make, designed to simplify target and dependency definition through YAML
  format. Makim empowers users to streamline documentation and parameterize
  targets effectively.
{%- elif cookiecutter.use_make == "yes" %}
- **Automation tools**: this project uses
  [_Make_](<https://en.wikipedia.org/wiki/Make_(software)>), a versatile build
  automation tool that uses Makefiles to define rules and dependencies for
  compiling code and building projects.
{%+ endif %}
- The _Code of conduct_ used is based on: {{ cookiecutter.code_of_conduct }}
- The _Governance document_ used is based on: {{ cookiecutter.governance_document }}
- The _Roadmap document_ used is based on: {{ cookiecutter.roadmap_document }}
{%- if cookiecutter.use_github_actions == "yes" %}
- **Continuous integration**: we use [_GitHub
  Actions_](https://github.com/features/actions), a native CI/CD platform
  integrated with GitHub, it offers flexible workflows and an easy setup
  process.
{%- elif cookiecutter.use_circleci == "yes" %}
- **Continuous integration**: we use [_CircleCI_](https://circleci.com/), known
  for its speed and reliability, CircleCI is a cloud-based CI/CD platform that
  streamlines the development process.
{%- elif cookiecutter.use_azure_pipelines == "yes" %}
- **Continuous integration**: we use [_Azure
  Pipelines_](https://azure.microsoft.com/products/devops/pipelines/), a robust
  CI/CD platform that enables automation of testing and deployments across
  multiple environments and supports multiple languages and platforms.
{%- elif cookiecutter.use_gitlab_ci == "yes" %}
- **Continuous integration**: we use [_GitLab
  CI/CD_](https://about.gitlab.com/topics/ci-cd/), it helps us to realize the
  vision of software development that is iterative, tested, and always
  releasing. A continuous and iterative process to build, test, and deploy
  helps avoid bugs and code failures.
{%+ endif %}

## Credits

This package was created with
[scicookie](https://github.com/osl-incubator/scicookie) project template.
