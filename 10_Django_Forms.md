
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

For an elaborate overview of HTML forms, please visit https://www.w3schools.com/html/html_forms.asp.

Once you fill this form and press the Submit button, an action has to happen. The action is defined by the backend. This is where Django comes in.

## 2. What is special about Django Form?

Django also provides its way of creating the form and its fields. This has some advantages over the form created by HTML syntax. Constraints and checks on the input can be added and Django warns the user if they are not satisfied. This saves us from writing additional code to do the checks.

Now we will see how to create Django form and also how to grab the form values at the backend and process them. 

## 3. Creating Django Form
Let's create a form that corresponds to the database tables that we created in the models namely, *Degree* and *Student*. The idea is that the user keys in the values which can be written to the database.

All Django Forms extend the class forms.Form class. The form fields are created using the Django Forms API. 

a. Create forms.py inside the app folder (first_app)
b. Import forms from django
c. Create a class for Degree (DegreeForm)
```python
from  django import forms

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

## 4. Storing the Form data to the database

## 5. Retrieve from database and display in Form

## 6. File upload
