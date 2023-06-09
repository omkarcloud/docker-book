---
sidebar_position: 30
---

# Django Dockerfile

Following is a Great Dockerfile for Django, optimized for production environment that serves Django at port 8000.

`Dockerfile`
```Dockerfile
FROM python:3.9
ENV PYTHONBUFFERED 1

COPY requirements.txt .
RUN python -m pip install -r requirements.txt

RUN mkdir app
WORKDIR /app
COPY . /app

CMD gunicorn --workers 3 -b 0.0.0.0:8000 config.wsgi
```

Please make sure to add `gunicorn` as a Python package dependency in your `requirements.txt` file.
`requirements.txt`
```plaintext
gunicorn==19.10.0
```