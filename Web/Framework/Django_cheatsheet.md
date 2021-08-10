# Django cheat sheet

## Virtual environnement
- Install virtual environnement : `> pip install virtualenv`
- Create virtual environnement : `> python -m venv venv`
- Activate virtual environnement : `> .\venv\Scripts\activate`
- Leaving virtual environnement : `> deactivate`
- Freezing all installed packages of a virtual (or not) environnement : `> pip freeze > requirements.txt`

## Django commands
- Installing Django : `pip install Django`
- Creating Django project : `django-admin startproject PROJECT_NAME`
- Creating app in a Django project : `python manage.py startapp APP_NAME` **note : always create a urls.py file into the app folder** then add `APP_NAME.apps.APP_NAMEConfig` in INSTALLED_APPS.
- Creating superuser : `python manage.py createsuperuser` then to use the admin side add this to the urls.py file of the project :
```py
from django.contrib import admin
...

urlpatterns = [
    ...
    path('admin/', admin.site.urls)
    ...
]
```
- Migrations :
	- Make migrations : `python manage.py makemigrations` for an app `python manage.py makemigrations APP_NAME`
	- Execute migrations : `python manage.py migrate` for an app `python manage.py migrate APP_NAME`
- Starting server : `python manage.py runserver`

## Tips & tricks
- Create static folder at the project's root for .css, .js, img file... then add this code to the settings.py file : 
```py
STATIC_URL = '/static/'
STATICFILES_DIRS = (str(BASE_DIR.joinpath('static')),)
```
- Create a template folder at the project's root for all HTML template then add this to the settings.py file :
```py
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```
And to render a template add `from django.shortcuts import render` to the views.py file.
- Create a media folder at the project's root for the uploaded file from the admin part. then add this code to the settings.py file :
```py
MEDIA_URL = 'media/'
MEDIA_ROOT = os.path.join(BASE_DIR,'media')
```
And to handle media you need to add this code to the urls.py of the project :
```py
from django.conf.urls.static import static
from django.conf import settings
urlpatterns = [
    ...
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```
- In settings.py in INSTALLED_APPS add : `django_cleanup.apps.CleanupConfig` to clean file when deleting records in the admin part
- To run django from another in your LAN you can add an IP adress in the allowed hosts list in settings.py
- To include another URL conf from another app in your project add `from django.urls import path,include` an use it like this `path('APP_NAME_DOMAIN/', include('APP_NAME.urls')),`
