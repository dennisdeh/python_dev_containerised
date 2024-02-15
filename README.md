# Containerised python development with database
#### A simple template to set up a containerised environment with a database using python

The repository contains a Docker compose file to set up a useful containerised python
development environment, that has a database for storing data and information
about various runs (db), an administration api (adminer) to access the databases,
and finally python container (py) where python code can be executed.

### Use cases
Some examples where this repository can come in handy:
- Automated data processing
- python APIs where a database functionality is required
- Home Assistant integrations

Finally, the number of containers can be extended ad infinitum to allow for processing
by other containerised applications.
Persistent data storage of the database can also simply be added, see 
[here for more info](https://mariadb.com/resources/blog/mariadb-and-docker-use-cases-part-1/).

### To develop python programs
A python module called [database.py](c1_python/app/utils/database.py) is included
and allows for easily saving to or loading from the database. Python
files should be put in [c1_python/app](c1_python/app) and will be copied into the container,
with [main.py](c1_python/app/main.py) being run as the default behavior.

### To run
Navigate into the repository in the terminal and type
``
docker compose up
``.

### Additional information
Default usernames, passwords and ports are globally set in the .env file.

Images used for the containers are:
> db: mariadb:latest\
> py: python:3.9-slim (can also be changed to another python stack depending on needs)\
> adminer: adminer:latest
