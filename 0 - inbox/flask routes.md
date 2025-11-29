---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-11-29T13:33
---
---

```python
# default route

@app.route('/') # methods = ['GET'] by default
def index():
	return "Hello World\n"
	
# post route
@app.route("/hello/<name>", methods=['POST'])
def hello1(name):
	return f"hello {name}\n"
	
# get route with url parameters
@app.route("/hello/<name>/<word>")
def hello(name, word):
	return f"Hello {name}, how are you {word}\n"
	
	
```


