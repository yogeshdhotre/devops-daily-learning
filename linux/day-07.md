# Linux Day 07 - File Archiving and Compression
## 1.What is Archiving?

Archiving means combining multiple files or directories into a single file.

It helps in organizing files and making backups easier.

Important points:

Archiving does not reduce file size

It only packages multiple files together

Commonly used when transferring or backing up files

Example:

10 files → combined into → archive.tar

## 2.What is Compression?

Compression means reducing the size of files to save storage space and improve transfer speed.

Benefits of compression:

Saves disk space

Faster file transfer

Efficient backups

Example:

file.txt → compressed → file.txt.gz

## 3.Difference Between Archiving and Compression

Archiving and compression are often used together but they are different.

Archiving

Combines multiple files

Does not reduce file size

Example tool: tar

Compression

Reduces file size

Can be applied to single or archived files

Example tools: gzip, zip

Example workflow:

Files → tar → archive.tar
archive.tar → gzip → archive.tar.gz

## 4.tar Command (Archiving Tool)

tar stands for Tape Archive.

It is used to combine multiple files into one archive file.

Create an archive:

tar -cvf archive.tar file1.txt file2.txt

Explanation:

c → create archive
v → verbose (shows files being processed)
f → archive file name

Example:

tar -cvf backup.tar file1.txt file2.txt

Archive a directory:

tar -cvf project.tar myfolder/

Extract archive:

tar -xvf archive.tar

x → extract files

## 5.gzip Command (Compression Tool)

gzip is used to compress files in Linux.

Compress a file:

gzip file.txt

Output:

file.txt.gz

Decompress file:

gunzip file.txt.gz

or

gzip -d file.txt.gz
## 6.zip and unzip Commands

zip is used for archiving and compression together.

Create a zip file:

zip file.zip file1.txt file2.txt

Example:

zip files.zip file1.txt file2.txt

Extract zip file:

unzip file.zip
## 7.Archiving and Compression Together

In Linux, archiving and compression are often used together.

Example:

tar -czvf archive.tar.gz folder/

Explanation:

c → create archive
z → compress with gzip
v → verbose
f → file name

Extract compressed archive:

tar -xzvf archive.tar.gz
## 8.Commands Practiced Today

Today I practiced archiving and compression commands.

Commands used:

tar -cvf archive.tar file1.txt file2.txt
tar -xvf archive.tar
gzip file.txt
gunzip file.txt.gz
zip file.zip file1.txt file2.txt
unzip file.zip

Example Practice:

touch file1.txt file2.txt
tar -cvf archive.tar file1.txt file2.txt
gzip file1.txt
zip files.zip file1.txt file2.txt
unzip files.zip
tar -xvf archive.tar
## 9.Important Points to Remember

1.Archiving combines multiple files into one file

2.Compression reduces file size

3.tar is used for archiving

4.gzip is used for compression

5.zip performs archiving and compression together

Most commonly used Linux archive format:

.tar.gz
## 10.Reflection

Today I learned how Linux handles file archiving and compression.

I understood the difference between archiving and compression and practiced commands like tar, gzip, and zip.

I also learned how to create and extract archive files.
This is useful for backups, file transfers, and managing large numbers of files in Linux systems.