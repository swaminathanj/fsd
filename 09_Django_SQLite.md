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
(myenv) CMD> python manage.py first_project
You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
```

First apply migration as follows.
```
(myenv) CMD> python manage.py migrate
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

## Step 2: Inserting values to models

**NOTE**: In this module, we will show how to perform model operations from Django Shell. In the next module, we will introduce Forms and show how to receive value from the user at front-end and insert into the model. At a later stage, we will show how to receive user uploaded file, parse them and insert the values.

1. Open the Django shell. It is basically a Python shell with Django environment.
```
(myenv) CMD> python manage.py shell
```

2. Import the models we migrated, namely Degree and Student.
```python
>>> from first_app.models import Degree, Student
```

3. Insert values into Degree and save.
```python
>>> d1 = Degree(title='M.Tech', branch='CS AI & ML')
>>> d1.save()
>>> d2 = Degree(title='M.Tech', branch='CSN')
>>> d2.save()
>>> d3 = Degree(title='M.Tech', branch='AI')
>>> d3.save()
>>> d4 = Degree(title='M.Tech', branch='WNA')
>>> d4.save()
```

4. Similarly, insert value to Student and save. Note that you cannot add Student with degree other than those added to Degree.

## Step 3: Retreiving values from model

1. To retrieve all values use &lt;model&rt;.objects.all(). Define  _ _ str _ _ method in the model to print in a desirable value.
```python
>>> Degree.objects.all()
```
2. To retrieve value matching a particular field, use filter method.
```python
>>> Degree.objects.filter(id=3)  # retrieves 3rd value of the table
>>> Degree.objects.filter(title='M.Tech')  # retrieves all values with title M.Tech
>>> Degree.objects.filter(branch__startswith='CS')  #retrieves all values with branch starting with CS)
```
3. Retrieve can also be done using get method
```python
>>> Degree.objects.get(id=1)
```
4. To retrieve a specific field
```python
>>> d = Degree.objects.get(id=1)
>>> d.title
```

## Step 4: Update values of model

1. To change the title of a model
```python
>>> d = Degree.objects.get(id=1)
>>> d.title = 'M.E.'
>>> d
```
