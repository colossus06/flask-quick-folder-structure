# flask-quick-folder-structure

![image](https://user-images.githubusercontent.com/96833570/196004000-00699ab4-046f-4097-8b2e-7adcf74ef4c5.png)


## run.py

```
from app import app

if __name__=="__main__":
    app.run(debug=True)
```
or//

```
from app import app
from livereload import Server


if __name__=="__main__":
    server = Server(app.wsgi_app)
    server.serve()
```

## `app/__init__.py`

```
from flask import Flask

app=Flask(__name__)

from app import admin_views, views
```

## app/views.py

```
from app import app
from flask import render_template


@app.route("/")

@app.route("/home")
def index():
    return render_template('public/home.html')

@app.route("/about")
def about():
    return render_template('public/about.html')
```

## app/admin_views.py

```
from app import app
from flask import render_template


@app.route("/admin/dashboard")
def admin_dashboard():
    return render_template("admin/dashboard.html")

@app.route("/admin/profile")
def admin_profile():
    return render_template("admin/profile.html")
```


# Static Directory Structure

![image](https://user-images.githubusercontent.com/96833570/196004115-2dedab5c-ff44-487f-9a79-94f3b07fc600.png)
