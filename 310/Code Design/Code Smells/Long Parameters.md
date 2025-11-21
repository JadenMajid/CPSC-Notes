Long parameter lists make it hard to remember what parameter does what. If two parameters have the same type, then it can be hard to differentiate them. 

We can mitigate long parameters with the type system, which can encapsulate several parameters into one object

```python
day_of_week(day, month, year):
	return ...
	
# Take this example, is this feb 1st or jan 2nd?
day_of_week(1, 2, 2025):
day_of_week(2, 1, 2025):
```

```python
day_of_week(date: datetime):
	return ...
# much more readable
dt = datetime.datetime.now()
day_of_week(dt):
```
#310
#310
#310