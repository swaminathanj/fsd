
# Django Forms

This builds on the previous topic of Django Models. We will create Forms corresponding to the table created in the last class and update the database. That way, one full cycle of request-process-store-response cycle will be complete.

## 1. HTML Forms

Here is a basic HTML form with one text field, a password text field, a drop-down field with few options, a date field, radiobuttons, checkboxes, a file field, a reset button and a submit button.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Sample Form</title>
  </head>
  <body>
  	<h1>A Sample HTML Form</h1>
    <form action="#" method="post">
      <label>Username</label>
      <input type="text"><br>

      <label>Password</label>
      <input type="password"> <br>

      <label>Age</label>
      <select>
        <option>0 - 18 years</option>
        <option>18 - 40 years</option>
        <option>41 - 65 years</option>
        <option>65+ years</option>
      </select> <br>

      <label for="birthday">Date of Birth</label>
      <input type="date"> <br>

      <label>Gender</label>
      <input type="radio" name="gender">
      <label>Male</label>
      <input type="radio" name="gender">
      <label>Female</label> <br>

      <label>Interests</label>
      <input type="checkbox">
      <label>Sports</label>
      <input type="checkbox">
      <label>Music</label>
      <input type="checkbox">
      <label>Travel</label><br>

      <input type="file"> <br>
      
      <input type="reset">
      <input type="submit" value="Submit">
    </form>
  </body>
</html>
```

For an elaborate overview of HTML forms and hands-on examples, please visit https://www.w3schools.com/html/html_forms.asp.

Once you fill this form and press the Submit button, an action has to happen. The action is defined by the backend. This is where Django comes in.

## 2. What is special about Django Forms?

Django provides its way of creating the form and its fields. Note that Django forms code will eventually be translated into HTML. There are some advantages over the form created by Django instead of using HTML syntax. Constraints and checks on the input can be added and Django automatically creates the necessary code to  perform them. This saves us from writing additional code to do the checks if we were to write the code in HTML.

Now we will see how to create Django form and also how to grab the form values at the backend and process them. 

## 3. Creating Django Form
Let's create a form that corresponds to the database tables that we created in the models namely, *Degree* and *Student*. The idea is that the user loads the form page, keys in the values and submits. The values are transferred over the network and reaches backend. Django processes the request, retrieves these values and then  writes to the database. The high level steps involved are as follows:

1. Create a form template in a html page with placeholder for 'form' variable. 
  - The 'form' variable contains the form fields defined in forms.py
  - The 'form' variable will be injected from views.py
  - Note that the name of html page can be anything but it has to be specified in urls.py
  - The html page must be in "templates" folder
2. Define the form in forms.py under the app folder (first_app).
  - It extends forms.Form class
  - Create the necessary fields
3. Define a function in views.py which 
  - Instantiates the form
  - Retrieves the user typed values from the request
  - Perform one or more actions
    - process the values and/or 
    - inserting to database and/or 
    - redirect to another page
  - Add form to the context for HttpResponse

```html
1. degree.html                                   2. forms.py
          
<form action="/degree/" method="post">           from django import forms
  {% csrf_token %}
    {{ form }}                                   class DegreeForm(forms.Form) :
  <input type="submit" value="Submit">             title = forms.CharField(label='Title', max_length=20)
</form>                                            branch = forms.CharField(label='Branch', max_length=50)
```

```python
3. views.py

from django.http import HttpResponseRedirect
from django.shortcuts import render

from .forms import DegreeForm                   # Relative import from our forms.py using .forms

def get_degree(request):    
  if request.method == 'POST':                  # if this is a POST request we need to process the form data
    form = DegreeForm(request.POST)             # create a form instance and populate it with data from the request:
    if form.is_valid():                         # check whether it's valid:
      title = form.cleaned_data['title']        # retrieve the data in form.cleaned_data as required
      branch = form.cleaned_data['branch']
      
      d = Degree(title=title, branch=branch)    # write to the database
      d.save()
      
      return HttpResponseRedirect('/degree/')   # redirect to a degree page or to new URL: return HttpResponseRedirect('/thanks/')
  else:                                         # if a GET (or any other method) we'll create a blank form
    form = DegreeForm()

    return render(request, 'degree.html', {'form': form})
```

```python
urlpatterns = [
    path('', views.index, name='index'),
    path('admin/', admin.site.urls),
    path('degree/', views.get_degree,  name='degree'),
]
```

## 4. JSON

- Stands for JavaScript Object Notation
- Language independent, text-based, open data interchange format
- Advantages
  - Easy for humans to read and write
  - Easy for machines to parse and generate
- JSON data can be easily converted to JavaScript objects
- Nearly every language has libraries to work with JSON file
- File type: <filename>.json

### Examples

```json
{                          /* Curly braces hold objects */
  "title" : "M.Tech",      /* Data is stored in name-value pairs. */
  "branch" : "CSN"         /* Data is separated by commas */
}
```

Square brackets hold arrays.

```json
{
  "degree" :  [
    { "title" : "M.Tech", "branch" : "CS AI & ML" },
    { "title" : "M.Tech", "branch" : "AI" },
    { "title" : "M.Tech", "branch" : "CSN" },
    { "title" : "M.Tech", "branch" : "WNA" },
    { "title" : "M.Tech", "branch" : "VLSI" }
  ]
}
```
  
## 5. Load, parse JSON file in Python
  

## 6. File upload in Django

We will show how to upload a JSON file, retrieve the values and update the models in bulk manner.

1. In degree.html, add one more form below with a submit button.
2. In forms.py, define another class and add file upload field.
3. In views.py, retrieve the JSON file, parse it, in a loop get each entry and update the Degree Model.

```

```

