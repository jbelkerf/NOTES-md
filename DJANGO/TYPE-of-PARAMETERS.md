
# Path parameter
- The URL pattern treats the identifiers in angular brackets (<..>) as the path parameters. By default, it parses the received value to the string type

--> the user browse the endpoint http://localhost:8000/myapp/John/1.

--> the url.py file :
```python
path('getuser/<name>/<id>', views.pathview, name='pathview'),
```
--> the views.py
```python

from django.http import HttpResponse

def pathview(request, name, id):
	return HttpResponse("Name:{} UserID:{}".format(name, id))
	
```

# Query parameter
- A query string is a sequence of one or more key=value pairs concatenated by the & symbol. Each key is the query parameter. The query string ends with the ? symbol after the URL endpoint.

--> the user browse http://localhost:8000/myapp/?name=John&id=1

--> url.py file:

```python
path('getuser/', views.qryview, name='qryview'),
```
--> views.py file:

```python
def qryview(request):
	name = request.GET['name']
	id = request.GET['id']
	return HttpResponse("Name:{} UserID:{}".format(name, id))
	
```
# Body parameters
- An HTML form sends the data to the URL mentioned in its action attribute using the POST method. The POST method is a more secure way of sending data than the GET method because the data is not revealed in the URL.

--> the form:
```html
<form action="/myapp/getform/" method="POST">
	{% csrf_token %}
	<p>Name: <input type="text" name="id"></p>
	<p>UserID :<input type="name" name="name"></p>
	<input type="submit">
</form>
```
 --> the url.py:
 
```python
path("showform/", views.showform, name="showform"),
```

--> the views.py:

```python
def getform(request):
	if request.method == "POST":
		id=request.POST['id']
		name=request.POST['name']
	return HttpResponse("Name:{} UserID:{}".format(name, id))
```


