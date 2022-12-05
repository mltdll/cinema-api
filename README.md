# cinema-api

A simple service providing REST API for a cinema. Written in Python using
Django REST Framework.

## Installation
### Prerequisites
* Python 3.10+ 
* Docker

### Steps to install
1. Clone the repository: `git clone https://github.com/mltdll/cinema-api.git`
2. Change the directory: `cd cinema-api`
   3. Set environment variables for credentials of the database to be created:
       * `DB_NAME`: Name of the database;
       * `DB_USER`: Name of the user;
       * `DB_PASSWORD`: Password for the database access;
       * `DJANGO_SECREET_KEY`: Secret key for your Django application.

       You can create a `.env` file in the root directory of the project 
       (as in `.env.example` file) or just set these variables in the 
       console; that way they will only persist until the console is closed:
       ```shell
       export DB_NAME=example_db
       export DB_USER=example_user
       export DB_PASSWORD=example_password
       export DJANGO_SECRET_KEY=example_key
       ```
       Syntax may vary depending on your operational system.
4. Run the docker containers: `docker-compose up`
5. Create superuser: 
    1. Get id of the docker container to access: `docker ps`
    2. Using this id, open the shell in the container: `docker exec -id <id> sh`
    3. Create superuser: `python manage.py createsuperuser`
    4. Provide the required credentials.
6. Read the documentation at `/api/docs/swagger/` or login at `/api/user/token/`

## Features
* With admin access, create genres, actors, cinema halls, movies;
* Use those to create movie sessions;
* With user access, order tickets for movie sessions and view the history of your orders.