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

- `chmod`: Change file permissions.
  ```bash
  chmod 755 filename    # Set read/write/execute permissions for the owner, and read/execute for others
  chmod u+x filename    # Add execute permission to the file for the owner
  ```

- `chown`: Change file owner and group
  ```bash
  chown user:group filename   # Change ownership of a file
  ```


### 4. Process Management

- `ps`: View running processes.
  ```bash
  ps
  ps -ef    # Detailed process view
  ```

- `top`: Display real-time system processes.
  ```bash
  top
  ```

- `kill`: Terminate a process by its PID.
  ```bash
  kill 1234    # Kill process with PID 1234
  ```

- `killall`: Terminate processes by name.
  ```bash
  killall process_name    # Kill all processes named "process_name"
  ```


### 5. System Information

- `uname`: Show system information.
  ```bash
  uname -a    # Display all system information
  ```

- `df`: Check disk space usage.
  ```bash
  df -h    # Show disk usage in human-readable format
  ```

- `du`: Check directory or file size.
  ```bash
  du -h directory_name   # Display the size of a directory
  ```

- `free`: Display memory usage.
  ```bash
  free -h    # Show memory in human-readable format
  ```

- `uptime`: Show how long the system has been running.
  ```bash
  uptime
  ```

### 6. Networking

- `ifconfig`: View or configure network interfaces.
  ```bash
  ifconfig
  # ifconfig: Unix-like systems, more powerful for managing network interfaces.
  # ipconfig: Windows systems, mainly for viewing and renewing IP information for troubleshooting.
  ```

- `ping`: Test network connectivity.
  ```bash
  ping google.com    # Send packets to a host to check connectivity
  ```

- `curl`: Transfer data from or to a server.
  ```bash
  curl http://example.com
  ```

- `wget`: Download files from the web.
  ```bash
  wget http://example.com/file
  ```

### 7. Archiving and Compression

- `tar`: Archive files and directories.
  ```bash
  tar -cvf archive.tar directory    # Create an archive of a directory
  tar -xvf archive.tar              # Extract an archive
  ```

- `gzip`: Compress files.
  ```bash
  gzip filename    # Compress a file
  gunzip filename.gz    # Decompress a file
  ```

  **difference between Archiving and Compressing:**

  | Feature             | Archiving                                          |   Compressing                                         |
  |---------------------|---------------------------------------------------|  ----------------------------------------------------|
  | **Definition**       | Combines multiple files into a single file without reducing size. |   Reduces the size of one or more files by encoding data more efficiently. |
  | **Purpose**          | Organize and store multiple files in one place.   | Save disk space   or reduce transfer time by making files smaller.          |
  | **File Structure**   | Maintains the original structure of the files.    | Changes the   internal structure to reduce file size. |
  | **Tools**            | `tar`, `cpio`, `7-zip` (for archiving)            | `gzip`, `bzip2`,   `zip`, `7z`, `xz`                 |
  | **Formats**          | `.tar`, `.iso`                                    | `.zip`, `.gz`, `.  bz2`, `.7z`, `.xz`                |
  | **Combination**      | Often combined with compression (e.g., `.tar.gz`).| Compression is   typically done after archiving.     |
  | **Use Case**         | Backup or group files for easier management or distribution. | Save   disk space or speed up file transfer.         |
  | **Restoring Files**  | Files are extracted while maintaining structure.  | Files are   decompressed and restored to original size. |


### 8. User and Group Management
- `whoami`: Display the current logged-in user.
  ```bash
  whoami
  ```

- `sudo`: Run a command with superuser privileges
  ```bash
  sudo command    # Run a command as the superuser
  ```

- `useradd`: Add a new user.
  ```bash
  sudo useradd username
  ```

- `passwd` username
  ```bash
  passwd username
  ```

