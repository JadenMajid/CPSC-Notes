---
tags:
  - "CPSC310"
---
The law of Demeter states a method should only call methods from
- itself
- an object passed as an argument
- an object it creates or instantiates
- an object stored in an instance variable


It leads to the avoidance of method chaining like:
```python
customer.getWallet().getMoney()
```
#310
#310
#310