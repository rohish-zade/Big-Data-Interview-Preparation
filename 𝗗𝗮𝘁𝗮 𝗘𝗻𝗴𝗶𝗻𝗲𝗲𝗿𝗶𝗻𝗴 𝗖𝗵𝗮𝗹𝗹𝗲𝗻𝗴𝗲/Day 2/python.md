## Python Challenge

### what will be the output of the following Python code?
  ```python
  # Dictionary Modification
  dict_1 = {'a': 1, 'b': 2}
  dict_2 = dict_1
  dict_2['c'] = 3
  print(dict_1)
  ```
- {'a': 1, 'b': 2}
- {'a': 1, 'b': 2, 'c': 3}
- {'c': 3}
- Error

**Ans:** {'a': 1, 'b': 2, 'c': 3}

**Explanation:**
- Dictionaries are mutable in Python, meaning changes to one reference affect all references to the same object.
- dict_2 = dict_1 does not create a new dictionary, but rather creates a new reference to the same object in memory.
- Any modification to dict_2 modifies dict_1 as well.
- To avoid this, use dict.copy() for a shallow copy or copy.deepcopy() for a deep copy when working with nested structures.