Aum Amma

## Installing Django

Please ensure python3 and pip are installed, if not already installed.

To install on Windows, go to https://docs.djangoproject.com/en/4.0/howto/windows/
- Open Command prompt
- Upgrade pip
  > python -m pip install --upgrade pip <br>
- Navigate to a folder where you want to create a project
  > cd D:\Swaminathan\django <br>
- Create a virtual environment
  > python -m venv myenv <br>
- Change directory to the virtual environment and examine the contents
  > cd myenv <br>
  > dir <br>
  * Include/
  * Lib/
  * pyveng.cfg
  * Scripts
- Activate the virtual environment
  > myenv\Scripts\activate <br>
- Once activated, the venv name should show up in the prompt. i.e. (myenv) 
  > Eg. (myenv) D:\Swaminathan\Learn\django> <br>
- Install Django
  > python -m pip install Django <br>
- Verify you Django installation
  > django-admin --version <br>
- Start a new project
  > django-admin startproject first_project <br>
- Check the contents of the first_project
  * first_project
    * first_project
      * asgi.py
      * settings.py  - To store all project settings
      * urls.py  - To store all url patters for the project (basically different pages of the web app - use regexp)
      * wsgi.py - Acts as the Web Server Gateway Interface to deploy the web app to production
      * _ _init_ _.py  - Lets Python know this directory can be treated as a package
    * manage.py  - Associated with many of the things that we do with the project
- Run the project
  > cd first_project <br>
  > python manage.py runserver <br>
- Check the working of the project
  * Open the browser
  * Type the url http://127.0.0.1:8000/

# Creating a Django Application

A Django application is a part of your web application which does a particular functionality. A django app can be reused by plugging into another django project.

* Navigate to first_project directory (top folder of the django project)
  > python manage.py startapp first_app
* The folder structure looks as follows
  * db.sqlite3
  * first_app/
    * admin.py  - To register your models here. Django will then use the models with admin interface
    * apps.py  - To specify app configurations
    * migrations/  - To store database related information 
    * models.py  - To store app's data models
    * tests.py  - Functions to test your code
    * views.py  - Functions to handle requests and return responses 
    * _ _init_ _.py  - Same purpose. This directory can be treated as a package
  * first_project/
* Open settings.py in the project folder (first_project)
* Scroll down to INSTALLED_APPS list
* Add first_app to the list
* Start the project again
* Run the project
  > python manage.py runserver <br>
* Check the working of the project
  * Open the browser
  * Type the url http://127.0.0.1:8000/ 
* Stop the server
* Open views.py in the first_app folder
* Add the following code below the existing code and save
``` python
from django.http import HttpResponse

def index(request) :    # 'request' name is convention. It can be some other name too.
    return HttpResponse("Hello World")
```
* Note: Each view must return an HttpResponse object
* Now, map this view to the urls.py file in project folder
* Open urls.py
* Add the following statement above urlpatterns list
```python
from first_app import views
```
* Add the following to urlpatterns list (it uses regexp)
```
urlpatterns = [
    path(r'^$', views.index, name='index'),
    path('admin/', admin.site.urls),
]
```
