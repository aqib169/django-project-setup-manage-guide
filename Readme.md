# Django Project Setup

Follow this guide to set up a Django project and create your first app. This guide is inspired by the following tutorials:
- [Django Project Setup Tutorial 1](https://www.youtube.com/watch?v=3EzKBFc9_MQ&list=PL4cUxeGkcC9iqfAag3a_BKEX1N43uJutw&index=14)
- [Django Project Setup Tutorial 2](https://www.youtube.com/watch?v=aAACOgAHg90&list=PL4cUxeGkcC9iqfAag3a_BKEX1N43uJutw&index=12)
- [Django Project Setup Tutorial 3](https://www.youtube.com/watch?v=6Ctsv9VB8L8&list=PL4cUxeGkcC9iqfAag3a_BKEX1N43uJutw&index=11)

## Prerequisites

Ensure the following are installed on your system:
- **Python**
- **Pip**

## Setting Up the Environment

1. Install `pipenv` for creating a virtual environment:
   ```bash
   pip install pipenv
   ```

2. Activate the virtual environment:
   ```bash
   pipenv shell
   ```

3. Install Django in the virtual environment:
   ```bash
   pipenv install django
   ```

4. Verify the installed modules and frameworks:
   ```bash
   pip freeze
   ```

## Creating the Django Project

1. Create a new Django project:
   ```bash
   django-admin startproject [Project-name]
   ```

2. Navigate to the project directory:
   ```bash
   cd [Project-name]
   ```

3. Create a new Django application within the project:
   ```bash
   python manage.py startapp [Application-name]
   ```

4. Run the development server to verify the setup:
   ```bash
   python manage.py runserver
   ```

## Configuring the App

1. **Add `urls.py` in the app folder:**
   Create a `urls.py` file in the app folder (`[Application-name]`) and add the following content:
   ```python
   from django.urls import path
   from . import views

   # Define the URL patterns for the app
   urlpatterns = [
       path('', views.index, name='index'),
   ]
   ```

2. **Define the view in `views.py`:**
   Update the `views.py` file in the app folder with the following:
   ```python
   from django.http import HttpResponse

   # Create your views here.
   def index(request):
       return HttpResponse("Hello, world. You're at the AsiaToursAgency index.")
   ```

3. **Update the main `urls.py` file:**
   In the main project's `urls.py` file (located in the `[Project-name]` folder), include the app's URLs:
   ```python
   from django.urls import path, include

   urlpatterns = [
       path('admin/', admin.site.urls),
       path('', include('[Application-name].urls')),
   ]
   ```

## Running the Server

Start the Django development server to test your application:
```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000/` in your browser to see the message: "Hello, world. You're at the AsiaToursAgency index."

---

This setup provides a foundation for building Django projects. For more detailed steps, refer to the linked tutorials.
