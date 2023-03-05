# SAMPLE VERSION OF TODO APP
This app is written in Python with Flask and SQLAlchemy, as a part of the Udacity's Full Stack Web Developer Nanodegree program.

## Demo
<img width="351" alt="image" src="https://user-images.githubusercontent.com/15206083/222968879-3838b171-50fd-4631-8e38-bbf9ff70f82a.png">

## A. Dependency
In order to run this app, the following dependencies must have been already installed:
1. Postgres. 
 * Start manually: `pg_ctl -D /usr/local/var/postgres start`
 * Stop manually: `pg_ctl -D /usr/local/var/postgres stop -s -m fast`
 
2. Flask

## B. Database
![image](https://user-images.githubusercontent.com/15206083/222969023-04f50437-58da-40c8-8e06-236a5615bdbb.png)

The database relations `todos(id, description, complete, list_id)` and `todolists(id, name)` must have been already created in Postgres. We have assumed that the Postgres is running on default port 5432.

* `dropdb todoapp -p 5432 && createdb todoapp -p 5432` 
* Open the database prompt - `psql -p 5432`
* Connect to the database - `\c todoapp` 
* Displays the tables in the database `\dt` 
* Displays the schema of the 'todos' table `\d todos` 
* Displays the schema of the 'todolists' table `\d todolists` 

You can insert a few rows in both the tables. Insert first in the `todolists` relation. 

## C. Steps to Run the App:

First of all locate to app directory using: `cd todoapp`

### 1. Setting up the virtual environment for Pyhton
* `python3 -m venv env` set the virtual environment for Pyhton 
* `source env/bin/activate` activate the venv

## 2. Intall dependencies
* `python -m pip install -r requirements.txt` to install dependencies. For Mac users, if you face difficulty in installing the `psycopg2`, you may consider intalling the `sudo brew install libpq` before running the `requirement.txt`. 

## 3. Setting up for database
* `flask db init` to create the migrations directory structure
* `dropdb todoapp` if you already have it
* `createdb todoapp`
* `flask db migrate` (Detects the model changes to be made and creates a migration file with upgrade and downgrade logic setup.
* Using `flask db uprade` when you want to commit your changes to database
* Using `flask db migrate` when you want to rollback the changes.

## 4. Running
* `export FLASK_APP=app.py`
* `export FLASK_DEBUG=true`
* Then `flask run` to run the app (http://127.0.0.1:5000/ or http://localhost:5000)
* `deactivate` de-activate the virtual environment
