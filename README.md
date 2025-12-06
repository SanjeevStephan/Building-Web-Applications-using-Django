# Building-Web-Applications-using-Django
Contains code for the web applications built using django web framework

Perfect question, Sam — let’s go step by step so you (and your students) can get Django up and running from scratch.  

---

## 🛠 Step 1: Install Python
- Django requires Python (3.10+ recommended).  
- Check version:
  ```bash
  python --version
  ```
- If not installed, download from [python.org](https://www.python.org).

---

## 📦 Step 2: Create a Virtual Environment
It’s best practice to isolate your project dependencies.

```bash
# Create a folder for your project
mkdir myproject && cd myproject

# Create virtual environment
python -m venv venv

# Activate it
# Windows (cmd)
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
```

---

## 📥 Step 3: Install Django
Inside the activated environment:

```bash
pip install django
```

Verify installation:
```bash
django-admin --version
```

---

## 🚀 Step 4: Create a Django Project
```bash
django-admin startproject mysite
cd mysite
```

Folder structure:
```
mysite/
├── manage.py
└── mysite/
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```

---

## 🖥 Step 5: Run the Development Server
```bash
python manage.py runserver
```

Output:
```
Starting development server at http://127.0.0.1:8000/
```

Open browser → `http://127.0.0.1:8000` → Django welcome page 🎉

---

## 🧩 Step 6: Create an App
Apps are modules inside your project.

```bash
python manage.py startapp blog
```

Folder structure:
```
blog/
├── admin.py
├── apps.py
├── models.py
├── views.py
├── templates/
└── static/
```

Register the app in `mysite/settings.py`:
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'blog',   # <-- add this
]
```

---

## 📝 Step 7: Add a View and URL
In `blog/views.py`:
```python
from django.http import HttpResponse

def home(request):
    return HttpResponse("Hello, Django!")
```

In `mysite/urls.py`:
```python
from django.contrib import admin
from django.urls import path
from blog import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.home, name='home'),
]
```

Run again:
```bash
python manage.py runserver
```
Visit → `http://127.0.0.1:8000` → shows **Hello, Django!**

---

## ✅ Quick Recap
1. Install Python & Django.  
2. Create virtual environment.  
3. Start project (`django-admin startproject`).  
4. Run server (`python manage.py runserver`).  
5. Create app (`startapp`).  
6. Add views & URLs.  

---
