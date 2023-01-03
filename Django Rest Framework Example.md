### Initial Setup

```
mkdir drf && cd drf
```
#### For Current Version
```
pip install django
pip install djangorestframework

```
#### Otherwise Specific version like fllowing

```
pip install django==3.0.3
pip install djangorestframework==3.11.0
```
#### Start Project
```
django-admin startproject tutorial .
python manage.py startapp corebd
```
#### Now add the corebd app and rest_framework to the INSTALLED_APPS config in our tutorial/settings.py file.
```
#tutorial/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework', # new
    'corebd', # new
]
```
#### Create models
```
from django.db import models

class Corebd(models.Model):
    created = models.DateTimeField(auto_now_add=True)
    title = models.CharField(max_length=100, blank=True, default='')
    Description = models.TextField(max_length=5000, blank=True, default='')
    
    class Meta:
        ordering = ['created']
        
    def __str__(self):
        return self.title
```
#### Then create an initial migration file and sync the database for the first time.
```
python manage.py makemigrations corebd
python manage.py migrate
```
#### But first we need to update snippets/admin.py
```
# corebd/admin.py
from django.contrib import admin
from .models import Corebd

admin.site.register(Corebd)
```
#### Now create a superuser account for log in. Follow all the prompts for setting a username, email, and password. I've used admin, admin@gmail.com, and adminpass123.
```
python manage.py createsuperuser
```
#### Afrer create superuser 
```
python manage.py runserver
```


![image](Images/django home page.png)
---

####
```

```
####
```

```
