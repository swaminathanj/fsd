# Django Deployment

The instructions to deploy in www.pythonanywhere.com is provided below.

## Move your code to GitHub repository

## Clone your code from GitHub to pythonanywhere

## 

![](deploy/0.png)

### 1. Setting the path to project source code
Navigate in the bash prompt to confirm the exact location.

![Setting the path to project source code](deploy/1.png)

### 2. Setting the path to virtual environment
Navigate in the bash prompt to confirm the exact location.

![Setting the path to virtual environment](deploy/2.png)

Here is how you can navigate to the virtual environment.
![](deploy/files-1.png)

Note that, this is a linux box and you need a different command to create the virtual environment.
> mkvirtualenv --python=/usr/bin/python3.8 mysite-virtualenv

### 3. Creating a new Web app using manual configuration
Don't use Django. Use manual configuration.

![Use manual configuration](manual.png)

### 4. Modifying the wsgi.py with project path and add to environment settings
This is the most important file from the deployment standpoint.

![Modifying the wsgi.py with project path and environment settings](deploy/wsgi.png)
