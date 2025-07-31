
- the reverse function is used to reverse the name to urls
- here is how to use reverse func
```bash
python manage.py shell

>>> from django.urls import reverse
>>> reverse('home')
'/demo/'
```
- if we have multiple apps we can use reverse this way
```shell
python manage.py shell
>>> from django.urls import reverse
>>> reverse('appname:home')
'appname/home'
```