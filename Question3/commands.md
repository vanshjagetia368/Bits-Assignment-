# File System and Link Analysis Command Reference

This document serves as a quick reference for the commands utilized during the Link Analysis experiment.

### 1. Create Directories and Original File
- **Command**: `mkdir -p experiment screenshots && echo "This is the original file containing confidential project data." > experiment/original.txt`
- **Purpose**: Creates the directory structure and a sample file with text.
- **Description**: Sets up the environment required for testing links.
- **Expected Result**: A new `original.txt` file is populated with the text string.

### 2. Create Hard Link
- **Command**: `ln experiment/original.txt experiment/hardlink.txt`
- **Purpose**: Creates a hard link pointing to the original file's inode.
- **Description**: Standard `ln` command without any flags creates a hard link.
- **Expected Result**: A file named `hardlink.txt` is created that perfectly mirrors `original.txt` without consuming additional data blocks.

### 3. Create Symbolic Link
- **Command**: `cd experiment && ln -s original.txt softlink.txt`
- **Purpose**: Creates a symbolic link pointing to the original file's path.
- **Description**: The `-s` flag tells `ln` to create a soft (symbolic) link instead of a hard link.
- **Expected Result**: A file named `softlink.txt` is created pointing to `original.txt`.

### 4. Investigate Inodes
- **Command**: `ls -li experiment`
- **Purpose**: Displays the inode numbers and detailed listing of the files.
- **Description**: The `-i` flag forces `ls` to print the index number (inode) of each file in the first column.
- **Expected Result**: Output showing that `original.txt` and `hardlink.txt` share the same inode number, while `softlink.txt` has a distinct one.

### 5. View File Metadata
- **Command**: `stat -x experiment/original.txt`
- **Purpose**: Displays the metadata stored within the inode.
- **Description**: The `stat` command extracts detailed information about the file. (`-x` is used on macOS/BSD systems for a Linux-like readable format).
- **Expected Result**: Information regarding the file's Size, Blocks, IO Block, Uid, Gid, Links count, and Timestamps (Access, Modify, Change).

### 6. Delete Original File
- **Command**: `rm experiment/original.txt`
- **Purpose**: Deletes the original file path name to test the resilience of the links.
- **Description**: Standard file removal command.
- **Expected Result**: The `original.txt` file disappears from the directory listing.

### 7. Test Hard Link
- **Command**: `cat experiment/hardlink.txt`
- **Purpose**: Attempts to read data from the hard link.
- **Description**: Prints file contents to standard output.
- **Expected Result**: The original text is successfully printed because the data blocks still exist on disk.

### 8. Test Symbolic Link
- **Command**: `cat experiment/softlink.txt`
- **Purpose**: Attempts to read data from the soft link.
- **Description**: Prints file contents to standard output.
- **Expected Result**: Fails with a "No such file or directory" error because the target path no longer exists.
