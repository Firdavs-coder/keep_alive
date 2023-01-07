# keep_alive

```python
from flask import Flask
from threading import Thread
import os

app = Flask("app")

STATIC_DIR = os.path.abspath('static')


@app.route('/')
def main():
  return "Working"


def run():
  app.run("0.0.0.0", port=8080)


def keep_alive():
  server = Thread(target=run)
  server.start()


if __name__ == "__main__":
  keep_alive()

```
