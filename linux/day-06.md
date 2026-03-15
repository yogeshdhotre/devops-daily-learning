# Linux Day 06 – Text Processing & File Editing
## 1.Text Editors in Linux

Linux provides multiple terminal-based text editors used to create and edit files.

Vim

vim is an advanced and powerful text editor widely used by developers and system administrators.

Basic command:

vim filename.txt

Important modes:

1.Normal Mode

Used for navigation and commands

2.Insert Mode

Used for writing text

Press i to enter insert mode

3.Command Mode

Used for saving and exiting

Press : to enter command mode

Important commands:

i      → insert text
Esc    → exit insert mode
:w     → save file
:q     → quit
:wq    → save and quit
:q!    → quit without saving
Nano

nano is a simple and beginner-friendly text editor.

Open file:

nano file.txt

Common shortcuts:

Ctrl + O   → save file
Ctrl + X   → exit editor
Ctrl + K   → cut line
Ctrl + U   → paste line
## 2.Basic File Viewing Commands
cat

Displays file content in the terminal.

cat file.txt

Create file:

cat > file.txt

Append content:

cat >> file.txt
head

Shows the first lines of a file.

head file.txt

Show first 5 lines:

head -5 file.txt
tail

Shows the last lines of a file.

tail file.txt
tail -f

Used for real-time log monitoring.

Example:

tail -f /var/log/syslog

Commonly used for monitoring application or system logs.

## 3.Text Processing Commands

Linux provides powerful tools for searching and processing text data.

grep

Searches for specific text inside files.

Example:

grep "error" logfile.txt

Useful options:

grep -i   → ignore case
grep -n   → show line numbers
grep -r   → recursive search

Example:

grep -i "linux" file.txt
awk

Used for pattern scanning and column-based text processing.

Example:

awk '{print $1}' file.txt

Print multiple columns:

awk '{print $1,$3}' file.txt

Example with system command:

df -h | awk '{print $1,$5}'
sed

sed is a stream editor used to modify text automatically.

Replace word:

sed 's/old/new/' file.txt

Replace all occurrences:

sed 's/old/new/g' file.txt

Edit file directly:

sed -i 's/old/new/g' file.txt
wc

Counts lines, words, and characters in a file.

Example:

wc file.txt

Options:

wc -l → line count
wc -w → word count
wc -c → character count
sort

Sorts lines in a file alphabetically.

sort file.txt

Reverse order:

sort -r file.txt
uniq

Removes duplicate lines.

uniq file.txt

Often used with sort:

sort file.txt | uniq
cut

Extracts specific columns from text.

Example:

cut -d " " -f1 file.txt

Explanation:

-d → delimiter
-f → field
## 4.Pipe Operator

The pipe | sends output of one command as input to another command.

Example:

cat file.txt | grep linux

Another example:

ps aux | grep nginx

Pipe is widely used in Linux automation and DevOps workflows.

## 5.Remote Access in Linux
SSH

SSH (Secure Shell) is used to connect securely to remote servers.

Example:

ssh user@server-ip

Example:

ssh ubuntu@192.168.1.10

SSH encrypts communication between client and server.

SSH Key Generation

SSH keys allow passwordless authentication.

Generate key:

ssh-keygen

Default key location:

~/.ssh/id_rsa

Copy key to server:

ssh-copy-id user@server-ip
SCP

scp is used to securely copy files between systems.

Copy file to server:

scp file.txt user@server-ip:/home/user/

Copy file from server:

scp user@server-ip:/home/user/file.txt .
rsync

rsync is used for efficient file synchronization.

Example:

rsync -av file.txt user@server-ip:/home/user/

Common options:

-a → archive mode
-v → verbose output

Used widely for backups and server synchronization.

~/.ssh/config

SSH configuration file used to simplify remote connections.

Location:

~/.ssh/config

Example configuration:

Host myserver
    HostName 192.168.1.10
    User ubuntu
    IdentityFile ~/.ssh/id_rsa

Now you can connect simply using:

ssh myserver
## 6.Reflection

Today I learned about Linux text processing tools and terminal-based file editors.

Commands like grep, awk, sed, and cut help in searching, filtering, and manipulating text data. These tools are very useful for log analysis and automation tasks in DevOps.

I also practiced remote access commands such as ssh, scp, and rsync, which are commonly used to manage remote Linux servers.

Understanding these commands is important for working with cloud servers and real production environments.