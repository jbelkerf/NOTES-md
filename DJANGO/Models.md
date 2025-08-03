
## Creating a model

- the model i. Django is like table in sql, we can create models by defining a class in the models.py file :
```python
class Menu(models.Model):
	name = models.CharField(max_length = 100)
	cuisine = models.CharField(max_length = 100)
	price = models.IntegerField()
  
	def __str__(self) -> str:
		return self.name + ":" + self.cuisine # whenever called will print name : cuisine
```
 - then we need to add some configuration to the settings.py file in the project folder 
```python
INSTALLED_APPS = [
'my_app.apps.MyAppConfig',
]
```
- to apply this on the database we need to perform migration, by 
```shell
	python manage.py makemigrations
	python manage.py migrate
```

- then if we want to add some records to the table manually we can do this like this :
```shell
	python manage.py shell
	>>> from my_app.models import Menu
	>>> t = Menu.objects.create(name = 'tajine', cuisine='morrocan',price= 30)
	>>> p = Menu.objects.create(name = 'pasta', cuisiene='italian', price= 20)
	>>> Menu.objects.all()
	<QuerySet [<Menu: tajine:morrocan>, <Menu: pasta:italian>]>
	>>> t.name = 'super tajine'
	>>> t.save()
	>>> Menu.objects.all()
	<QuerySet [<Menu: super tajine:morrocan>, <Menu: pasta:italian>]>
	>>> N = Menu.objects.get(pk=2)
```

--> adding a record is done using Menu.objects.create()
--> geting a record is done using the Menu.bjects.get(pk=x)
...
