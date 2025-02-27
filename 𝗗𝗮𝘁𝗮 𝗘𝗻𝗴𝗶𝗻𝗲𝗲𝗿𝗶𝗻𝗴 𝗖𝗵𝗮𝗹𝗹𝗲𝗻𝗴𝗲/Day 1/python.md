## Python Challenge

```python
list_1 = [1, 2, 3]
list_2 = list_1
list_2.append(4)
print(list_1)
```

### what will be the output of the following Python code?
- [1, 2, 3]
- [1, 2, 3, 4]
- [4, 1, 2, 3]
- Error

**Ans:** [1, 2, 3, 4]

**Explanation:**
- You cannot copy a list simply by typing list_2 = list_1, because: list_2 will only be a reference to list_1, and changes made in list_1 will automatically also be made in list_2 and vice versa.
- There are ways to make a copy, one way is to use the built-in List method copy().
  ```python
  # Make a copy of a list with the copy() method:
  thislist = ["apple", "banana", "cherry"]
  mylist = thislist.copy()
  print(mylist)
  
  # Another way to make a copy is to use the built-in method list().
  mylist2 = list(thislist)
  print(mylist)
  ```