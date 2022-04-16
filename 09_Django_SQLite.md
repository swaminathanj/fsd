# Django with SQLite

With Django you access database the object way instead of SQL way. This is possible due to Object-Relational Mapper (ORM). You create models which are object representation of the database tables. Once you apply 'migrate' command, tables are automatically created by Django. Once created, the CRUD operations can be performed by accessing the models as object.

Firstly, note that settings.py already has the following entry which set the default database engine to SQLite3. If you are using any other database, this entry will require changes.

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```

## Step 0: Perform unapplied migrations

Before you create models, perform a migration in case there are unapplied migrations. To know if you have unapplied migrations, activate the virtual environment, navigate to project folder (first_project) and run the server. You will know if there are any unapplied migrations.
```
(myenv) PS CMD> python manage.py first_project
You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
```

First apply migration as follows.
```
python manage.py migrate
```

## Step 1: Creating Models

Models are created by extending models.Model class in the models.py file. Let's create two models *Degree* and *Student*.
1. Note that we don't state PRIMARY KEY explicitly. Django adds a unique id by default when you insert values. This serves as the PRIMARY KEY.
2. Degree is specified as the FOREIGN KEY in Students.

```python
from django.db import models

class Degree(models.Model):
    title = models.CharField(max_length=20)
    branch = models.CharField(max_length=50)

class Student(models.Model):
    roll_number = models.CharField(max_length=20)
    name = models.CharField(max_length=50)
    year = models.IntegerField(default=1)
    dob = models.DateTimeField('date of birth')
    degree = models.ForeignKey(Degree, on_delete=models.CASCADE)
```

Now apply the migration as follows. The first command creates migrations for the models or changes to the models. The second command applies them to the database. 
```
(myenv) CMD> python manage.py makemigrations first_app
(myenv) CMD> python manage.py migrate
```

At this point you can check if Degree and Student tables are created in the database. Check this by invoking sqlite at the top-level first_project folder and listing the tables.
```
(myenv) CMD> sqlite3 db.sqlite3
> .tables
```
