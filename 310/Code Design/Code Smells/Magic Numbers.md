Magic numbers are when specific values are used that are not explained or abstracted in code. They make changes difficult because they are hard to interpret, and two usages of the same magic number can be extremely difficult to tell apart

In this case, the 6.X number is extremely hard to interpret
```python
def f(m1,m2,r):
	return 6.6743 × 10 ** -11 * m1 * m1 / (r ** 2)
```

In this case, G is much more understandable
```python
G = 6.6743 × 10 ** -11 # Gravitational constant
def f(m1,m2,r):
	return G * m1 * m1 / (r ** 2)
```
#310