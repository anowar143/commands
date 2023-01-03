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
python3 manage.py startapp corebd
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
#### Create models corebd/models.py
```
from django.db import models

class Corebd(models.Model):
    created = models.DateTimeField(auto_now_add=True, )
    title = models.CharField(max_length=100, blank=False, )
    description = models.TextField(max_length=5000, blank=False, )
    
    class Meta:
        ordering = ['created']
        
    def __str__(self):
        return self.title
```
#### Then create an initial migration file and sync the database for the first time.
```
python3 manage.py makemigrations
python3 manage.py migrate
```
#### But first we need to update corebd/admin.py
```
from django.contrib import admin
from .models import Corebd

admin.site.register(Corebd)
```
#### Create a corebd/serializers.py file.
```
from rest_framework import serializers
from .models import Corebd

class CorebdSerializer(serializers.ModelSerializer):

    class Meta:
        model = Corebd
        fields = ('id', 'title', 'description')
        

```
#### Edit the corebd/views.py file
```
from rest_framework import generics
from .models import Corebd
from .serializers import CorebdSerializer

class CorebdList(generics.ListCreateAPIView):
    queryset = Corebd.objects.all()
    serializer_class = CorebdSerializer


class CorebdDetail(generics.RetrieveUpdateDestroyAPIView):
    queryset = Corebd.objects.all()
    serializer_class = CorebdSerializer
```
#### The final step is to configure the tutorial/urls.py file 
```
from django.contrib import admin
from django.urls import path include, # new

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('corebd.urls')), # new
]
```
#### Then create a corebd/urls.py file
```
from django.urls import path
from corebd import views

urlpatterns = [
    path('corebd/', views.CorebdList.as_view()),
    path('corebd/<int:pk>/', views.CorebdDetail.as_view()),
]

```
#### Browsable API (Django Rest Framework ships with a browsable API that we can now use. Make sure the local server is running.)
```
python3 manage.py runserver

```
#### Navigate to the Corebd List endpoint at http://127.0.0.1:8000/corebd/.
```

```
#### We can also go to the detail view for each Corebd at http://127.0.0.1:8000/corebd/id/.
```
