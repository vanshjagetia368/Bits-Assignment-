# Question 3: File System and Link Analysis

## Objective
The objective of this assignment module is to explore and analyze the core architecture of the Linux/Unix filesystem. By creating, examining, and testing original files, hard links, and symbolic links, this experiment practically demonstrates how metadata and data blocks are linked, stored, and managed through inodes. 

## Folder Structure
```text
Question3/
├── Link_Analysis_Report.txt
├── commands.md
├── README.md
├── screenshots/
└── experiment/
    ├── hardlink.txt
    └── softlink.txt (dangling after experiment)
```

## Files Included
- **`Link_Analysis_Report.txt`**: A comprehensive professional report documenting the experiment setup, execution, metadata collected, and the final analytical comparison between link types.
- **`commands.md`**: A quick reference markdown guide detailing all the commands used to perform the link analysis and metadata collection.
- **`README.md`**: This documentation file, outlining the goals and structure of this question.
- **`screenshots/`**: The designated directory to store all visual evidence captured during command execution.
- **`experiment/`**: The practical directory where the original files and links were created and tested.

## Linux Concepts Covered
1. **Inodes**: Understanding how the OS maps filenames to data blocks.
2. **Hard Links**: Recognizing how multiple directory entries can point to the same physical data.
3. **Symbolic (Soft) Links**: Understanding pointers that link to paths rather than data.
4. **Metadata Management**: Analyzing timestamps, ownership, and sizes using `stat`.
5. **Deletion Mechanisms**: Comprehending how the `rm` command behaves based on inode link counts.

## How to Reproduce the Experiment
All execution steps are detailed in `commands.md`. Navigate into this directory (`cd "Bits Assignment/Question3"`) and run the commands sequentially. Start by creating the environment, adding the links, running `ls -li` and `stat` to observe the metadata, and finally executing `rm` to observe the deletion fallout.

## Expected Learning Outcomes
By completing this task, you will be able to:
- Explain what an inode is and what metadata it holds.
- Differentiate between hard links and soft links theoretically and practically.
- Diagnose dangling symbolic links.
- Confidently recover or protect files using hard link backup strategies.

## Screenshot Checklist
Please capture the following screenshots and place them in the `screenshots/` directory:

- **Screenshot 01**: Create original file (`echo` into `original.txt`).
- **Screenshot 02**: Create hard link (`ln` command).
- **Screenshot 03**: Create symbolic link (`ln -s` command).
- **Screenshot 04**: Display inode numbers (`ls -li`).
- **Screenshot 05**: Display metadata (`stat` command).
- **Screenshot 06**: Delete original file (`rm original.txt`).
- **Screenshot 07**: Hard link after deletion (`cat hardlink.txt`).
- **Screenshot 08**: Broken symbolic link (`cat softlink.txt`).
- **Screenshot 09**: Final experiment verification (`ls -li` showing dangling link).

## Notes
- To accurately retrieve detailed Linux-style metadata on macOS, the `stat -x` command is utilized instead of standard GNU `stat`.
- The `original.txt` file is intentionally missing from the final repository state, as its deletion is the core proof of the experiment.
