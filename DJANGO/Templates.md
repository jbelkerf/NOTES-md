
- text-based documents or python strings marked up using DTL : dgango template language

- example of template in django:
template
```django
<h2> this weeks special is {{dish_name}} with a price of {{ price }}.</h2>
```
views.py
```python
def about(request):
	info = {'dish_name': 'pasta', 'price': '200$'}
	return render(request, 'specials.html', {info:'info'})
```