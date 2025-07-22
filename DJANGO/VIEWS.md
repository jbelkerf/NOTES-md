
- a view in Django is a function design to handle user request and return a response 
- the views funcs are preferably saved in views.py in the app directory 

--> view example:

```python
from django.http import HttpResponce

def home(request):
	return "<h1>this is a page</h1>"
```

## ROUTING
-  MAPPING THE VIEW TO URL VIA urls.py
- the urls.py is in the app directory 
--> urls.py example:

```python
from django.urls import path
from . import views

urlpatterns = [
	path('home', views.home),
]
```
## URL configuration 
--> there is two urls.py one in the project level one in the app level if we want to link the project level with the app level we use the include() function


### example of linking the app level with the project level 
--> the myapp level:
```python
from djabgo.shortcuts import render
from django.http import HttpResponse
from django.urls import path
from . import views

urlpatterns = [
	path('home', views.home),
]
```
-->  the project level:
```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
	path('admin/', admin.site.urls),
	path('', include('myapp.urls'))
]
```