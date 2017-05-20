# Coding Standards

All GoSource developers will observe the following coding standards

## General


## HTML

Please use coding standards defined for the framework you use. For example, for Bootstrap it means 2 spaces indentation and so on.

## Python

Following [pep8](https://www.python.org/dev/peps/pep-0008/) is strongly recommended. There are plugins for most popular code editors, so you don't have to think about it - the utils like flake8 will show you all problems and explanations.

If you use Django please read [django-specific style guide](https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/)

For repository structure, please follow the guide below unless you have a good reason to do otherwise:

* all python code is in /src/ folder (including manage.py file)
* /src/ folder contains subforder for project named after the project name, so any project-specific app gets imported as import projectname.appname, not impor appname - to avoid global namespace tampering
* any logical domain (devops things, documentation, client scripts, usage examples) goes to separate folder in the root repo.
* root git directory may have docker-compose file for local development, dockerfile and so on. But generally devops things shall be moved to devops/ directory and it's Jenkins job to put files to correct places.

So, for example:

```
devops/
src/
src/manage.py
src/projname/settings/base.py
src/projname/settings/...
src/projname/app1/
src/projname/app2/
src/projname/static/ - global static files
src/projname/app/static/ - app-specific static
README.md
helper scripts
example scripts and env files
docs/ - for RST or any other documentation format
client-sh/ - if app has API and bash clients
client-py/ - if app has API and python clients
...
var/ - gitignore and dockerignored directory
  * for collected static files
  * for local dev media directory
  * for any other files which should not go to main repo
node_modules/
  * if we have node requirements then they will be installed here (because package.json is in this directory as well) and loaded from django directly.
```

## Java


## Javascript


