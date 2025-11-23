---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-11-23T18:26
---
---

- this is a basic flask server code:
```python
#!/bin/python3

from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
	return "Hello Worlld"

if __name__ == '__main__':
	app.run(host="0.0.0.0", port=5000, debug=True)

```

- here debug is when we are still developing and we want python to restart the server on new changes.
	- we will pass it false when deploying
- `pip3 freeze`: will give in terminal all the installed dependencies
	- `pip3 freeze > requirements.txt` will transfer and write these into requirements.txt
	- `pip3 install -r requirements.txt` will install all the dependencies inside requirements.txt

