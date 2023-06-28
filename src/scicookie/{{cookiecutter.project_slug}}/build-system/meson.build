project(
  '{{ cookiecutter.project_slug }}',
  'python',
  version = '{{ cookiecutter.project_version }}'  # semantic-release
  license: '{{ cookiecutter.project_license }}',
  meson_version: '>= 0.64.0',
)
name = '{{ cookiecutter.project_slug }}'

py_mod = import('python')
py = py_mod.find_installation(pure: false)

py.extension_module(
    ''{{ cookiecutter.package_slug }}',
    '{{ cookiecutter.package_slug }}.py',
    install: true,
)

{% if cookiecutter.project_layout == "src" -%}
install_subdir('src' / name, install_dir: py.get_install_dir() / name)
{%- else %}
install_subdir(name, install_dir: py.get_install_dir() / name)
{%- endif %}
