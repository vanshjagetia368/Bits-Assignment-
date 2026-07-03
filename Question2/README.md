# Question 2: Secure Project Workspace Setup

## Objective
The objective of this assignment section is to establish a secure, organized workspace for a project team. By practically applying Linux file permissions (`chmod`) and understanding default file creation masks (`umask`), this module demonstrates how to lock down confidential project data, configuration files, and reports from unauthorized system access.

## Folder Structure
```text
Question2/
├── Project_Workspace_Report.txt
├── commands.md
├── README.md
├── screenshots/
└── workspace/
    ├── config/
    │   └── settings.conf
    ├── logs/
    │   └── project.log
    ├── project_docs/
    │   ├── notes.txt
    │   └── requirements.txt
    └── reports/
        └── weekly_report.txt
```

## Files Included
- **`Project_Workspace_Report.txt`**: The comprehensive professional report detailing the scenario, executed commands, actual outputs, permission analyses, and security observations.
- **`commands.md`**: A quick reference markdown guide detailing all the commands used to create the workspace and modify permissions.
- **`README.md`**: This documentation file, outlining the goals and structure of this question.
- **`screenshots/`**: The designated directory to store all visual evidence captured during command execution.
- **`workspace/`**: The practical directory structure created to test and demonstrate Linux permissions.

## Linux Concepts Demonstrated
1. **Directory Management**: Creating nested directory structures efficiently using `mkdir -p`.
2. **File Permissions**: Reading octal and symbolic permissions using `ls -l` and modifying them securely using `chmod`.
3. **Ownership**: Understanding the relationship between the file owner, the group, and the rest of the world.
4. **Umask**: Comprehending how the system calculates default permissions for newly generated files and directories.

## How to Execute the Commands
All execution steps are detailed in `commands.md`. Navigate into this directory (`cd "Bits Assignment/Question2"`) and run the commands sequentially. Start by creating the workspace using `mkdir` and `touch`, view the initial state with `ls -lR`, modify the permissions with `chmod`, and observe the changes.

## Expected Learning Outcomes
By completing this task, you will be able to:
- Architect standard directory structures for Linux applications.
- Interpret the 10-character permission string in a Linux directory listing.
- Apply the Principle of Least Privilege to secure sensitive configuration files.
- Calculate and predict the permissions of new files based on the system `umask`.

## Screenshots Required
Please capture the following screenshots and place them in the `screenshots/` directory:

- **Screenshot 01**: Workspace creation (`mkdir` and `touch`).
- **Screenshot 02**: Directory hierarchy and Initial permissions (`ls -lR workspace` before `chmod`).
- **Screenshot 03**: Permission modification (`chmod` commands).
- **Screenshot 04**: Updated permissions (`ls -lR workspace` after `chmod`).
- **Screenshot 05**: Ownership details (`ls -ld workspace/project_docs`).
- **Screenshot 06**: Umask value (`umask`, `umask 077`, creating a test file, and `ls -l`).

## Notes
Ownership modification commands (`chown` or `chgrp`) generally require root (`sudo`) privileges on Linux systems to prevent severe security risks. Because this environment is operating under standard user privileges, the theoretical concepts are explained in the report, but `chown` was deliberately bypassed in the practical execution to adhere to system constraints.
