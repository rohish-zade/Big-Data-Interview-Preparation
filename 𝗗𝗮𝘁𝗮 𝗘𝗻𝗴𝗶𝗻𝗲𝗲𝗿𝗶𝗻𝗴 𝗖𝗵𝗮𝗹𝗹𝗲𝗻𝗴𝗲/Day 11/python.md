## Python Challenge: Multithreading vs. Multiprocessing

### What is the advantage of using a context manager (with statement) when working with files?

- A) It reduces memory usage
- B) It automatically closes the file after execution
- C) It speeds up file reading
- D) It prevents all errors

**Ans:** B) It automatically closes the file after execution


**Explanation:**
- Using a context manager (`with` statement) ensures that a file is properly closed after execution, even if an error occurs. This helps in preventing resource leaks and improves code readability.
-  Example Without Context Manager:
    ```python
    file = open("data.txt", "r")
    data = file.read()
    file.close()  # Must manually close the file
    ```
- Example With Context Manager:
    ```python
    with open("data.txt", "r") as file:
        data = file.read()  # File is automatically closed after this block
    ```