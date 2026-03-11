# Linux Day 02 – File Operations, Permissions & User Management
## 1. Basic File & Directory Commands

Today I practiced important Linux commands used to manage files and directories.

pwd
Shows the current working directory.

Example:

pwd

ls
Lists files and directories.

ls

ls -l
Shows detailed list including permissions, owner, size, and date.

ls -l

cd
Used to change directory.

Examples:

cd foldername
cd ..
cd ~

Meaning:

Command	Meaning
cd folder	Go inside folder
cd ..	Go back one directory
cd ~	Go to home directory
## 2. Creating and Removing Directories

mkdir
Creates a directory.

mkdir myfolder

rmdir
Removes an empty directory.

rmdir myfolder
## 3. File Operations

cp – Copy files

cp file1.txt file2.txt

mv – Move or rename files

mv file1.txt newfile.txt

rm – Remove a file

rm file1.txt

rm -r – Remove directory recursively

rm -r foldername

Important:
rm -r permanently deletes files and directories.

## 4. Understanding Linux Permissions

Linux is a permission-based system. Every file and directory has permissions that control who can read, write, or execute it.

Example output of:

ls -l

Example:

-rwxr-xr-- 1 yogesh dev 120 Mar 5 file.sh

Breakdown:

Section	Meaning
-	File type
rwx	Owner permissions
r-x	Group permissions
r--	Others permissions

Permission types:

Symbol	Meaning
r	Read
w	Write
x	Execute
5. Numeric Permission System

Permissions can also be represented using numbers.

Permission	Value
Read	4
Write	2
Execute	1

Examples:

Numeric	Meaning
7	rwx
6	rw-
5	r-x
4	r--

Example command:

chmod 755 file.sh

Meaning:

Owner → rwx
Group → r-x
Others → r-x

## 6. Symbolic Permission Method

Permissions can also be modified using symbols.

Examples:

chmod u+x file.sh
chmod g-w file.sh
chmod o+r file.sh

Meaning:

Symbol	Meaning
u	User
g	Group
o	Others
## 7. Ownership in Linux

Each file has:

Owner

Group

Example:

ls -l

Output shows owner and group.

Example:

-rw-r--r-- 1 yogesh dev file.txt

Owner → yogesh
Group → dev

## 8. Changing Ownership

chown command is used to change file owner.

Example:

sudo chown user file.txt

Change owner and group:

sudo chown user:group file.txt
## 9. User Management in Linux

Linux supports multiple users for security and system management.

Create a User
sudo useradd username

Set password:

sudo passwd username
Check Existing Users

Users are stored in:

/etc/passwd

Command:

cat /etc/passwd
## 10. Group Management

Groups allow multiple users to share permissions.

Create a Group
sudo groupadd groupname
Add User to Group
sudo usermod -aG groupname username
Check User Groups
groups username

or

id username
## 11. Types of Groups

Linux has two types of groups:

Primary Group

Main group assigned to a user.

Secondary Group

Additional groups the user belongs to.

Change User Primary Group
sudo usermod -g groupname username
## 12. Change File Group
sudo chgrp groupname file.txt
## 13. Remove User from Group
sudo gpasswd -d username groupname
## 14. Important Linux Distributions

Some popular Linux distributions:

Ubuntu

Debian

CentOS

Amazon Linux

Red Hat Enterprise Linux

Fedora

Most cloud environments like AWS EC2 use Linux distributions such as Amazon Linux or Ubuntu.

## 15. Reflection

Today I practiced important Linux file operations and user management commands.
I learned how Linux controls access using permissions, ownership, and groups.

I now understand:

File permissions (r, w, x)

Numeric permission system (chmod)

Ownership and groups

Creating users and managing groups

These concepts are critical because Linux servers in cloud environments rely heavily on permission and user management for security.

Tomorrow I will practice more advanced topics like networking commands and system monitoring tools.