# Linux Day 05 - Package Management
## 1.What is a Package?

A package in Linux is a compressed file that contains:

Software program

Required libraries

Configuration files

Metadata information

Packages make software installation easier because everything needed for the application is bundled together.

Example packages:

nginx

git

docker

python

Instead of compiling software manually, Linux allows installing software using packages.

## 2.What is a Package Manager?

A Package Manager is a tool used to install, update, remove, and manage software packages in Linux.

It automates the process of:

Downloading software

Installing dependencies

Updating packages

Removing packages

Without a package manager, installing software on Linux would be much more complex.

## 3.Popular Package Managers

Different Linux distributions use different package managers.

Distribution	Package Manager
Ubuntu / Debian	apt
Amazon Linux / CentOS / RHEL	yum / dnf
Arch Linux	pacman

Examples:

Ubuntu:

sudo apt install nginx

Amazon Linux:

sudo yum install nginx
## 4.Key Responsibilities of Package Management

Package managers perform several important tasks.

1.Install Software
Download and install packages from repositories.

2.Resolve Dependencies
Automatically install required libraries needed by the software.

3.Update Software
Upgrade installed packages to newer versions.

4.Remove Software
Uninstall packages that are no longer needed.

5.Maintain System Stability
Ensure packages are compatible with the system.

## 5.What is a Repository?

A repository is an online storage location where Linux packages are stored.

The package manager downloads software from these repositories.

Example repository types:

Official distribution repositories

Third-party repositories

Local repositories

When you run:

sudo apt update

Your system updates the list of available packages from repositories.

## 6.What is a Dependency?

A dependency is a software library required for another program to work.

Example:

If a program requires certain libraries to run, those libraries must be installed first.

Package managers automatically install dependencies.

This prevents errors caused by missing libraries.

## 7.Where Packages are Stored in Linux

After installation, different parts of a package are stored in different locations.

Common locations:

Directory	Purpose
/usr/bin	Executable program files
/etc	Configuration files
/var/log	Application logs
/usr/lib	Libraries required by software

Example:

The nginx configuration file is stored in:

/etc/nginx
## 8.Remove a Package

Linux allows removing installed packages.

Example:

sudo apt remove nginx

This removes the program but keeps configuration files.

Remove Package Completely

To remove software including configuration files:

sudo apt purge nginx

This completely removes the package from the system.

## 9.Fix Broken Packages

Sometimes installations fail due to missing dependencies.

Linux provides a command to fix broken packages.

sudo apt --fix-broken install

This installs missing dependencies and repairs package issues.

## 10.Lab Practice

Today I practiced basic package management commands.

Check Linux Distribution
cat /etc/os-release

Update Package List
sudo apt update

Check Upgradable Packages
apt list --upgradable

Install nginx
sudo apt install nginx -y

Check nginx version:
nginx -v

Check nginx Service Status
systemctl status nginx

Check nginx Port
ss -tulnp | grep 80

Remove nginx
sudo apt remove nginx -y

Remove nginx Completely
sudo apt purge nginx -y

Install Specific Version
sudo apt install nginx=<version>

List Installed Packages
dpkg -l | grep nginx

## 12.Reflection

Today I learned how Linux manages software using package managers.

I practiced:

Installing packages

Updating packages

Removing software

Fixing broken packages

Checking services and ports

Understanding package management is important because Linux servers depend heavily on repositories and package managers to maintain software.