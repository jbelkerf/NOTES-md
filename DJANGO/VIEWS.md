
- a view in Django is a function design to handle user request and return a response 

--> view example:
```python
from django.http import HttpResponce

def home(request):
	return "<h1>this is a page</h1>"
```