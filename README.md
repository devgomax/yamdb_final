# yamdb_final
yamdb_final
## Author: @devgomax

[![Yamdb-app Actions Status](https://github.com/devgomax/yamdb_final/workflows/Yamdb-app/badge.svg)](https://github.com/devgomax/yamdb_final/actions)

### Small website that allows people to rate films, read reviews on it, etc.
### Server deployment instructions:
- create ```.env``` file to the project's root directory with the next lines:
     ```
        DB_ENGINE=django.db.backends.postgresql
        DB_NAME={database name}
        POSTGRES_USER=postgres
        POSTGRES_PASSWORD={create password for db user}
        DB_HOST=db
        DB_PORT=5432
     ```
- create directory ```/static/``` with static files for django
- execute next commands in terminal:
    ```
        docker-compose up -d
        docker-compose exec web python manage.py makemigrations users
        docker-compose exec web python manage.py migrate --noinput
        docker-compose exec web python manage.py makemigrations api
        docker-compose exec web python manage.py migrate --noinput
        docker-compose exec web python manage.py createsuperuser
        docker-compose exec web python manage.py collectstatic --no-input
    ```
  
### That's it! Now your website is available at ```http://127.0.0.1/``` and admin panel at ```/admin/```
- ```docker-compose up -d``` to start project
- ```docker-compose down``` to stop all the working containers
