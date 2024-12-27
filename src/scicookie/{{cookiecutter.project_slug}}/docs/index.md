![LOGO](/images/logo.png)

{% set is_open_source = cookiecutter.project_license != 'Other' -%}
# {{ cookiecutter.project_name }}

{{ cookiecutter.project_short_description }}

{% if is_open_source -%}
- License: {{ cookiecutter.project_license }}
- Documentation: https://{{ cookiecutter.project_slug }}.github.io
{%- endif %}

## Features

{% if cookiecutter.project_layout == "src" %}
- **Structure of the project**: this project uses the _src (Source) layout_, a
  common approach where the source code files are organized within a dedicated
  "src" directory and typically contains subdirectories that represent
  different modules or packages.
{%- elif cookiecutter.project_layout == "flat" %}
- **Structure of the project**: this project uses the _flat layout_, involves
  placing all the project's source code files directly in the project's root
  directory without any subdirectories.
{%+ endif %}
{% if cookiecutter.build_system == "poetry" %}
- **Build system**: [_Poetry_](https://python-poetry.org/) it's a Python package
  manager that streamlines dependency management and package distribution. With Poetry, you can easily install, update, and remove dependencies, and it
  automatically handles conflicts and resolution between packages.
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
  provides a way to define metadata about your project, such as its name,
  version, dependencies, and other details. It also provides functionality for
  building and distributing packages, creating distribution archives, and
  installing packages with their dependencies.
{%- elif cookiecutter.build_system == "pdm" %}
- **Build system**: [_PDM_](https://pdm.fming.dev/) it's a modern Python package
  and dependency manager supporting the latest PEP standards. It has very
  powerful features, including easy and fast dependency resolution, especially
  for large binary distributions, a PEP 517 compilation backend, PEP 621
  project metadata, a flexible and powerful plugin system.
{%- elif cookiecutter.build_system == "hatch" %}
- **Build system**: [_Hatch_](https://hatch.pypa.io) it's a modern, extensible
  Python project manager. It provides a standardized build system with
  reproducible builds by default, robust environment management with support
  for custom scripts, easy publishing to PyPI or other indexes, version
  management, and configurable project generation with sane defaults.
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
  scripts. It acts as a bridge between the two languages, allowing C++
  algorithms and functionality to be directly called from Python as if they
  were native Python modules.
{%- elif cookiecutter.build_system == "pixi" %}
- **Build system**: [_Pixi_](https://pixi.sh/latest/) is a package manager
  designed to simplify dependency management by creating reproducible
  development environments. Pixi focuses on local environments for specific
  projects, generating automatic lock-files to ensure that the same
  dependencies can be installed across different machines.
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
  documentation. Documentation source files are written in _Markdown_ and
  configured with a single `YAML` file.
  The _Theme_ used is {{ cookiecutter.mkdocs_theme }}
{%- elif cookiecutter.documentation_engine == "sphinx(rst)" %}
- **Documentation engine**: [_Sphinx_](https://www.sphinx-doc.org/en/master/)
  it provides various output formats such as HTML, LaTeX, ePub, Texinfo, manual
  pages, plain text. _Sphinx-rst_ uses the _reStructuredText_ markup language
  by default. The _Theme_ used is: {{ cookiecutter.sphinx_theme }}
{%- elif cookiecutter.documentation_engine == "sphinx(myst)" %}
- **Documentation engine**: [_Sphinx_](https://www.sphinx-doc.org/en/master/)
  it provides various output formats such as HTML, LaTeX, ePub, Texinfo, manual
  pages, plain text. _Sphinx-myst_(Markedly Structured Text - Parser) is a
  Sphinx and Docutils extension to parse MyST, a rich and extensible flavour of
  Markdown for authoring technical and scientific documentation.
  The _Theme_ used is: {{ cookiecutter.sphinx_theme }}
{%- elif cookiecutter.documentation_engine == "jupyter-book" %}
- **Documentation engine**:
[_JupyterBook_](https://jupyterbook.org/en/stable/intro.html) uses Jupyter
notebooks as the basis for creating interactive content. It allows you to
structure and organise the notebooks into a cohesive, navigable book. The
_Theme_ used is: {{ cookiecutter.jupyter_book_theme }}
{%- elif cookiecutter.documentation_engine == "quarto" %}
- **Documentation engine**: [_Quarto_](https://quarto.org/) it offers the
  unique feature of embedding Python code directly into your documentation,
  enabling interactive and dynamic content creation. With Quarto, you can
  easily render your documents in multiple formats such as HTML, PDF, and
  websites, making it convenient for sharing and presenting your work. 
  The _Theme_ used is: {{ cookiecutter.quarto_theme }}
{%+ endif %}
{% if cookiecutter.use_conda == "yes" %}
- **Virtual environment**: this project uses
  [_Conda_](https://docs.conda.io/en/latest/) an open source package and
  environment management system that runs on Windows, MacOS and Linux. It
  quickly installs, runs and updates packages and their dependencies. It also
  makes it easy to create, save, load and switch between environments on your
local machine.
{%- else %}
- **Virtual environment**: this project uses
  [_virtualenv_](https://virtualenv.pypa.io/en/latest/) a tool to create isolated Python environments, a subset of it has been integrated into the standard library under the `venv module`. The `requirements.txt` file allows you to manage the environment.
{%+ endif %}
{% if cookiecutter.use_black == "yes" %}
- **Code formatter**: we use [_Black_](https://black.readthedocs.io), a
  popular code formatter tool for Python that automatically formats code to
  conform to PEP 8 guidelines. It provides a simple and opinionated way to
  format code, making it easy to use.
{%- elif cookiecutter.use_ruff_formatter == "yes" %}
- **Code formatter**: we use [_Ruff_](https://docs.astral.sh/ruff/), a versatile
  tool for Python that offers both linting and auto-formatting capabilities. As
  an auto-formatter, Ruff ensures consistent code formatting, fixes import
  sorting, and adheres to best practices. Notably, Ruff is significantly faster
  than tools like Black, making it ideal for large codebases.
{%- elif cookiecutter.use_prettier == "yes" %}
- **Code formatter**: we use [_Prettier_](https://prettier.io/docs/en/), an
  opinionated code formatter that removes all original styling and ensures that
  all output code conforms to a consistent style. Prettier takes the code and
  reprints it from scratch taking line length into account.
{%+ endif %}
{%- if cookiecutter.use_bandit == "yes" %}
- **The security of our code**: _Bandit_ is a powerful tool that we use in our Python
  project to ensure its security. This tool analyzes the code and detects
  potential vulnerabilities. Some of the key features of Bandit are its ease of
  use, its ability to integrate with other tools, and its support for multiple
  Python versions. If you want to know about bandit you can check its
  [documentation](https://bandit.readthedocs.io/en/latest/).
{%+ endif -%}
{%- if cookiecutter.use_coverage == "yes" %}
- **Code coverage testing**: [_Coverage_](https://coverage.readthedocs.io/)
  it's an open source tool for measuring the code coverage of a program. This
  means that it measures what percentage of the program code was executed when
  the tests were run. Coverage can be useful for identifying parts of the code
  that are not being tested and may be vulnerable to bugs.
{%+ endif -%}
{%- if cookiecutter.use_flake8 == "yes" %}
- **Code style**: we use [_Flake8_](https://flake8.pycqa.org/), a tool that
  helps you find potential performance issues in your code. Flake8 can detect
  errors in syntax, indentation, naming conventions, and other types of style
  errors. Enforces coding style conventions defined in the Python
  Enhancement Proposal 8 (PEP 8).
{%+ endif -%}
{%- if cookiecutter.use_ruff_linter == "yes" %}
- This project uses [_Ruff_](https://docs.astral.sh/ruff/), an extremely fast
  Python _linter_ written in Rust. Ruff is designed to perform the process of
  inspecting code for potential bugs or style problems quickly and efficiently.
  It is particularly useful for large code bases where traditional Python
  linters can be slow and resource-intensive.
{%+ endif -%}
{%- if cookiecutter.use_isort == "yes" %}
- **Code separation**: we use [_isort_](https://pycqa.github.io/isort/) a
  Python utility/library for automatically sorting imports alphabetically and
  separating them into sections and by type. This can help maintain a
  consistent import style and make the code easier to read.
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
Python code that may be difficult to maintain or understand. By identifying
complex code at the outset, we as developers can refactor it to make it easier
to maintain and understand. In summary, McCabe helps us to improve the quality
of our code and make it easier to maintain. If you would like to learn more
about McCabe and code complexity, you can visit [McCabe - Code Complexity
Checker](https://here-be-pythons.readthedocs.io/en/latest/python/mccabe.html).
This tool is included with [Flake8](https://flake8.pycqa.org/en/latest/).
{%+ endif -%}
{%- if cookiecutter.use_mypy == "yes" %}
- This package uses [_mypy_](https://mypy.readthedocs.io/en/stable/) as a
  _static type checker_ in the code, so it finds errors in the programs without
  even executing them. It helps to ensure that we are using variables and
  functions correctly in the code.
{%+ endif -%}
{%- if cookiecutter.use_pytest == "yes" %}
- **Test library**: in this project we performed the test with
  [_Pytest_](https://docs.pytest.org/en/), a popular testing framework for
  Python. With Pytest, you can automatically discover and collect test cases,
  use fixtures for test setup and resource management, and write test functions
  with assert statements to check expected outcomes.
{%- elif cookiecutter.use_hypothesis == "yes" %}
- **Test library**: in this project we performed the test with
  [_Hypothesis_](https://hypothesis.readthedocs.io/) a property-based testing
  library for Python. It focuses on generating diverse input data and exploring
  different scenarios to thoroughly test code. Instead of relying on specific
  examples, Hypothesis allows you to define general properties that your code
  should satisfy.
{%+ endif -%}
{%- if cookiecutter.use_shellcheck == "yes" %}
- **Static analysis of shell scripts**: we use
  [_ShellCheck_](https://github.com/koalaman/shellcheck), a static analysis
  tool for shell scripts. It checks shell scripts for common errors and
  potential bugs, such as syntax errors, variable misuse, and command
  substitution issues. Shellcheck supports various shells, including Bash,
  Dash, and Zsh, and it can be integrated into various text editors and IDEs.
{%+ endif -%}
{%- if cookiecutter.use_pre_commit == "yes" %}
- **Pre-commit verification**: this project uses
  [_pre-commit_](https://pre-commit.com/) a framework for managing and
  maintaining multi-language pre-commit hooks. A list of desired hooks must be
  specified, and pre-commit manages the installation and execution of all hooks
  written in any language before each commit. You will be notified before the
  end of the commit if validation fails, as configured.
{%+ endif -%}
{%- if cookiecutter.use_containers == 'Docker' %}
- **Integration with DevOps tools**: we use _Docker_ because it allows us to create an
  isolated environment for our application that includes all the necessary
  dependencies, libraries and configurations. This makes it easier to manage and
  reproduce our development and production environments without any conflicts or
  inconsistencies.
  With Docker, we can easily share our application with others and deploy it to
  different environments. This streamlines our development, testing, deployment,
  and collaboration workflows, making the entire process more efficient.
{%- elif cookiecutter.use_containers == 'Podman' %}
- **Integration with DevOps tools**: we use  _Podman_ in our Python project
  because it helps us achieve a more secure, efficient, and flexible
  containerization strategy, and give us more control over application's
  dependencies and configurations. Podman allows us to manage containers
  without the need for a daemon, providing a more secure and lightweight
  solution. With Podman, we can easily create and run containers, as well as
  manage their lifecycle and resources. This integration has improved our
  development and deployment processes, making them more efficient and
  streamlined.
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
  compiling code and building projects. It automates the process, intelligently
  rebuilding only changed components, streamlining software development
  workflows.
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
  CI/CD_](https://about.gitlab.com/topics/ci-cd/), helps you realize the vision
  of software development that is iterative, tested, and always releasing. A
  continuous and iterative process to build, test, and deploy helps avoid bugs
  and code failures.
{%+ endif %}

## Credits

This package was created with Cookiecutter and the
[osl-incubator/scicookie](https://github.com/osl-incubator/scicookie) project
template.
