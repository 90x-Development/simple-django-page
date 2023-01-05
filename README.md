# simple-django-page

First, start a new Django project:

```python
django-admin startproject myproject
```
This will create a new directory called "myproject" with the basic Django files. Next, create a new Django app:

```python
python manage.py startapp myapp
```
This will create a new directory called "myapp" with the basic Django app files.

Next, open the file "myproject/settings.py" and add "myapp" to the list of installed apps:

```python
INSTALLED_APPS = [    ...    'myapp',]
```
Next, create a new view in the file "myapp/views.py":

```python
from django.shortcuts import render

def home(request):
    return render(request, 'myapp/home.html')
```
This view will use Django's render function to render a template called "home.html".

Next, create the template "myapp/templates/myapp/home.html":

```html
<!doctype html>
<html>
  <head>
    <title>My 1st App</title>
    <style>
      h1 {
        color: #333;
        text-align: center;
        margin-top: 50px;
      }
      p {
        font-size: 18px;
        line-height: 1.6;
        width: 60%;
        margin: 0 auto;
        text-align: justify;
      }
    </style>
  </head>
  <body>
    <h1>My 1st App</h1>
    <p>Welcome to my first Django app! This is a simple page with a title and a paragraph of text. I've added some basic CSS styling to make the page look a little bit better. I hope you like it!</p>
  </body>
</html>
```
This template includes a title, some basic CSS styling, and a paragraph of text.

Next, create a new URL pattern in the file "myapp/urls.py":

```python
from django.urls import path

from . import views

urlpatterns = [
    path('', views.home, name='home'),
]
```
This URL pattern will map the root URL of the app to the "home" view.

Finally, include the URL patterns of the app in the project's URL patterns in the file "myproject/urls.py":

```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('myapp/', include('myapp.urls')),
    path('admin/', admin.site.urls),
]
```
Now you can start the development server and visit http://localhost:8000/myapp/ to see the page with the title "My 1st App" and the paragraph of text.

```python
python manage.py runserver
```
I hope this helps! Let me know if you have any questions
