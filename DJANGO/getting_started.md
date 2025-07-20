
# Getting started

## install virtual environment for django 

```bash
$	python3 -m venv myvenv
```


## dialing with the python server
```bash
$	python3 manage.py runserver # To run the server

$	python3 manage.py makemigrations # To compile the migrations

$	python3 manage.py migrate # To migrate the changes in Database
```

## adding apps 

```bash
python manage.py startapp feed
python manage.py startapp comments
python manage.py startapp comments
```

### --> steps to create a Django project

```bash
# creating a directory
mkdir buildDjango
cd buildDJANGO
#creating virtual environment 
python -m venv first-dg_prjct
#activate the venv
source first-dg-prjct/bin/activate
#install django
pip install django
#start a project
django-admin startproject first_prjct .
python manage.py runserver
```

## ADMIN INTERFACES

--> Django-admin is ready to use command line utility  automatically installed and exist on the system path
--> manage.py is a local version of the Django-admin


















