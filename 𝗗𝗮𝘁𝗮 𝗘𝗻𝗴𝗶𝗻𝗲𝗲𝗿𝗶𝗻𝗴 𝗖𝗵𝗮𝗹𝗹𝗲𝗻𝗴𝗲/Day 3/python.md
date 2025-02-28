## Python Challenge: Lambda functions

### What does this Python statement return?
```python
numbers = [1, 2, 3, 4]
doubled = list(map(lambda x: x*2, numbers))
print(doubled)
```
- [2, 4, 6, 8]
- [1, 2, 3, 4]
- Error
- [1, 4, 9, 16]

**Ans:** [2, 4, 6, 8]

**Explanation:**
- `map(lambda x: x*2, numbers):` 
  - map() applies the lambda function (lambda x: x*2) to each element in the numbers list.
  - The lambda function doubles each element.
  - This results in an iterator that would produce the values 2, 4, 6, and 8.
- `list(...):`
  - The list() function converts the iterator returned by map() object into a list.
