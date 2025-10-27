---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-10-25T18:01
---
---

## Django Cheatsheet (Beginner to Advanced)

### 1. Installation & Setup

```bash
# Install Django
pip install django

# Check version
django-admin --version

# Create a new project
django-admin startproject projectname

# Run development server
python manage.py runserver

# Create a new app
python manage.py startapp appname
```

### 2. Virtual Environment

```bash
# Create virtual environment
python3 -m venv venv

# Activate environment
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

# Deactivate environment
deactivate
```

### 3. Project Structure

```
projectname/
├── manage.py
├── projectname/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
└── appname/
    ├── models.py
    ├── views.py
    ├── urls.py
    ├── admin.py
    ├── apps.py
    ├── migrations/
    └── templates/
```

### 4. Migrations & Database

```bash
# Make migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# Show migration history
python manage.py showmigrations

# Rollback migration
python manage.py migrate appname migration_name
```

### 5. Models

```python
from django.db import models

class Employee(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
    email = models.EmailField(unique=True)
    joined_on = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.name
```

### 6. Admin Panel

```bash
# Create superuser
python manage.py createsuperuser
```

```python
# admin.py
from django.contrib import admin
from .models import Employee

admin.site.register(Employee)
```

### 7. Views

```python
# views.py
from django.shortcuts import render, HttpResponse

def home(request):
    return render(request, 'home.html')

def about(request):
    return HttpResponse('About Page')
```

### 8. URLs

```python
# project/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('appname.urls')),
]

# app/urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),
    path('about/', views.about, name='about'),
]
```

### 9. Templates

```bash
# In settings.py
TEMPLATES = [
    {
        'DIRS': [BASE_DIR / 'templates'],
    }
]
```

```html
<!-- templates/home.html -->
<!DOCTYPE html>
<html>
<head>
  <title>Home</title>
</head>
<body>
  <h1>Welcome {{ name }}</h1>
</body>
</html>
```

### 10. Static & Media Files

```python
# settings.py
STATIC_URL = '/static/'
STATICFILES_DIRS = [BASE_DIR / 'static']

MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

```bash
# Collect static files
python manage.py collectstatic
```

### 11. Forms

```python
from django import forms
from .models import Employee

class EmployeeForm(forms.ModelForm):
    class Meta:
        model = Employee
        fields = '__all__'
```

### 12. ORM Queries

```python
Employee.objects.all()
Employee.objects.filter(age__gte=30)
Employee.objects.get(id=1)
Employee.objects.create(name='John', age=30)
Employee.objects.update(age=35)
Employee.objects.delete()
```

### 13. Authentication System

```bash
# Built-in views
login, logout, password_change, password_reset
```

```python
from django.contrib.auth.models import User
from django.contrib.auth import authenticate, login, logout
```

### 14. Middleware

```python
# settings.py
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
]
```

### 15. Signals

```python
from django.db.models.signals import post_save
from django.dispatch import receiver
from django.contrib.auth.models import User

@receiver(post_save, sender=User)
def create_profile(sender, instance, created, **kwargs):
    if created:
        print('Profile created!')
```

### 16. File Uploads

```python
# models.py
file = models.FileField(upload_to='uploads/')
```

```html
<form method="POST" enctype="multipart/form-data">
  {% csrf_token %}
  <input type="file" name="file">
  <button type="submit">Upload</button>
</form>
```

### 17. Class-Based Views

```python
from django.views import View
from django.shortcuts import render

class HomeView(View):
    def get(self, request):
        return render(request, 'home.html')
```

### 18. Django REST Framework (DRF)

```bash
pip install djangorestframework
```

```python
# settings.py
INSTALLED_APPS = [
    'rest_framework',
]

# serializers.py
from rest_framework import serializers
from .models import Employee

class EmployeeSerializer(serializers.ModelSerializer):
    class Meta:
        model = Employee
        fields = '__all__'

# views.py
from rest_framework import viewsets
from .models import Employee
from .serializers import EmployeeSerializer

class EmployeeViewSet(viewsets.ModelViewSet):
    queryset = Employee.objects.all()
    serializer_class = EmployeeSerializer

# urls.py
from rest_framework.routers import DefaultRouter
router = DefaultRouter()
router.register('employees', EmployeeViewSet)
urlpatterns += router.urls
```

### 19. Caching

```python
# settings.py
CACHES = {
    'default': {
        'BACKEND': 'django.core.cache.backends.locmem.LocMemCache',
    }
}
```

### 20. Deployment

```bash
# Collect static files
python manage.py collectstatic

# Run server
python manage.py runserver 0.0.0.0:8000

# WSGI/ASGI setup for production
```

### 21. Testing

```bash
python manage.py test
```

```python
from django.test import TestCase
from .models import Employee

class EmployeeTest(TestCase):
    def test_create(self):
        emp = Employee.objects.create(name='John', age=25)
        self.assertEqual(emp.name, 'John')
```

### 22. Advanced Topics

- **Custom Middleware**
    
- **Custom Template Tags & Filters**
    
- **Celery for background tasks**
    
- **Channels for WebSockets**
    
- **Django Signals**
    
- **Custom User Model**
    
- **JWT Authentication (DRF)**
    
- **Permissions & Throttling (DRF)**
    
- **Environment Variables with `python-decouple`**
    
- **Caching (Memcached, Redis)**
    
- **Asynchronous Views (async def)**
    
- **Internationalization (i18n)**
    
- **Django Security (CSRF, HTTPS, HSTS)**
    
- **Logging Configuration**
    

---

This cheatsheet covers Django from setup to deployment, including ORM, DRF, signals, caching, and production concepts.

