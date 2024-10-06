# Introduction to Shell Scripting

## What is Shell?
The shell is a command-line interpreter that provides a user interface for interacting with the operating system. The most commonly used shell is Bash (Bourne Again Shell).

- Shell scripting is writing a series of commands for the shell to execute.
- Scripts help automate repetitive tasks, such as `file manipulation`, `program execution`, and `system monitoring`.


### Shell vs Bash
- A shell is a general term for any command-line interface that allows users to interact with the operating system. There are many types of shells, like `sh`, `csh`, `ksh`, and b`ash, each with its own set of commands and syntax.

- Bash (Bourne Again Shell) is a specific type of shell, widely used on Unix-like systems (Linux, macOS), and is an enhanced version of the original Bourne Shell (sh). It offers additional features like command history, auto-completion, and advanced scripting capabilities.


## How to Write and Run a Shell Script
- `Create a script file:` Use a text editor like nano, vim, or gedit to write a script.
- Example:
  ```bash
  vim myscript.sh
  ```
- `Add the Shebang line:` Every script should start with a shebang (#!), which tells the system which interpreter to use.
  ```bash
  chmod +x myscript.sh
  ```

- `Make the script executable:` Use the chmod command to make the script executable.
  ```bash
  chmod +x myscript.sh
  ```

- `Run the script:` You can run the script by typing:
  ```bash
  ./myscript.sh
  ```


## Variables

### Defining Variables
- Variables store data that can be referenced later.
- No spaces allowed around the `=` sign.
- To access a variable, prefix it with `$`.
  ```bash
  #!/bin/bash
  name="Rohish"
  echo "Hello, $name"
  ```

### Types of Variables
- `Local variables`: Declared within the script and accessible only within that script.
- `Environment variables`: Available to any script or process running in the session.
- `Special variables`: Predefined variables like $0 (script name), $1 (first argument), etc.

### Read User Input
  ```bash
  #!/bin/bash
  echo "Enter your name: "
  read name
  echo "Hello, $name"
  ```

## Comparison Operators
In shell scripting, comparison operators are used to compare values, typically within conditional statements like `if`, `while`, and `until`. Here’s a breakdown of the common comparison operators in shell scripting:

### Numeric Comparison Operators

  | Operator | Description                           | Example                          |
  |----------|---------------------------------------|----------------------------------|
  | `-eq`    | Equal to                              | `if [ "$a" -eq "$b" ]`          |
  | `-ne`    | Not equal to                          | `if [ "$a" -ne "$b" ]`          |
  | `-gt`    | Greater than                          | `if [ "$a" -gt "$b" ]`          |
  | `-lt`    | Less than                             | `if [ "$a" -lt "$b" ]`          |
  | `-ge`    | Greater than or equal to              | `if [ "$a" -ge "$b" ]`          |
  | `-le`    | Less than or equal to                 | `if [ "$a" -le "$b" ]`          |

### String Comparison Operators

  | Operator | Description                               | Example                              |
  |----------|-------------------------------------------|--------------------------------------|
  | `=`      | Equal to                                  | `if [ "$str1" = "$str2" ]`          |
  | `!=`     | Not equal to                              | `if [ "$str1" != "$str2" ]`         |
  | `<`      | Less than (for string comparison)        | `if [[ "$str1" < "$str2" ]]`        |
  | `>`      | Greater than (for string comparison)     | `if [[ "$str1" > "$str2" ]]`        |
  | `-z`     | String is null (zero length)             | `if [ -z "$str" ]`                  |
  | `-n`     | String is not null (non-zero length)     | `if [ -n "$str" ]`                  |

### File Comparison Operators

  | Operator | Description                             | Example                          |
  |----------|-----------------------------------------|----------------------------------|
  | `-e`     | File exists                             | `if [ -e "$file" ]`             |
  | `-f`     | File is a regular file                 | `if [ -f "$file" ]`             |
  | `-d`     | File is a directory                     | `if [ -d "$dir" ]`              |
  | `-r`     | File is readable                        | `if [ -r "$file" ]`             |
  | `-w`     | File is writable                        | `if [ -w "$file" ]`             |
  | `-x`     | File is executable                      | `if [ -x "$file" ]`             |
  | `-s`     | File is not empty                       | `if [ -s "$file" ]`             |


## Control Structures

### Conditional Statements

#### if-else Statement
  ```bash
  #!/bin/bash
  if [ $1 -gt 10 ]
  then
      echo "Number is greater than 10"
  else
      echo "Number is less than or equal to 10"
  fi
  ```
- `$1` is the first argument passed to the script.
- Conditions: Use square brackets `[ ]` for conditions.
- you can save the above code in file and run by giving argument as shown below:
  ```bash
   ./if_else.sh 10 # output: Number is less than or equal to 10
  ```


### elif Statement

  ```bash
  #!/bin/bash
  if [ $1 -eq 10 ]
  then
      echo "Number is 10"
  elif [ $1 -gt 10 ]
  then
      echo "Number is greater than 10"
  else
      echo "Number is less than 10"
  fi
  ```

## Loops

### for Loop
The `for` loop iterates over a list of items.
- Syntax:
  ```bash
  for variable in list
  do
    # commands
  done
  ```
- Example:
  ```bash
  #!/bin/bash
  for i in 1 2 3 4 5 # or for i in {1..5}
  do
      echo "Number: $i"
  done
  ```

### While Loop
The `while` loop continues as long as a specified condition is true.
- Syntax:
  ```bash
  while [ condition ]
  do
      # commands
  done
  ```
- Example:
  ```bash
  #!/bin/bash
  count=1
  while [ $count -le 5 ]
  do
      echo "Count: $count"
      ((count++))  # Increment the count
  done
  ```

### Until Loop
The `until` loop continues until a specified condition becomes true.
- Syntax:
  ```bash
  until [ condition ]
  do
      # commands
  done
  ```
- Example:
  ```bash
  count=1
  until [ $count -gt 5 ]
  do
      echo "Count: $count"
      ((count++))  # Increment the count
  done
  ```

### Nested Loops
You can nest loops inside each other.
- Example:
  ```bash
  for i in 1 2
  do
      for j in A B
      do
          echo "Outer: $i, Inner: $j"
      done
  done
  ```

### Break and Continue
- `break`: Exits the loop entirely.
- `continue`: Skips the current iteration and proceeds to the next iteration of the loop.

- Example with `Break`:
  ```bash
  for i in {1..5}
  do
      if [ $i -eq 3 ]; then
          break  # Exit the loop when i is 3
      fi
      echo "Number: $i"
  done
  ```
- Example with `Continue`:
  ```bashfor i in 1 2 3 4 5
  do
      if [ $i -eq 3 ]; then
          continue  # Skip the iteration when i is 3
      fi
      echo "Number: $i"
  done
  ```

### Case Statements
- In shell scripting, a case statement is used to execute a block of code based on the value of a variable.
- It's particularly useful for handling multiple conditions in a cleaner and more organized way compared to a series of if-elif statements.

- Example:
  ```bash
  #!/bin/bash
  
  echo "Enter a number between 1 and 5:"
  read number
  
  case $number in # start of case statment
      1)
          echo "You entered one."
          ;;
      2)
          echo "You entered two."
          ;;
      3)
          echo "You entered three."
          ;;
      4)
          echo "You entered four."
          ;;
      5)
          echo "You entered five."
          ;;
      *)
          echo "Invalid input. Please enter a number between 1 and 5."
          ;;
  esac # end of case statment
  ```


## Functions in Shell Scripting

Functions in shell scripting are reusable blocks of code that perform a specific task. They help to organize scripts, reduce code duplication, and make the script easier to read and maintain.

### Defining and Calling Functions
  ```bash
  #!/bin/bash

  # Function definition
  greet() {
      echo "Hello, $1!"  # $1 refers to the first argument passed to the function
  }
  
  # Calling the function
  greet "Rohish"  # Output: Hello, Rohish!
  ```

$1, $2, etc., are used to access function arguments.

### Returning Values
- Shell functions can return values, but they do so using the `return` statement for an exit status (0 for success, 1 for failure, etc.). 
- To return a value from a function, you can use `echo` to output the value and capture it when calling the function.

  ```bash
  #!/bin/bash
  
  # Function to add two numbers
  add() {
      local sum=$(( $1 + $2 ))  # Use local to define a variable within the function
      echo $sum  # Output the result
  }
  
  # Calling the function and capturing the result
  result=$(add 5 10)
  echo "The sum is: $result"  # Output: The sum is: 15
  ```