# Readings: Django REST Framework & Docker

### Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework. It always must be added to a project after Django itself has been installed and configured.

### In this chapter, we will review the similarities and differences between traditional Django and Django REST Framework. The most important takeaway is that Django creates websites containing webpages, while Django REST Framework creates web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON.

### To illustrate these concepts, we will build out a basic Library website with traditional Django and then extend it into a web API with Django REST Framework.

# Traditional Django
### Navigate to the existing `code` directory on the Desktop and make sure you are not in a current virtual environment. You should not see `(.venv)` before the shell prompt. If you do, use the command `deactivate` to leave it. Make a new directory called `library`, create a new virtual environment, activate it, and install Django.

```
# Windows
> cd onedrive\desktop\code
> mkdir library
> cd library
> python -m venv .venv
> .venv\Scripts\Activate.ps1
(.venv) > python -m pip install django~=4.0.0

# macOS
% cd desktop/desktop/code
% mkdir library
% cd library
% python3 -m venv .venv
% source .venv/bin/activate
(.venv) % python3 -m pip install django~=4.0.0
```

### A traditional Django website consists of a single project with multiple apps representing discrete functionality. Let’s create a new project with the `startproject` command called `django_project`. Don’t forget to include the period . at the end which installs the code in our current directory. If you do not include the period, Django will create an additional directory by default.

```
(.venv) > django-admin startproject django_project .
```
### Pause for a moment to examine the default project structure Django has provided for us. You examine this visually if you like by opening the new directory with your mouse on the Desktop. The `.venv` directory may not be initially visible because it is “hidden” but nonetheless still there.


```
├── django_project
│   ├── __init__.py
|   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── manage.py
└── .venv/
```
### The .venv directory was created with our virtual environment but Django has added a django_project directory and a manage.py file. Within django_project are five new files:


* `__init__.py` indicates that the files in the folder are part of a Python package. Without this file, we cannot import files from another directory which we will be doing a lot of in Django!
* `asgi.py` allows for an optional `Asynchronous Server Gateway Interface` to be run
* `settings.py` controls our Django project’s overall settings
* `urls.py` tells Django which pages to build in response to a browser or URL request
* `wsgi.py` stands for Web `Server Gateway Interface` which helps Django serve our eventual web pages.
The manage.py file is not part of django_project but is used to execute various Django commands such as running the local web server or creating a new app. Let’s use it now with migrate to sync the database with Django’s default settings and start up the local Django web server with runserver.

```
(.venv) > python manage.py migrate
(.venv) > python manage.py runserver
```

Open a web browser to `http://127.0.0.1:8000/` to confirm our project is successfully installed and running.




