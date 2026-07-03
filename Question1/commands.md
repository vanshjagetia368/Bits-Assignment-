# Linux Environment Command Reference

This file serves as a quick command reference for the Linux Environment Verification tasks.

### 1. Username
- **Command**: `whoami`
- **Short Description**: Prints the effective username.
- **Purpose**: To determine the currently logged-in user on the system.
- **Expected Output**: The username (e.g., `vanshjagetia`).

### 2. User Groups
- **Command**: `groups`
- **Short Description**: Prints group memberships.
- **Purpose**: To determine every group the current user belongs to.
- **Expected Output**: A space-separated list of group names (e.g., `staff admin everyone`).

### 3. Current Shell
- **Command**: `echo $SHELL`
- **Short Description**: Prints the current shell path.
- **Purpose**: To determine the current shell being used for the session.
- **Expected Output**: The absolute path to the shell executable (e.g., `/bin/zsh` or `/bin/bash`).

### 4. Present Working Directory
- **Command**: `pwd`
- **Short Description**: Print working directory.
- **Purpose**: To determine the current absolute path of the directory in the file system.
- **Expected Output**: The full path to the current directory (e.g., `/Users/vanshjagetia/Desktop/Bits Assignment/Question1`).

### 5. Files and Directories
- **Command**: `ls -la`
- **Short Description**: Lists all directory contents in long format.
- **Purpose**: To list all files and directories, including hidden ones, with their detailed permissions and metadata.
- **Expected Output**: A detailed list containing file types, permissions, link counts, owner, group, size, date, and filename.

### 6. Network Connectivity Verification
- **Command**: `ping -c 4 8.8.8.8`
- **Short Description**: Sends ICMP echo requests.
- **Purpose**: To verify internet connectivity by sending packets to an external server.
- **Expected Output**: Network statistics showing packets transmitted, received, packet loss percentage, and round-trip times.
