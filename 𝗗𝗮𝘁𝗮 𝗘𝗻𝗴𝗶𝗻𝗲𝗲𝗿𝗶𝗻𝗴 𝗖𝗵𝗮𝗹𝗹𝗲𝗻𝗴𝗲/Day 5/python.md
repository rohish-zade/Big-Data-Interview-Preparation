## Python Challenge: Exception Handling

### What will be the output of this Python code?
  ```python
  try:
      print(5/0)
  except ZeroDivisionError:
      print("Error: Cannot divide by zero!")
  ```
- A) 5
- B) Error: Cannot divide by zero!
- C) ZeroDivisionError
- D) SynataxError

**Ans:** B) Error: Cannot divide by zero!

**Explanation:**
- `try block:` The code inside the try block is executed.
- `print(5/0):` This line attempts to divide 5 by 0, which causes a ZeroDivisionError.
- `except ZeroDivisionError:` Since a `ZeroDivisionError` occurred, the code inside the `except` block is executed.
- `Output:` The `print("Error: Cannot divide by zero!")` statement outputs the error message to the console.