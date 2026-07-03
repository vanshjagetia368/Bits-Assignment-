# Question 1: Linux Environment Verification

## Objective
The objective of this section is to perform fundamental Linux environment verification tasks. This includes validating user identity, group affiliations, the shell environment, navigating the file system, listing directory contents, and confirming network connectivity. These steps establish that the environment is correctly configured and ready for administrative operations.

## Files Included
- `Environment_Report.txt`: The main professional report detailing the commands executed, actual outputs, observations, and conceptual explanations.
- `commands.md`: A quick reference guide documenting all the commands utilized during this verification process.
- `README.md`: This file, outlining the purpose of the directory and providing execution instructions.
- `screenshots/`: A directory designated to store the visual evidence of the commands being executed in the terminal.

## How to Reproduce the Experiment
1. Open your terminal emulator (e.g., macOS Terminal, iTerm2, or any Linux shell).
2. Navigate to this directory using the `cd` command:
   ```bash
   cd "Bits Assignment/Question1"
   ```
3. Execute the commands exactly as detailed below and capture the outputs.

## How to Execute Every Command
Execute the following commands sequentially in your terminal:

1. **Verify Username**:
   ```bash
   whoami
   ```
2. **Verify User Groups**:
   ```bash
   groups
   ```
3. **Check Current Shell**:
   ```bash
   echo $SHELL
   ```
4. **Print Working Directory**:
   ```bash
   pwd
   ```
5. **List Files and Directories**:
   ```bash
   ls -la
   ```
6. **Verify Network Connectivity**:
   ```bash
   ping -c 4 8.8.8.8
   ```

## Expected Learning Outcomes
- Understanding how to identify the current user and their associated access groups.
- Comprehending the role of the shell and how to identify the active interpreter.
- Learning file system navigation and interpreting detailed directory listings including permissions and ownership.
- Demonstrating the ability to verify and interpret basic network connectivity metrics (packet loss and RTT).

## Screenshots
The `screenshots/` directory is meant to contain visual evidence of the commands executed. Below are the placeholders for the required screenshots:

- **Screenshot 1**: `whoami` output.
- **Screenshot 2**: `groups` output.
- **Screenshot 3**: `echo $SHELL` output.
- **Screenshot 4**: `pwd` output.
- **Screenshot 5**: `ls -la` output.
- **Screenshot 6**: `ping` output.
