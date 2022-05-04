
# Django Forms

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

## 2. What is special about Django Form?

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
  - Perform an action - copying to database or process the values or redirect to another page
  - Add form to the context for HttpResponse

```
          1. degree.html                                     2. forms.py
          
<form action="/degree/" method="post">           from django import forms
  {% csrf_token %}
    {{ form }}                                   class DegreeForm(forms.Form) :
  <input type="submit" value="Submit">             degree = forms.CharField(label='Degree', max_length=20)
</form>                                            branch = forms.CharField(label='Branch', max_length=50)
```

<table>
  <tr>
    <td>
    &lt;form action="/degree/" method="post"&gt;
      {% csrf_token %}
        {{ form }}
      &lt;input type="submit" value="Submit"&gt;
    &lt;/form&gt;
    </td>
    <td>
       ```python
      
      ```
    </td>
    <td>
       ```python
      
      ```
    </td>
  </tr> 
</table>

All Django Forms extend the class forms.Form class. The form fields are created using the Django Forms API. 

a. Create forms.py inside the app folder (first_app)
b. Import forms from django
c. Create a class for Degree (DegreeForm)
```python
from django import forms

class DegreeForm(forms.Form) :
  degree = forms.CharField(label='Degree', max_length=20)
  branch = forms.CharField(label='Branch', max_length=50)
```

This eventually creates the following HTML code.
```html
<label for="degree">Degree: </label>
<input id="degree" type="text" name="degree" maxlength="20" required>
<label for="branch">Branch: </label>
<input id="branch" type="text" name="branch" maxlength="50" required>
```
Note: This does not provide &lt;form&gt; tags. This has to provided by us in the html file in templates folder.

d. Define a method in views.py to instantiate the form
```python
from django.http import HttpResponseRedirect
from django.shortcuts import render

from .forms import DegreeForm

def get_degree(request):
    # if this is a POST request we need to process the form data
    if request.method == 'POST':
        # create a form instance and populate it with data from the request:
        form = DegreeForm(request.POST)
        # check whether it's valid:
        if form.is_valid():
            # process the data in form.cleaned_data as required
            degree = form.cleaned_data['degree']
            branch = form.cleaned_data['branch']
            # Add the logic to write to the database
            
            # redirect to a new URL:
            return HttpResponseRedirect('/thanks/')

    # if a GET (or any other method) we'll create a blank form
    else:
        form = DegreeForm()

    return render(request, 'degree.html', {'form': form})
```
e. Let's now create degree.html in template folder
```html
<form action="/degree/" method="post">
    {% csrf_token %}
    {{ form }}
    <input type="submit" value="Submit">
</form>
```
f. Add degree.html to urls.py

## 4. Storing the Form data to the database

## 5. Retrieve from database and display in Form

## 6. File upload
