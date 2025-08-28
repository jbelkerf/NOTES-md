- if we want to create a form using django we can create our class in the forms.py file :
```python
from django import forms

class Appform(forms.Form):
    name = forms.CharField(label="name of user", max_length=10)
    age = forms.CharField(label="enter your name here", max_length=50)
    address = forms.CharField(label="address", max_length=100)
    hobies = (('Managa', 'Managa'),
              ('Anime', 'Anime'),
              ('Sieries', 'Sieries'))
    field = forms.ChoiceField(choices=hobies)
```

- but if we already have a model (like a table in the database) we can create the form from the model directly:
--> the model in models.py:
```python
from django.db import models

class Booking(models.Model):
	first_name = models.CharField(max_length=200)
	last_name = models.CharField(max_length=200)
	guest_count = models.IntegerField()
	reservation_time = models.DateField(auto_now=True)
	comments = models.CharField(max_length=200)
```

--> the form in forms.py:
```python
from django import forms
from .models import Booking

	class BookingForm(forms.ModelForm):
		class Meta:
			model = Booking
			fields = "__all__"
```
- that will create a form with all the fields in the model but if we want to specify which fields we can do like that :
```python
from django import forms
from .models import Booking

	class BookingForm(forms.ModelForm):
		class Meta:
			model = Booking
			fields = ["first_name", "last_name"]
```

--> in the views.py to save the result to the database:
```python
from django.shortcuts import render
from myapp.forms import BookingForm

def form_view(request):
	form = BookingForm()
	if request.method == 'POST':
		form = BookingForm(request.POST)
			if form.is_valid():
			form.save()
	context = {"form" : form}
	return render(request, "booking.html", context)
```