
# Django Forms

## 1. HTML Forms

Here is a basic HTML form with one text field, a password text field,

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>An example of HTML Form</title>
  </head>
  <body>
    <form>
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
      <label>Travel</label>
    </form>
  </body>
</html>
```

## 2. What is special about Django Form

## 3. Creating Django Form

## 4. Storing the Form data to the database

## 5. Retrieve from database and display in Form

## 6. File upload
