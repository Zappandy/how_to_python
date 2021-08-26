# * and \*\*

https://stackabuse.com/unpacking-in-python-beyond-parallel-assignment/

How does a single * work in Python?

## Packing and unpacking with *
```python
*a, = 1,  # [1]
*a, b = 1, 2, 3, 5  # a = [1, 2, 3] # b = 5
*a, b, c, d = 1, 2, 3 # [] # 1 # 2 # 3
*ran, = range(10)  # [0, 1, 2...]
*gen, = (2 ** x for x in range(10))  # [1, 2, 4, 8, 16...]
```

We are using the logic of a tuple, thus why we need to use a comma *,*. It's important to note that we can't use more than one stared expression in the assignment

Other uses can be...

```python
my_tuple = (1, 2, 3)
(0, *my_tuple, 4)  # (0, 1, 2, 3, 4)
my_str = "456"
[*my_tuple, *my_str]  # [1, 2, 3, '4', '5', '6']
```
## Packing and unpacking with \**

```python
numbers = {"one": 1, "two": 2, "three": 3}
letters = {"a": "A", "b": "B", "c": "C"}
combination = {**numbers, **letters}
#{'one': 1, 'two': 2, 'three': 3, 'a': 'A', 'b': 'B', 'c': 'C'}
```

An issue is that when dictionaries share the same key, the right-most dictionary will override the values of the left most dictionary.

```python
letters = {'a': 'A', 'b': 'B', 'c': 'C'}
fake_vowels = {'a': 'a', 'b': 'e'}
{**letters, **fake_vowels}
```

https://medium.com/swlh/how-to-pack-and-unpack-data-in-python-tuples-and-dictionaries-55d218c65674

## Cool methods

### For dictionaries and sets
update(), accepts a dictionary or keys with its values in an iterable as its argument to add to the current dict. I.e. letters.update(g='G', h='H') or letters.update({'g': 'G', 'h': 'H'}). As we can seewhen we pass an iterable, the keys should not be strings/chars.

Unlike setdefault, this can override previous keys. Update can also work with sets. It unpacks values from other iterables and adds them to the set!

 Do not forget that add() works with sets, not dictionaries

pop() removes elements at random in sets and in dictionaries it removes the passed key. We can add a 2nd arg as a default result if the key is not in the dictionary
