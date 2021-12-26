Heroku Procfile file for Python (Django) :
```
web: gunicorn CrazyCrytoBackend.wsgi:application --log-file - --log-level debug
heroku ps:scale web=1
```
