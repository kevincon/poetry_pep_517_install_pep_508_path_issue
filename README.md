If you create a virtual environment and try to `pip install` the `master` branch of this repo into it, it will fail:

```
C:\Users\kdconley\venvs
λ C:\Users\kdconley\AppData\Local\Programs\Python\Python38-32\python.exe -m venv poetry_pep_517_install_pep_508_path_issue

C:\Users\kdconley\venvs
λ poetry_pep_517_install_pep_508_path_issue\Scripts\activate.bat

C:\Users\kdconley\venvs
(poetry_pep_517_install_pep_508_path_issue) λ python -m pip install --upgrade pip
Collecting pip
  Using cached https://files.pythonhosted.org/packages/5a/4a/39400ff9b36e719bdf8f31c99fe1fa7842a42fa77432e584f707a5080063/pip-20.2.2-py2.py3-none-any.whl
Installing collected packages: pip
  Found existing installation: pip 19.2.3
    Uninstalling pip-19.2.3:
      Successfully uninstalled pip-19.2.3
Successfully installed pip-20.2.2

C:\Users\kdconley\venvs
(poetry_pep_517_install_pep_508_path_issue) λ python -V
Python 3.8.3

C:\Users\kdconley\venvs
(poetry_pep_517_install_pep_508_path_issue) λ pip -V
pip 20.2.2 from c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip (python 3.8)

C:\Users\kdconley\venvs
(poetry_pep_517_install_pep_508_path_issue) λ pip install git+ssh://git@github.com/kevincon/poetry_pep_517_install_pep_508_path_issue.git
Collecting git+ssh://****@github.com/kevincon/poetry_pep_517_install_pep_508_path_issue.git
  Cloning ssh://****@github.com/kevincon/poetry_pep_517_install_pep_508_path_issue.git to c:\users\kdconley\appdata\local\temp\pip-req-build-kmt_blio
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
    Preparing wheel metadata ... done
ERROR: Exception:
Traceback (most recent call last):
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 3021, in _dep_map
    return self.__dep_map
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 2815, in __getattr__
    raise AttributeError(attr)
AttributeError: _DistInfoDistribution__dep_map

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 3101, in __init__
    super(Requirement, self).__init__(requirement_string)
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\packaging\requirements.py", line 115, in __init__
    raise InvalidRequirement("Invalid URL: {0}".format(req.url))
pip._vendor.packaging.requirements.InvalidRequirement: Invalid URL: lib\library

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_internal\cli\base_command.py", line 216, in _main
    status = self.run(options, args)
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_internal\cli\req_command.py", line 182, in wrapper
    return func(self, options, args)
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_internal\commands\install.py", line 324, in run
    requirement_set = resolver.resolve(
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_internal\resolution\legacy\resolver.py", line 183, in resolve
    discovered_reqs.extend(self._resolve_one(requirement_set, req))
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_internal\resolution\legacy\resolver.py", line 437, in _resolve_one
    set(req_to_install.extras) - set(dist.extras)
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 2978, in extras
    return [dep for dep in self._dep_map if dep]
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 3023, in _dep_map
    self.__dep_map = self._compute_dependencies()
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 3033, in _compute_dependencies
    reqs.extend(parse_requirements(req))
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 3094, in parse_requirements
    yield Requirement(line)
  File "c:\users\kdconley\venvs\poetry_pep_517_install_pep_508_path_issue\lib\site-packages\pip\_vendor\pkg_resources\__init__.py", line 3103, in __init__
    raise RequirementParseError(str(e))
pip._vendor.pkg_resources.RequirementParseError: Invalid URL: lib\library
```