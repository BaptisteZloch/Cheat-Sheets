# Flask cheat sheet

## Virtual environnement
- Install virtual environnement : `> pip install virtualenv`
- Create virtual environnement : `> python -m venv venv`
- Activate virtual environnement : `> .\venv\Scripts\activate`
- Leaving virtual environnement : `> deactivate`
- Freezing all installed packages of a virtual (or not) environnement : `> pip freeze > requirements.txt`

## Flask commands
- Installing Flask : `> pip install Flask`
- To create a Flask project first create a app.py file then in it add this code :

```py
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello, World!"

if __name__ == '__main__':
    app.run(debug=True)
```

- Running flask project : `flask run`
  
## Tips & tricks
- To add a static folder containing all the css, js, img file add `app = Flask(__name__, static_folder="static")` to app.py file. You also need to create a folder static at the projects's root.
- You can specify for a route the HTTP methods allowed like this `@app.route("/path",methods=["GET","POST"])`
- To create global variable : `app.config['MyVariable'] = value`
- To create dynamic routing you can do it like this :
```py
@app.route('/path/<int:param>')
def realisation(param):
```
- To render template create a folder named templates at the projects's root then add `from flask import Flask, render_template` to app.py and for a route add `return render_template("file.html", param=value)`
- To redirect add add `from flask import Flask, render_template` to app.py, you can redirect to another route like this `return redirect('/otherpath')`
- To programm job you can use APScheduler from flask_apscheduler like this :
```py
from flask_apscheduler import APScheduler

scheduler = APScheduler()
scheduler.init_app(app)
scheduler.start()

...

app.scheduler.add_job(func=function, date=datetime(AAAA/MM/DD),id=unique_id,args=[ARGS_OF_FUNCTION])

```
- To send mails you can use Mail, Message from flask_mail like this :
```py
from flask_mail import Mail, Message

mail = Mail(app)
msg = Message(...)
msg.body = ...
mail.send(msg)
...

app.scheduler.add_job(func=function, date=datetime(AAAA/MM/DD),id=unique_id,args=[ARGS_OF_FUNCTION])

```
- To handle cors use CORS from flask_cors like this : 
```py
from flask_cors import CORS

app = Flask(__name__)
CORS(app,resources=r'/api/v1/*') #Allow CORS
```