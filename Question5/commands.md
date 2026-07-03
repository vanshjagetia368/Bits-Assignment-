# Storage Health Assessment Command Reference

This document serves as a quick reference for the commands utilized during the Storage Health Assessment.

### 1. View Available Storage Devices and Partitions
- **Command**: `diskutil list`
- **Purpose**: Displays the hierarchical structure of physical disks, logical containers, and synthesized volumes.
- **Description**: This is the macOS equivalent of the Linux `lsblk` and `fdisk -l` commands. It reads the partition tables and displays the sizes and identifiers of all connected storage hardware.
- **Expected Result**: A detailed list of all physical and logical drives (e.g., `disk0`, `disk2s1`).

### 2. View Mounted Filesystems
- **Command**: `mount | head -n 10`
- **Purpose**: Displays currently mounted filesystems and their specific mount configurations.
- **Description**: The `mount` command reads the active mount tables. The output shows the device, the mount point, and the options (like `read-only`, `local`, `journaled`). `head` is used to limit the output to the most relevant top lines.
- **Expected Result**: A list showing the root filesystem `/` and virtual filesystems like `devfs`.

### 3. Measure Disk Usage
- **Command**: `df -h`
- **Purpose**: Reports the amount of available and used disk space on all mounted filesystems.
- **Description**: The `-h` flag ensures the output is printed in "human-readable" format (Gigabytes/Megabytes instead of raw byte blocks).
- **Expected Result**: A table displaying Size, Used, Avail, and Capacity percentage for each mount point.

### 4. Measure Inode Utilization
- **Command**: `df -i`
- **Purpose**: Reports the number of used and free inodes on the filesystems.
- **Description**: Instead of measuring data blocks, the `-i` flag measures the metadata index nodes. This is crucial for detecting situations where a disk runs out of file slots before running out of data space.
- **Expected Result**: A table displaying `iused`, `ifree`, and `%iused`.

### 5. Inspect Storage Health (SMART Status)
- **Command**: `diskutil info disk0 | grep SMART`
- **Purpose**: Queries the hardware controller for its internal health diagnosis.
- **Description**: Uses `diskutil info` to pull deep hardware metrics for the primary physical disk, and pipes (`|`) the output into `grep` to filter exclusively for the "SMART Status" line. (The Linux equivalent would typically be `smartctl -a /dev/sda`).
- **Expected Result**: A line outputting `SMART Status: Verified`.
