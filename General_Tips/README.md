# * and \*\*

https://stackabuse.com/unpacking-in-python-beyond-parallel-assignment/

How does a single * work in Python?

## Packing with a *
```python
*a, = 1,  # [1]
*a, b = 1, 2, 3, 5  # a = [1, 2, 3] # b = 5
```
