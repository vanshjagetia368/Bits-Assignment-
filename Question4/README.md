# Question 4: File Access and I/O Investigation

## Objective
The objective of this assignment module is to practically investigate how the Linux operating system handles File Input/Output (I/O). By manipulating standard streams (`stdin`, `stdout`, `stderr`), identifying active file descriptors, filtering output with redirection operators, and auditing system resource limits, this module provides the skills necessary to troubleshoot logging issues and application resource exhaustion.

## Folder Structure
```text
Question4/
├── IO_Investigation_Report.txt
├── commands.md
├── README.md
├── screenshots/
└── experiment/
    ├── combined_output.txt
    ├── error.txt
    ├── logfile.txt
    ├── output.txt
    └── sample_input.txt
```

## Files Included
- **`IO_Investigation_Report.txt`**: A comprehensive professional report documenting the scenario, command executions, actual system outputs, and a deep technical analysis of file descriptors and I/O redirection.
- **`commands.md`**: A quick reference markdown guide detailing all the commands used to perform the I/O investigation.
- **`README.md`**: This documentation file, outlining the goals and structure of this question.
- **`screenshots/`**: The designated directory to store all visual evidence captured during command execution.
- **`experiment/`**: The practical directory containing all the target log files and redirection output text files.

## Linux Concepts Demonstrated
1. **File Descriptors**: Understanding integers 0, 1, and 2, and how the kernel maps them to input/output streams.
2. **Process Tracking**: Identifying exactly which background process holds a lock on a file using `lsof`.
3. **Data Redirection**: Utilizing `>`,`>>`, and `2>` to surgically route output and errors.
4. **Combined Logging**: Merging standard error into standard output using `2>&1`.
5. **Resource Limits**: Understanding `ulimit` and how the OS restricts file descriptors and stack memory.

## How to Reproduce the Investigation
All execution steps are detailed in `commands.md`. Navigate into this directory (`cd "Bits Assignment/Question4"`) and run the commands sequentially. Start by creating the experimental log files, investigate the `/dev/fd` directory, test the various redirection operators, and finally check your machine's default `ulimit` settings.

## Expected Learning Outcomes
By completing this task, you will be able to:
- Trace open files back to their parent process ID.
- Successfully capture hidden error messages into dedicated log files.
- Explain why a server might crash with a "Too many open files" error.
- Architect combined logging pipelines for background daemon processes.

## Screenshot Checklist
Please capture the following screenshots and place them in the `screenshots/` directory:

- **Screenshot 01**: Create experiment files (`mkdir` and `touch`).
- **Screenshot 02**: Open file (using `tail -f` in the background).
- **Screenshot 03**: `lsof` output (filtering for `logfile.txt`).
- **Screenshot 04**: File descriptors (`ls -l /dev/fd`).
- **Screenshot 05**: Output redirection (`>` and `>>`).
- **Screenshot 06**: Error redirection (`2>`).
- **Screenshot 07**: Combined output (`2>&1`).
- **Screenshot 08**: Resource limits (`ulimit -a`).
- **Screenshot 09**: Final experiment verification (Listing the populated files in `experiment/`).

## Notes
- `lsof` (List Open Files) is an essential diagnostic tool. If a process is abruptly killed, its file descriptor is automatically released by the kernel.
- The `ulimit` values observed in this experiment are specific to the default restrictions enforced by macOS/BSD on your current user session.
