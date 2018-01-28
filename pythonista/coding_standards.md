# Python Coding Standards

The purpose of having python coding standards:

 * avoid the problems that come with lack of coding standards (difficulty caused by inconsistency, etc)
 * encourage some desirable qualities in the code (readability etc)

That may seem obvious, but note that it's not about "having an opinion about what's best (and being right)". There are many good ways to do it, and this one is ours.

## PEP8

[pep8](https://www.python.org/dev/peps/pep-0008/) can be a pain - it's very fussy, and for that reason some people don't like it. If we follow PEP8, then we completely avoid the problems that come from a lack of coding standards; however it does not ensure optimal readability.

Another interesting thing about PEP8 is that it is convenient for us to automatically check against it in our CI/CD processes (using flake8 - you are encourage to use it locally too). This reduces the human compliance workload during code reviews. This is a very good thing, and for this reason we always use PEP8. If you want to violate PEP8 in some place for some good reason that's OK (do it, violating PEP8 is not a crime), but you will have to use the # NOQA tag in that place to get your code deployed.

## Django Coding Standards

For django projects, developers should be aware of the [django style guide](https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/) and consider it an important guideline. You can deviate from it in places, if you have a good reason to. But frequent deviation is considered a "bad smell" - really, you should mostly follow it most of the time. 

We do not currently have a convenient way to test Django Coding Standards into our CI/CD pipeline, so voilations are not considerd bugs (yes, we are aware of [django-lint](https://chris-lamb.co.uk/projects/django-lint) but have not integrated it into our process, yet).


# Repository Structure

We use a very particular repository structure because it is part of our CI/CD configuration management methodology. Sometime initial prototypes are not laid out this way, but eventually everything that needs to be deployed will need to be laid out this way.

TODO: link to a CI/CD page explaining file system layout (and more)

Note that for python code, that you will always need:

 * a `manage.py` that behaves like a django manage.py file.
   TODO: link to the flask wrapper boilerplate.
 * a package named after the product, so any product-specific app gets
   imported as import productname.appname (not import appname) - to keep
   the global namespace clean
 * any logical domain (devops things, documentation, client scripts,
   usage examples) goes to separate folder adjacent to the product
   package

Sometime it's also good to have a `docker-compose.yaml` that will run up the system for local development (with Dockerfile etc). 
