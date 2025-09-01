
- converting  a model instance to a JSON response

```python
from django.froms.models import model_to_dict
from django.http import JsonResponce

book = Book.objects.get(pk=12)
return JsonResponce(model_to_dict(book))
```

- parse request body 

```python
from django.http import QueryDict

request_body = QueryDict(request.body)

title = request_body.get('title')
```