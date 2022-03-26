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
      * settings.py
      * urls.py
      * wsgi.py
      * __init__.py
    * manage.py
- Run the project
  * cd first_project
  * python manage.py runserver
