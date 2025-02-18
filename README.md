# Project Deployment Guide

## Step 1: Ensure Your Project is Ready
Before deploying, make sure your Django project has:

- A requirements.txt file
- A Procfile
- Proper static file handling
- Correct ALLOWED_HOSTS and DEBUG settings in settings.py

##  step 2 :  Create a Procfile
Inside your project folder (same level as manage.py), create a new file named Procfile (without any extension) and add this line:
```sh
web: gunicorn (name_of_the_project).wsgi:application
```
for example :-
  web: gunicorn ExpenseTracker.wsgi:application
This line is added to the Procfile, which tells Render how to start your Django application. Here's what each part means:

web:

This tells Render that this command will run a web service.
Render recognizes "web" as the process responsible for handling web requests.
gunicorn

gunicorn (short for Green Unicorn) is a Python web server for running Django applications in production.
Django comes with a built-in development server (python manage.py runserver), but it is not suitable for production.
Gunicorn is lightweight, fast, and recommended for production.
 ExpenseTracker.wsgi:application

This tells Gunicorn to use Django’s WSGI application (which acts as a bridge between web servers and Django).
 ExpenseTracker – This is your Django project name (the folder that contains settings.py and wsgi.py).
.wsgi – This refers to the wsgi.py file inside your Django project folder.
:application – This is the actual WSGI application object defined in wsgi.py.
