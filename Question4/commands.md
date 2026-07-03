# File Access and I/O Investigation Command Reference

This document serves as a quick reference for the commands utilized during the File Access and I/O Investigation.

### 1. Create Directories and Experiment Files
- **Command**: `mkdir -p experiment screenshots && touch experiment/logfile.txt experiment/output.txt experiment/error.txt experiment/combined_output.txt experiment/sample_input.txt`
- **Purpose**: Creates the directory structure and required placeholder files.
- **Description**: Standard `mkdir` and `touch` commands to set up the lab environment.
- **Expected Result**: Directories and empty text files are created without error.

### 2. View Open File Descriptors
- **Command**: `ls -l /dev/fd`
- **Purpose**: Displays the active file descriptors for the current shell session.
- **Description**: Lists the contents of the dynamic `/dev/fd` directory which tracks open streams.
- **Expected Result**: Output displaying descriptors 0 (stdin), 1 (stdout), and 2 (stderr).

### 3. Track Open Files with lsof
- **Command**: `tail -f experiment/logfile.txt &` followed by `lsof -p <PID>`
- **Purpose**: Opens a file in the background and investigates it using the List Open Files (`lsof`) utility.
- **Description**: `lsof -p` filters the open file tracking to a specific Process ID.
- **Expected Result**: Output displaying the `tail` process maintaining an active file descriptor on `logfile.txt`.

### 4. Output Redirection (Overwrite)
- **Command**: `echo "Line 1" > experiment/output.txt`
- **Purpose**: Redirects standard output (stdout) into a file, overwriting its contents.
- **Description**: The `>` operator captures FD 1 and writes it to disk.
- **Expected Result**: File is created/overwritten with the text "Line 1".

### 5. Output Redirection (Append)
- **Command**: `echo "Line 2" >> experiment/output.txt`
- **Purpose**: Redirects standard output (stdout) into a file, appending to the end.
- **Description**: The `>>` operator captures FD 1 and adds it to the bottom of the file without deleting existing data.
- **Expected Result**: File now contains "Line 1" followed by "Line 2".

### 6. Error Redirection
- **Command**: `ls non_existent_file 2> experiment/error.txt`
- **Purpose**: Redirects standard error (stderr) into a dedicated error log file.
- **Description**: The `2>` operator specifically captures FD 2, ensuring errors don't clutter the terminal screen.
- **Expected Result**: The terminal shows no error, but `error.txt` contains the "No such file or directory" message.

### 7. Combined Output Redirection
- **Command**: `ls / experiment/non_existent_file > experiment/combined_output.txt 2>&1`
- **Purpose**: Redirects both standard output (stdout) and standard error (stderr) into the same file.
- **Description**: First routes FD 1 to the file (`>`), and then routes FD 2 into FD 1 (`2>&1`).
- **Expected Result**: The resulting file contains both the successful directory listing of `/` and the error message for the non-existent file.

### 8. Inspect Resource Limits
- **Command**: `ulimit -a`
- **Purpose**: Displays the resource limits enforced on the current shell session.
- **Description**: The `-a` flag lists all limits, including maximum open files and memory stack size.
- **Expected Result**: Output detailing the limits for cpu time, file descriptors, and processes.
