# Linux Day 04 - Process and System Monitoring
## 1.What is a Process?

A process is a program that is currently running in the system.

Every running application in Linux becomes a process.

Example:

Opening a browser

Running a script

Executing a command

Each process has:

PID (Process ID) – Unique identifier

CPU usage

Memory usage

User who started the process

Linux allows users and administrators to monitor and control processes.

## 2.Process Monitoring Commands

Linux provides several commands to monitor running processes.

ps

The ps command shows information about running processes.

Example:

ps

Commonly used command:

ps aux

Meaning:

a → show processes of all users

u → display detailed user information

x → show processes not attached to terminal

This command helps identify which programs are running.

## 3.Real-Time System Monitoring
top

The top command displays real-time system activity.

Example:

top

It shows:

CPU usage

Memory usage

Running processes

System load

Press q to exit.

htop

htop is an improved and interactive version of top.

Example:

htop

Features:

Colorful interface

Easier process navigation

Ability to kill processes directly

If not installed:

sudo apt install htop
## 4.Killing a Process

Sometimes a process may freeze or consume too many resources.

Linux provides the kill command to stop processes.

Syntax:

kill PID

Example:

kill 1234

Force kill a process:

kill -9 1234
## 5.Memory Monitoring

Linux provides the free command to check memory usage.

Example:

free -h

-h means human-readable format.

Output shows:

Total memory

Used memory

Free memory

Swap usage

This command is useful for checking RAM usage on servers.

## 6.Disk Space Monitoring
df

The df command shows disk space usage.

Example:

df -h

It displays:

Total disk size

Used disk

Available disk space

du

The du command shows the size of directories.

Example:

du -sh foldername

Example:

du -sh /var/log

This helps identify which folders consume the most disk space.

## 7.System Uptime

The uptime command shows how long the system has been running.

Example:

uptime

Output includes:

Current time

System running time

Number of users logged in

Load average

This helps administrators monitor system stability.

## 8.System Logs with journalctl

Linux systems use systemd journal logs to track system events.

Command:

journalctl

Example:

journalctl -u ssh

This shows logs related to the SSH service.

Logs help diagnose system problems and monitor system behavior.

## 9.Checking Open Ports

The lsof command shows which processes are using network ports.

Example:

lsof -i :80

This displays the process using port 80 (HTTP).

Useful for debugging server applications.

## 10.Background Processes

Linux allows commands to run in the background.

Example:

sleep 100 &

The & symbol sends the process to background.

Check running background jobs:

jobs

Bring process back to foreground:

fg
## 11.Sleep Command

The sleep command pauses execution for a specific time.

Example:

sleep 10

The system waits 10 seconds before continuing.

This command is commonly used in scripts.

## 12.Commands Practiced Today

Today I practiced system monitoring and process management commands:

ps aux
top
htop
kill
free -h
df -h
du -sh
uptime
journalctl
lsof -i :80
sleep
jobs
fg

These commands are important for system administrators and DevOps engineers to monitor servers.

## 13.Reflection

Today I learned how Linux manages running processes and how to monitor system resources.

I practiced commands for:

Viewing running processes

Monitoring CPU and memory usage

Checking disk space

Viewing system logs

Running background processes

These skills are important for managing Linux servers in real-world environments such as cloud platforms like AWS.