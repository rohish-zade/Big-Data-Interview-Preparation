# Essential Linux commands

### 1. File and Directory Management

- `ls`: List the contents of a directory
  ```bash
  ls
  ls -l     # Detailed list view
  ls -a     # Include hidden files
  ```

- `cd`: Change the current directory
  ```bash
  cd /path/to/directory
  cd ..     # Go up one level
  cd ~      # Go to the home directory
  ```

- `pwd`: Print the working directory (current location).
  ```bash
  pwd
  ```

- `mkdir`: Create a new directory
  ```bash
  mkdir new_directory
  ```

- `rmdir`: Remove an empty directory.
  ```bash
  rmdir: Remove an empty directory.
  ```

- `rm`: Remove files or directories.
  ```bash
  rm filename            # Remove a file
  rm -r directory_name    # Remove a directory and its contents
  ```

- `cp`: Copy files or directories.
  ```bash
  cp file1 file2                     # Copy file1 to file2
  cp -r directory1 directory2        # Copy directory1 to directory2
  ```

- `mv`: Move or rename files or directories.
  ```bash
  mv oldname newname                 # Rename a file or directory
  mv filename /path/to/destination   # Move a file
  ```

### 2. File Viewing and Editing

- `cat`: View the contents of a file.
  ```bash
  cat filename
  ```

- `less`: View a file one page at a time.
  ```bash
  less filename
  ```

- `head`: View the first few lines of a file.
  ```bash
  head filename
  head -n 20 filename    # View the first 20 lines
  ```
- `tail`: View the last few lines of a file.
  ```bash
  tail filename
  tail -f filename       # Follow a file as it grows (useful for logs)
  ```

- `nano`: Open a simple text editor.
  ```bash
  nano filename
  ```

### 3. Permissions and Ownership
