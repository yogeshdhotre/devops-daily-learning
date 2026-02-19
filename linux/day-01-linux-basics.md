# Linux Day 01 - Fundamentals

## 1.What is an Operating System?
An Operating System (OS) is system software that manages hardware and software resources and provides services for programs.

### Core Responsibilities of OS:

1.Process Management
   - Handles running programs
   - Controls CPU scheduling

2.Memory Management
   - Allocates RAM to processes
   - Manages virtual memory

3.File System Management
   - Organizes files and directories
   - Controls access permissions

4.Device Management
   - Manages hardware like disk, keyboard, network

5.Security and User Management
   - Handles authentication
   - Manages permissions

## 2.What is Linux?
Linux is an open-source, Unix-like operating system widely used in servers, cloud environments, and DevOps.
Most cloud platforms like AWS use Linux-based servers.

## 3.What Exists Inside a Linux OS?

1.Linux Kernel
   - Core of the system
   - Manages hardware and system resources

2.Shell
   - Interface between user and kernel
   - Example: bash

3.System Utilities
   - Commands like ls, cd, cp

4.Package Manager
   - Used to install software 
   - Example: apt, yum

5.File System
   -Provides hierarchical directory structure for organizing files
   - Example:/home, /etc

6.Optional Graphical Interface (GUI)
   - Not required for servers

## 4.Why Linux is Important?

- Used in Cloud (AWS EC2)
- Used in DevOps
- Used in Servers and Data Centers
- More secure and stable than many desktop OS
- Command-line driven (important for automation)
Most AWS EC2 instances run on Linux, so understanding Linux is essential for Cloud and DevOps roles.

## 5.Linux Architecture

Hardware
↓
Kernel
↓ 
Shell
↓
Utilities
↓
Applications

Example:

Hardware → Physical components like CPU, RAM, Disk

Kernel → Core of Linux, manages hardware and system resources

Shell → Interface where user types commands (bash)

Utilities → Commands like ls, cd, cp

Applications → Programs running on top (nginx, mysql, etc.)

## 6.Linux File System Structure

/        → Root directory
/home    → User home directories
/root    → Root user home
/bin     → Essential system binaries
/etc     → Configuration files
/usr     → User programs and libraries
/var     → Logs and variable data
/tmp     → Temporary files

## 7.Basic Commands Practiced

Today I practiced basic navigation commands:

pwd        → Show current directory
ls         → List files and folders
ls -l      → Detailed list with permissions
cd         → Change directory
mkdir      → Create directory
touch      → Create file
rm         → Remove file
cat        → View file content

Example Practice:

mkdir linux-practice
cd linux-practice
touch file1.txt
echo "Hello Linux" > file1.txt
cat file1.txt
rm file1.txt
cd ..
rmdir linux-practice

## 8.Important Linux Rules

1.Linux is Case-Sensitive
   File.txt ≠ file.txt

2.Linux is Permission-Based
   Every file has read, write, execute permissions

3.Linux is Command-Driven
   Most server operations are done via terminal

## 9.Reflection

Today I understood the core responsibilities of an Operating System and how Linux is structured internally.

I now understand the flow:
User → Shell → Kernel → Hardware.

I practiced basic navigation commands, but I still need more speed and confidence while moving between directories.
Tomorrow I will focus more on hands-on file operations.
