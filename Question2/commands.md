# Secure Project Workspace Command Reference

This document serves as a quick reference for the commands utilized during the Secure Project Workspace Setup.

### 1. Create Workspace Directories
- **Command**: `mkdir -p workspace/project_docs workspace/reports workspace/config workspace/logs`
- **Purpose**: Creates the directory hierarchy.
- **Short Description**: Creates multiple directories at once, creating parent directories if they don't exist (`-p`).
- **Expected Result**: Four directories are created inside the `workspace` folder without any errors.

### 2. Create Sample Files
- **Command**: `touch workspace/project_docs/requirements.txt workspace/project_docs/notes.txt workspace/reports/weekly_report.txt workspace/config/settings.conf workspace/logs/project.log`
- **Purpose**: Generates empty placeholder files for the workspace.
- **Short Description**: Creates empty files if they don't exist, or updates their timestamps.
- **Expected Result**: Empty files are created in their respective directories.

### 3. Display Directory and File Permissions
- **Command**: `ls -lR workspace`
- **Purpose**: Recursively lists all files and directories with their permissions.
- **Short Description**: Long format listing (`-l`) applied recursively (`-R`).
- **Expected Result**: A detailed output showing permissions (e.g., `drwxr-xr-x` and `-rw-r--r--`), owner, group, and sizes for every file in the hierarchy.

### 4. Secure the Project Documents Directory
- **Command**: `chmod 700 workspace/project_docs`
- **Purpose**: Restricts directory access entirely to the owner.
- **Short Description**: Modifies permissions to `rwx------`.
- **Expected Result**: Only the user can enter or list files in `project_docs`.

### 5. Secure Configuration Files
- **Command**: `chmod 600 workspace/config/settings.conf`
- **Purpose**: Restricts read and write access to the owner only.
- **Short Description**: Modifies permissions to `rw-------`.
- **Expected Result**: The file becomes invisible/unreadable to groups and others.

### 6. Adjust Report Permissions
- **Command**: `chmod 640 workspace/reports/weekly_report.txt`
- **Purpose**: Allows the owner to read/write, and the group to read, but blocks others.
- **Short Description**: Modifies permissions to `rw-r-----`.
- **Expected Result**: Members of the assigned group can view the report, but outsiders cannot.

### 7. Secure the Logs Directory
- **Command**: `chmod 750 workspace/logs`
- **Purpose**: Allows the owner full access and the group read/execute access, blocking others.
- **Short Description**: Modifies permissions to `rwxr-x---`.
- **Expected Result**: Others cannot view or traverse the logs directory.

### 8. Display Ownership Details
- **Command**: `ls -ld workspace/project_docs`
- **Purpose**: Displays the ownership and group of a specific directory without listing its contents.
- **Short Description**: Long format listing for a directory (`-d`).
- **Expected Result**: Output showing the owner (e.g., `vanshjagetia`) and group (e.g., `staff`).

### 9. View Default Umask
- **Command**: `umask`
- **Purpose**: Displays the current user file-creation mask.
- **Short Description**: Prints the octal umask value.
- **Expected Result**: Output such as `022`.

### 10. Temporarily Change Umask
- **Command**: `umask 077`
- **Purpose**: Changes the default permissions for newly created files to be completely restricted.
- **Short Description**: Sets the umask to `077`.
- **Expected Result**: Command executes silently. Subsequent files created will have `600` permissions.
