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



