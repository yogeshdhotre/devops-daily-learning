# Linux Day 02 - Permissions, Users & Ownership

##1.What are Linux Permissions?
-Linux is a permission-based operating system.
-Every file and directory has access control rules that define:

-Who can read the file
-Who can modify the file
-Who can execute the file
Permissions are used to secure the system and prevent unauthorized access.

##2.Permission Structure in Linux
-Permissions can be viewed using:
-ls -l
-Example:o/p
  -rwxr-xr-- 1 yogesh dev 245 Feb 20 file.txt
Breakdown:

- → File type (d = directory, - = file)
rwx → Owner permissions
r-x → Group permissions
r-- → Others permissions
yogesh → Owner
dev → Group

-Linux divides permissions into three user categories:

1.Owner
2.Group
3.Others
3.Permission Meaning

##3.Each permission has a numeric value:

r (read) = 4
w (write) = 2
x (execute) = 1

Examples:
7 = rwx
6 = rw-
5 = r-x
4 = r--

##4.Change permission using numeric system:
chmod 755 file.sh

Meaning:
Owner → rwx
Group → r-x
Others → r-x

##5.Symbolic Permission System
-Permissions can also be changed using symbols.
-Examples:
chmod u+x file.sh
chmod g-w file.txt
chmod o+r file.txt
chmod a+r file.txt

Symbols:

u → user
g → group
o → others
a → all

##6.What is Ownership in Linux?
-Each file in Linux has:
 One Owner (User)
 One Group

Check ownership:
ls -l

Change file owner:
sudo chown username file.txt

Change owner and group:
sudo chown username:group file.txt

Change only group:
sudo chgrp groupname file.txt

##7.User Management in Linux
-Create a new user:
sudo useradd username

-Set password:
sudo passwd username

-Check all users:
cat /etc/passwd

-Count total users:
cat /etc/passwd | wc -l

-All system users are stored in:
/etc/passwd

##8.Group Management in Linux
-Create a new group:
sudo groupadd dev

-Check all groups:
cat /etc/group

-Groups are stored in:
/etc/group

##9.Types of Groups in Linux
-Linux has two types of groups:

1.Primary Group
-Assigned when user is created
-Only one primary group

2.Secondary Group
-Additional groups
-A user can belong to multiple secondary groups

##10.Adding User to Group

-Add user to a secondary group:
sudo usermod -aG dev username

Important:
-a → append (keeps existing groups)
-G → secondary groups

-Check which groups a user belongs to:

groups username

##11.Deleting Users and Groups
Delete user:
I now understand why permission management is critical in server administration and cloud environments like AWS EC2.sudo userdel username

I understood the difference between primary and secondary groups.
Delete user with home directory:
sudo userdel -r username
I practiced creating users and groups manually.
I learned how numeric and symbolic permission systems work.

Today I understood Linux permissions, ownership, and user management in depth.
Delete group:
