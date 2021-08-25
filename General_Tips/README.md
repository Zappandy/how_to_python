# * and \*\*

https://stackabuse.com/unpacking-in-python-beyond-parallel-assignment/

How does a single * work in Python?

## Packing with a *
```python
*a, = 1,  # [1]
*a, b = 1, 2, 3, 5  # a = [1, 2, 3] # b = 5
*a, b, c, d = 1, 2, 3 # [] # 1 # 2 # 3
*ran, = range(10)  # [0, 1, 2...]
*gen, = (2 ** x for x in range(10))  # [1, 2, 4, 8, 16...]
```

We are using the logic of a tuple, thus why we need to use a comma *,*. It's important to note that we can't use more than one stared expression in the assignment

https://medium.com/swlh/how-to-pack-and-unpack-data-in-python-tuples-and-dictionaries-55d218c65674
