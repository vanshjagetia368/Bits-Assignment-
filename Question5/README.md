# Question 5: Storage Health Assessment and Documentation

## Objective
The objective of this assignment module is to practically evaluate the storage infrastructure of a Linux/Unix system. By auditing physical block devices, logical volumes, active mount points, data block utilization, inode consumption, and hardware SMART health, this module provides the foundational skills necessary to maintain system stability and plan for infrastructure deployments.

## Folder Structure
```text
Question5/
├── Storage_Assessment_Report.txt
├── commands.md
├── README.md
├── screenshots/
└── notes/
```

## Files Included
- **`Storage_Assessment_Report.txt`**: A comprehensive, professional system administration report documenting the storage architecture, capacity constraints, inode health, and technical recommendations. **Note: Created and saved using the `vi` text editor as per assignment requirements.**
- **`commands.md`**: A quick reference markdown guide detailing all the commands used to perform the storage audit.
- **`README.md`**: This documentation file, outlining the goals and structure of this question.
- **`screenshots/`**: The designated directory to store all visual evidence captured during command execution.
- **`notes/`**: A directory allocated for temporary or raw observational data.

## Linux Storage Concepts Covered
1. **Block Devices vs. Partitions**: Differentiating between raw hardware and logical slices.
2. **Mount Points**: Understanding how the OS maps physical storage to directory trees (e.g., `/`).
3. **Data Block Usage (`df -h`)**: Tracking actual bytes consumed and capacity planning.
4. **Inode Exhaustion (`df -i`)**: Understanding how millions of small files can break a filesystem even with gigabytes of free space.
5. **Hardware Health (SMART)**: Relying on hardware-level self-diagnostics to predict drive failure before it happens.
6. **Command Line Text Editing (`vi`)**: Utilizing standard Unix text editors for remote server administration.

## How to Reproduce the Investigation
All execution steps are detailed in `commands.md`. Navigate into this directory (`cd "Bits Assignment/Question5"`) and run the commands sequentially. Start by investigating the disk layout, audit the mount points, check usage metrics, and finally verify the hardware SMART status. 

## Expected Learning Outcomes
By completing this task, you will be able to:
- Identify near-full partitions before they cause application crashes.
- Explain why a server might be unable to create new files despite having free disk space.
- Audit mounted filesystems and their permissions (e.g., read-only roots).
- Perform basic hardware failure prediction.
- Navigate, edit, and save text files entirely from the terminal using `vi`.

## Screenshot Checklist
Please capture the following screenshots and place them in the `screenshots/` directory:

- **Screenshot 01**: Open vi editor (Showing the terminal screen inside `vi`).
- **Screenshot 02**: Available storage devices (`diskutil list`).
- **Screenshot 03**: Mounted filesystems (`mount`).
- **Screenshot 04**: Disk usage (`df -h`).
- **Screenshot 05**: Inode utilization (`df -i`).
- **Screenshot 06**: Partition information (Can be combined with Screenshot 02).
- **Screenshot 07**: Storage health command (`diskutil info disk0 | grep SMART`).
- **Screenshot 08**: Storage report inside vi (Showing the report text inside the editor).
- **Screenshot 09**: Final project verification (Git status or final directory listing).

## Notes
- macOS utilizes the APFS (Apple File System) and synthesized containers, which results in a highly abstracted storage layout compared to traditional Linux `ext4` partitions.
- Standard GNU/Linux utilities like `lsblk`, `fdisk`, and `smartctl` are replaced by the native macOS `diskutil` utility to accurately retrieve local hardware information without fabricating data or installing unauthorized third-party binaries.
