# read-23 : Django Custom User
# Django Custom User

## Django Best Practices: Custom User Model

### Django ships with a built-in User model for authentication and if you'd like a basic tutorial on how to implement log in, log out, sign up and so on see the Django Login and Logout tutorial for more.

### However, for a real-world project, the official Django documentation highly recommends using a custom user model instead. This provides far more flexibility down the line so, as a general rule, always use a custom user model for all new Django projects.

### But how to implement one? The official documentation example is not actually what many Django experts recommend using. There is a far easier yet still powerful approach to starting off new Django projects with a custom user model which I'll demonstrate here.

## Setup
### To start, create a new Django project from the command line. We need to do several things:

* create and navigate into a dedicated directory called accounts for our code
* install Django
* make a new Django project called django_project
* make a new app accounts
* start the local web server

### Here are the commands to run:

```
# Windows
> cd onedrive\desktop\code
> mkdir pages
> cd pages
> python -m venv .venv
> .venv\Scripts\Activate.ps1
(.venv) > python -m pip install django~=4.0.0
(.venv) > django-admin startproject django_project .
(.venv) > python manage.py startapp accounts
(.venv) > python manage.py runserver

# macOS
% cd ~/desktop/code
% mkdir pages
% cd pages
% python3 -m venv .venv
% source .venv/bin/activate
(.venv) % python3 -m pip install django~=4.0.0
(.venv) % django-admin startproject django_project .
(.venv) % python3 manage.py startapp accounts
(.vent) % python3 manage.py runserver
```

### Note that we did not run migrate to configure our database. It's important to wait until after we've created our new custom user model before doing so.

### If you navigate to http://127.0.0.1:8000 you’ll see the Django welcome screen.

### Sweet. For now, stop the local server with Control+c because otherwise it will start kicking off lots of errors as we implement a custom user model.

## AbstractUser vs AbstractBaseUser
### There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser. In both cases we can subclass them to extend existing functionality however AbstractBaseUser requires much, much more work. Seriously, don't mess with it unless you really know what you're doing. And if you did, you wouldn't be reading this tutorial, would you?

### So we'll use AbstractUser which actually subclasses AbstractBaseUser but provides more default configuration.

# Custom User Model
### Creating our initial custom user model requires four steps:

* update django_project/settings.py
* create a new CustomUser model
* create new UserCreation and UserChangeForm
* update the admin

### In settings.py we'll add the accounts app and use the AUTH_USER_MODEL config to tell Django to use our new custom user model in place of the built-in User model. We'll call our custom user model CustomUser.

### Within INSTALLED_APPS add accounts at the bottom. Then at the bottom of the entire file, add the AUTH_USER_MODEL config.




