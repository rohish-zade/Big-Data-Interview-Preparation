## Python Challenge: Decorators

### What will be the output of this Python code?
  ```python
  def decorator(func):
      def wrapper():
          print('Before function')
          func()
          print('After function')
      return wrapper
  
  def say_hello():
      print('Hello!')
  
  decorated = decorator(say_hello)
  decorated()
  ```
- A) 'Before function' -> 'Hello!' -> 'After function'
- B) 'Hello!'
- C) Error
- D) 'After function' -> 'Hello!' -> 'Before function'

**Ans:** A) 'Before function' -> 'Hello!' -> 'After function'


**Explanation:**
- The `decorator` function takes another function (`func`) as an argument and returns the `wrapper` function.
- The `wrapper` function prints 'Before function', calls the original function (`func`), and then prints 'After function'.
- `decorated = decorator(say_hello)` applies the decorator manually, meaning decorated now refers to wrapper.
- When `decorated()` is called:
  - 'Before function' is printed.
  - say_hello() is executed, printing 'Hello!'.
  - 'After function' is printed.