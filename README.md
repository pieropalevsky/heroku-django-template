# Heroku Django Starter Template

An utterly fantastic project starter template for Django 1.10.

## Features

- Production-ready configuration for Static Files, Database Settings, Gunicorn, etc.
- Enhancements to Django's static file serving functionality via WhiteNoise.
- Latest Python 3.6 runtime environment. 

## How to Use

To use this project, follow these steps:

1. Create your working environment.
2. Install Django (`$ pip install django`)
3. Create a new project using this template

## Creating Your Project

Using this template to create a new Django app is easy. You can replace ``project_name`` with your desired project name.


    $ django-admin.py startproject --template=https://github.com/pieropalevsky/heroku-django-template/archive/master.zip --name=Procfile project_name
    $ cd project_name 
    $ virtualenv -p python3 venv
    $ source venv/bin/activate 
    $ pip install -r requirements.txt

Then save your SECRET_KEY setting somewhere safe to keep it out of version control. To use it locally save as an environment variable

    $ export SECRET_KEY="SECRET_KEY GOES HERE"

The next step is to point your project at the correct settings file.
    
    $ export DJANGO_SETTINGS_MODULE='project_name.settings.local'

Then set up up your ./manage.py to be executable

    $  chmod u+rwx manage.py
    
To finish setting up locally run

    $ ./manage.py migrate
    $ ./manage.py collectstatic

## Deployment to Heroku

    $ git init
    $ git add -A
    $ git commit -m "Initial commit"

    $ heroku create
    $ git push heroku master

    $ heroku run python manage.py migrate

See also, a [ready-made application](https://github.com/heroku/python-getting-started), ready to deploy.

## Using Python 2.7?

Just update `runtime.txt` to `python-2.7.13` (no trailing spaces or newlines!).


## License: MIT

## Further Reading

- [Gunicorn](https://warehouse.python.org/project/gunicorn/)
- [WhiteNoise](https://warehouse.python.org/project/whitenoise/)
- [dj-database-url](https://warehouse.python.org/project/dj-database-url/)
