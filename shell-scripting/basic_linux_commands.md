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

- `touch`: Create an empty file
  ```bash
  touch newfile.txt # create newfile.txt
  ```

- `find`: Search for files in a directory hierarchy	
  ```bash
  find / -name "myfile.txt" # find myfile.txt starting from root
  ```

- `locate`: Find files by name	
  ```bash
  locate file.txt # search for file.txt
  ```

- file: Determine file type	
  ```bash
  file image.png # show type of image.png
  ```


### 2. File Viewing and Editing

- `echo`: Print text to standard output
  ```bash
  echo "Hello World" # print Hello World
  ```

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

- `grep`: Search for patterns in files	
  ```bash
  grep "error" logfile.txt # search for "error" in logfile.txt
  ```

- `awk`: Pattern scanning and processing language	
  ```bash
  awk '{print $1}' file.txt # print the first column from file.txt
  ```

- `sed`: Stream editor for filtering and transforming text	
  ```bash
  sed 's/old/new/g' file.txt # replace old with new in file.txt
  ```

- `cut`: Remove sections from each line of files	
  ```bash
  cut -d':' -f1 /etc/passwd # cut and display first field from /etc/passwd file
  ```

- `sort`: Sort lines of text files	
  ```bash
  sort file.txt # sort lines alphabetically in file.txt
  ```

- `uniq`: Report or filter out repeated lines	
  ```bash
  uniq file.txt # filter out duplicate lines in file.txt
  ```

- `wc`: Print newline, word, and byte counts for files	
  ```bash
  wc -l file.txt # count lines in file.txt
  ```

- `diff`: Compare files line by line	
  ```bash
  diff file1.txt file2.txt # compare file1.txt and file2.txt
  ```

- `cmp`: Compare two files byte by byte	
  ```bash
  cmp file1.txt file2.txt (compare files byte by byte)
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

- `jobs`: List background jobs	
  ```bash
  jobs # list active jobs
  ```

- `nohup`: Run a command immune to hangups	
  ```bash
  nohup script.sh & (run script.sh immune to terminal closing)
  ```

- `time`: Measure program execution time	
  ```bash
  time ./script.sh (measure how long script.sh takes to run)
  ```


### 5. System Information

- `uname`: Show system information.
  ```bash
  uname -a    # Display all system information
  ```

- `hostname`: Display or set the system’s hostname	
  ```bash
  hostnamectl set-hostname newname # change hostname to newname
  ```

- `uptime`: Show how long the system has been running.
  ```bash
  uptime
  ```

- `vmstat`:	Report virtual memory statistics	
  ```bash  
  vmstat 1 # show virtual memory statistics every second
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

- `id`:	Display user and group IDs	
  ```bash
  id username # show user and group IDs for username
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

