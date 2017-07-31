# Steps
## Install docker-compose
`pip install docker-compose` or use OS providers package distribution.

## Create a Django project
Run `django-admin.py startproject simple-django` in a `web` image.

`docker-compose run web django-admin.py startproject simple_django .`

## Connect the database
Modify `simple_django/settings.py` as follow:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}
```

## Run the service
`docker-compose up`

# Reference
https://docs.docker.com/compose/django/#connect-the-database