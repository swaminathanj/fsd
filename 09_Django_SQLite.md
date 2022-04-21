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
    
    def __str__(self):
        return (self.title, self.branch)

class Student(models.Model):
    roll_number = models.CharField(max_length=20)
    name = models.CharField(max_length=50)
    year = models.IntegerField(default=1)
    dob = models.DateField('date of birth')
    degree = models.ForeignKey(Degree, on_delete=models.CASCADE)
    
    def __str__(self):
        return (self.roll_number, self.name, self.degree)
```

For complete list of Django model fields, check https://www.webforefront.com/django/modeldatatypesandvalidation.html.

## Step 2: Applying migrations to the database

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
You will see *first_app_degree* and *first_app_student* in the list.

## Step 3: Inserting values to models

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
```
>>> s1 = Student(degree=d1, roll_number='AM.EN.P2AML21001', name='Akshay', year=1, dob='2000-12-28')
>>> s1.save()
>>> s2 = Student(degree=d1, roll_number='AM.EN.P2AML21002', name='Amit', year=1, dob='2000-07-16')
>>> s2.save()
>>> s3 = Student(degree=d1, roll_number='AM.EN.P2AML21003', name='Arya', year=1, dob='2000-03-20')
>>> s3.save()
>>> s4 = Student(degree=d1, roll_number='AM.EN.P2AML21004', name='Bhanu', year=1, dob='2000-11-09')
>>> s4.save()
>>> s5 = Student(degree=d2, roll_number='AM.EN.P2CSN21001', name='Albert', year=1, dob='2000-12-28')
>>> s5.save()
>>> s6 = Student(degree=d2, roll_number='AM.EN.P2CSN21003', name='Ananya', year=1, dob='2000-05-18')
>>> s6.save()
>>> s7 = Student(degree=d2, roll_number='AM.EN.P2CSN21004', name='Binu', year=1, dob='2001-01-21')
>>> s7.save()
>>> s8 = Student(degree=d2, roll_number='AM.EN.P2CSN21005', name='Deepa', year=1, dob='1999-02-29')
>>> s8.save()
```

## Step 4: Retreiving values from model
Retrieval methods return a QuerySet that matches the specified fields given as parameters to the methods.

1. To retrieve QuerySet of all values, use &lt;model&gt;.objects.all(). Note that  _ _ str _ _ method ensures model values are printed in a desirable manner.
```python
>>> Degree.objects.all()
>>> Student.objects.all()
```
2.To retrieve a specific value(s) from a model.
```python
>>> Degree.objects.get(id=1)
>>> deg = Degree.objects.get(branch='CSN')
>>> Student.objects.get(degree=deg)
```
3.  To retrieve subset of QuerySet the match the lookup parameters, use filter method.
```python
>>> Degree.objects.filter(id=3)  # retrieves 3rd value of the table
>>> Degree.objects.filter(title='M.Tech')  # retrieves all values with title M.Tech
>>> Degree.objects.filter(branch__startswith='CS')  #retrieves all values with branch starting with CS)
```
4. To retrieve a subset of QuerySet that don't match the lookup parameters, use excluded method.
```python
>>> Degree.objects.exclude(id=3)  # retrieves other than 3rd value of the table
>>> Degree.objects.exclude(title='M.Tech')  # retrieves all values with title not equal to M.Tech
>>> Degree.objects.exclude(branch__startswith='CS')  # retrieves all values with branch not starting with CS
```
5. You can use both fiter and exclude to extract a subset of QuerySet.
```python
>>> q = Course.objects.filter(headline__startswith="M.")
>>> q = q.exclude(branch__icontains="WNA")
```
6. To retrieve values of a given range from the QuerySet, specify the range.
```python
>>> q = Degree.objects.all()
>>> q[1:3]
>>> q[:5]
>>> q.[1:]
```
7. To reverse the values returned, use reverse() method.
```python
>>> q = Degree.objects.all()
>>> q.reverse()
```
8. To retrieve a specific field, specify the field name.
```python
>>> d = Degree.objects.get(id=1)
>>> d.title
```
**Most used retrieval methods**: all(), get(), filter() and exclude().

There are plenty of methods to retrieve different kinds of data from models. Refer to https://docs.djangoproject.com/en/4.0/ref/models/querysets/#queryset-api for complete QuerySet API reference.

## Step 5: Update model values

1. To change the value of a field, title of a model
```python
>>> d = Degree.objects.get(id=1)
>>> d.title = 'M.S.'
>>> d
```
2. To update the value of a foreign key field, 
```python
# To be added
```

## Step 6: Delete values from model

1. To delete a value from a model, use delete method
```python
>>> d = Degree.objects.get(branch='WNA')
>>> d.delete()
>>> Degree.objects.all()
```

2. To delete the value of a foreign key field, 
```python
# To be added
```

## Step 7: Reading table values and displaying in html

Now that we have added some entries into the database from shell, let's read them and display in the html.

1. In views.py, first import the tables.
```python
from first_app.models import Degree, Student
```

2. Down below under index function, retrieve the QuerySet from the database table and store it in a variable.
```python
degree_values = Degree.objects.all()
```

Now all the values of the Degree table is in the python variable degree_values. 
3. Add degree_values to the dictionary.
```python
my_dict = {
        ...,
        ...,
        ...,
        'degree_rows' : degree_values,
    }
```
Note: degree_values is the name of the variable in views.py. This is assigned to 'degree_rows' which will be used in index.html.

4. In index.html create a &lt;table&rt; entry. In a for loop, add the &lt;tr&rt; entries and under each &lt;tr&rt; entry, add &lt;td&rt; entries for every field.
```html
<h3>Degrees offered</h3>

    <table border="1">
      {% for r in degree_rows %}
        <tr>
          <td>{{ r.title }}</td>
          <td>{{ r.branch }}</td>
        </tr>
      {% endfor %}
    </table>
```

5. Run the server and refresh the page.
6. Similarly, read and display Student table. 

## Step 8: Adding methods to model

Apart from the fields and _ _ str _ _ method, there are other methods which can be used. 
* _ _ eq _ _ for checking the equality based on primary key
* _ _ hash _ _ to compute hashcode based on primary key
* _ _ get_absolute_url _ _

You can also define additional methods to perform special computations.
