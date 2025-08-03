## migrations commands 
--> makemigrations is used to create a script to add the changes to the database
```shell
python manage.py makemigrations
Migrations for 'my_app':
  my_app/migrations/0004_person_age.py
    - Add field age to person
```

--> migrate is used to execute the scripts created by the makemigrations.
```shell
python manage.py migrate
```

--> the showmigrations command is used to list the history of the migration 
```shell
python manage.py showmigrations

my_app
 [X] 0001_initial
 [X] 0002_person
 [ ] 0003_rename_name_person_user_name
 [ ] 0004_person_age
sessions
 [X] 0001_initial
```

--> the sqlmigrate command is used to show the sql query is executed in each migrations 
```shell
 python manage.py sqlmigrate my_app 0001_initial
BEGIN;
--
-- Create model Menu
--
CREATE TABLE "my_app_menu" ("id" integer NOT NULL PRIMARY KEY AUTOINCREMENT, "name" varchar(100) NOT NULL, "cuisine" varchar(100) NOT NULL, "price" integer NOT NULL);
COMMIT;
```


