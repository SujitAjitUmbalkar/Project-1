# Customised Virtual File System in C Language 
Project-1st 

This project is a simplified Virtual File System (VFS) implemented in C. It provides a command-line interface to perform basic file system operations such as creating, reading, writing, and deleting files within a virtual environment. This project is a great learning tool for understanding fundamental file system concepts like inodes, superblocks, and file descriptors.


About the Project 🤔
This Virtual File System is a pedagogical tool designed to simulate the core functions of a real file system without interacting with the underlying operating system's kernel. The entire file system—including its directory structure, files, and data—is managed in the program's memory. This approach allows developers to explore and manipulate file system components like inodes and data blocks directly, providing a clear understanding of how files are stored and accessed at a low level.

Advantages of a Virtual File System ✨
Safety and Isolation: The VFS operates in its own isolated memory space. Any changes, errors, or data corruption within the VFS do not affect the host operating system's file system. This makes it a safe environment for experimentation and learning.

Educational Value: It provides a hands-on experience for understanding complex concepts like file allocation, data structures (e.g., inodes, superblocks), and the flow of file operations (e.g., open, read, write). This knowledge is directly applicable to kernel-level programming and systems engineering.

Cross-Platform Portability: Since the VFS is a self-contained application, it can be compiled and run on any platform that supports a C compiler (like Windows, Linux, macOS). It doesn't rely on platform-specific APIs for file management.

Performance Analysis: A VFS can be used to test and analyze different file allocation schemes or data retrieval algorithms without the overhead of disk I/O. This makes it an ideal environment for benchmarking different approaches to file storage.

Debugging and Development: It provides a controlled and predictable environment for testing applications that require file I/O. Developers can simulate various file system states, such as a full disk or corrupted files, to test how their programs handle edge cases.

Features 🚀
The VFS supports the following commands, emulating a standard shell environment:

create: Create a new regular file with specified permissions.

open: Open an existing file.

read: Read data from an open file.

write: Write data to an open file.

ls: List all files in the virtual file system.


stat: Display statistical information about a file using its name.

fstat: Display statistical information about a file using its file descriptor.

truncate: Remove all data from a file, but keep the file itself.

rm: Delete a file from the VFS.

close: Close a specific opened file.

closeall: Close all opened files.

lseek: Change the file offset for an open file.

man: Display the manual page for a specific command.

help: Display a list of all available commands.

clear: Clear the console screen.

exit: Terminate the virtual file system application.

Data Structures 💻
The project utilizes several key data structures to mimic a real file system.

SUPERBLOCK: Manages the overall state of the file system, including the total number of inodes and the number of free inodes available.

INODE: The core of the file system. Each inode represents a file and stores metadata such as the file name, size, type, permissions, and a pointer to the file's data buffer.

FILETABLE: Tracks information about open files, including read/write offsets, mode, and a reference to its corresponding inode.

UFDT (User File Descriptor Table): An array that serves as the mapping between a user's file descriptors and the open file entries in the file table.

How to Compile and Run ▶️
Prerequisites
A C/C++ compiler (e.g., GCC, MinGW)

Compilation
Navigate to the project directory and compile the C code using GCC.

Bash

gcc -o vfs_project vfs_project.c
Execution
Run the compiled executable from your terminal.

Bash

./vfs_project
This will launch the VFS command-line interface, where you can start interacting with the virtual file system.

Command Usage Example ⌨️
Here is a quick example of how to use the commands:

Create a file with read and write permissions:

Marvellous VFS : > create my_notes.txt 3
File is successfully created with the discriptor : 0
Write some content to the file:

Marvellous VFS : > write my_notes.txt
Enter the data :
Hello, this is my first virtual file!
Read the content from the file:

Marvellous VFS : > read my_notes.txt 100
Hello, this is my first virtual file!
List all files:

Marvellous VFS : > ls

File Name       Inode number    File size       Link count
---------------------------------------------------
my_notes.txt    1               35              1
-----------------------------------------------------
View file stats:

Marvellous VFS : > stat my_notes.txt

----------Statical Information about File----------------
File name : my_notes.txt
Indode Number : 1
File size : 2048
Actual File size : 35
Link count : 1
Reference count : 1
File Permission : Read & Write
-----------------------------------------------------------------
