# This is Example Django and React.js (Server side rendering) containerize project
To run this project, 
```
docker-compose up -d
docker-compose up # with real time logging
```
Environment variables: (appear in `.env.example` file)
Before you run you need to create a `.env` file with the environment variables listed below.
```
DEBUG: Set to `true` to enable debug mode. ex: `true`
SECRET_KEY: Set to a long random secret key. ex: `my-secret-key-is-very-lo00000ong`
ALLOWED_HOSTS: Set to a comma-separated list of allowed hosts. ex: `localhost,example.com`
ALLOWED_ORIGINS: Set to a comma-separated list of allowed origins. ex: `http://localhost:3000,https://example.com`
DB_NAME: Set to the name of the database. ex: `mydb`
DB_USER: Set to the database user. ex: `myuser`
DB_PASSWORD: Set to the database password. ex: `mypassword` 
CELERY_BROKER_URL: Set to the Celery broker URL. ex: `redis://localhost:6379/0`
CELERY_RESULT_BACKEND: Set to the Celery result backend URL. ex: `redis://localhost:6379/0`
```
Set superuser credentials:
```
docker exec -it example_django python manage.py createsuperuser
```

_Note: this project is tested on x86_64 architecture and modern version of Docker (>=A.D. 2025)._
