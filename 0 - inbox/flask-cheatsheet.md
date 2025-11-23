---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-11-22T17:56
---
---

### Introduction

A comprehensive reference covering essential commands, concepts, patterns, and utilities used in Flask.

---

### Project Setup

- **Install Flask**

```bash
pip install flask
```

- **Check Flask Version**

```bash
python -c "import importlib.metadata; print(importlib.metadata.version('flask'))"
```

- **Create Basic App Structure**

```
project/
	app.py
	templates/
	static/
```

---

### Basic App

```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
	return "Hello, Flask!"

if __name__ == '__main__':
	app.run(debug=True)
```

---

### Routing

- **Basic Route**

```python
@app.route('/about')
def about():
	return "About Page"
```

- **Route with Variables**

```python
@app.route('/user/<username>')
def profile(username):
	return f"User: {username}"
```

- **Type-Specific Variables**

```python
@app.route('/post/<int:id>')
def post(id):
	return f"Post ID: {id}"
```

- **Multiple Methods**

```python
@app.route('/submit', methods=['GET', 'POST'])
def submit():
	...
```

---

### Request Handling

```python
from flask import request

@app.route('/login', methods=['POST'])
def login():
	username = request.form.get('username')
	password = request.form.get('password')
	return f"Logged in as {username}"
```

- **Query Params**

```python
request.args.get('key')
```

- **JSON Body**

```python
data = request.get_json()
```

---

### Response & Status Codes

```python
from flask import make_response, jsonify

@app.route('/json')
def json_res():
	return jsonify({"msg": "Hello"}), 201
```

---

### Templates (Jinja2)

- **Render Template**

```python
from flask import render_template

@app.route('/')
def home():
	return render_template('index.html', title="Home")
```

- **Template Syntax**

```
{{ variable }}
{% for item in items %} ... {% endfor %}
{% if condition %} ... {% endif %}
```

---

### Static Files

- Place inside `static/` folder

```html
<link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
```

---

### Redirects & URLs

```python
from flask import redirect, url_for

@app.route('/go-home')
def go():
	return redirect(url_for('home'))
```

---

### Sessions

```python
from flask import session
app.secret_key = "secret123"

@app.route('/set')
def set():
	session['user'] = 'john'
	return 'Set Session'

@app.route('/get')
def get():
	return session.get('user')
```

---

### Cookies

```python
resp = make_response("Setting cookie")
resp.set_cookie('username', 'john', max_age=3600)
return resp
```

---

### Error Handling

```python
@app.errorhandler(404)
def not_found(e):
	return "Page not found", 404
```

---

### Blueprints

```python
from flask import Blueprint

users = Blueprint('users', __name__)

@users.route('/profile')
def profile():
	return "User Profile"

app.register_blueprint(users, url_prefix='/users')
```

---

### Flask CLI

- **Run App**

```bash
flask run
```

- **Set App Module**

```bash
export FLASK_APP=app.py
```

- **Enable Debug Mode**

```bash
export FLASK_DEBUG=1
```

---

### Environment Variables

```bash
export FLASK_APP=app.py
export FLASK_ENV=development
```

---

### Database (Flask + SQLAlchemy Snippet)

```python
from flask_sqlalchemy import SQLAlchemy

app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///test.db'
db = SQLAlchemy(app)

class User(db.Model):
	id = db.Column(db.Integer, primary_key=True)
	name = db.Column(db.String(80))
```

- **Create DB**

```python
db.create_all()
```

---

### Middleware (Before/After Request)

```python
@app.before_request
def before():
	print("Before request")

@app.after_request
def after(response):
	print("After request")
	return response
```

---

### JSONifying

```python
import json
json.dumps(data)
```

---

### File Uploads

```python
from flask import request

@app.route('/upload', methods=['POST'])
def upload():
	file = request.files['file']
	file.save(f"uploads/{file.filename}")
	return 'Uploaded'
```

---

### Flask Extensions to Know

- Flask-SQLAlchemy
- Flask-Migrate
- Flask-Login
- Flask-WTF
- Flask-RESTful
- Flask-Mail

---

### Deployment (Gunicorn Example)

```bash
gunicorn app:app --bind 0.0.0.0:8000
```

---

### Useful Patterns

- App Factory Pattern
- Blueprint-based structuring
- Using `.env` files for configs
- Jinja2 template inheritance

---

### App Factory Example

```python
def create_app():
	app = Flask(__name__)
	app.register_blueprint(users)
	return app
```

---

End of Cheatsheet.

