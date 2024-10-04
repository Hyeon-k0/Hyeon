# Command Line Interface (CLI) Lecture Notes

The Command Line Interface (CLI) is a powerful tool for interacting with a computer system. It allows users to execute commands, manage files, control permissions, and automate tasks. This guide covers essential CLI topics such as I/O redirection, pipelines, permissions, superuser privileges, text editors, shell scripting, and useful command-line tools like `wget`, `curl`, and `grep`.

## I/O Redirection
I/O Redirection allows users to control where command inputs and outputs come from and go to.

- **Input Redirection**: The `<` symbol takes input from a file instead of the keyboard. 
  For example, you can feed input from a file into a command that expects user input interactively.

- **Output Redirection**: The `>` symbol redirects command output to a file, overwriting the file if it already exists. If you want to append the output to an existing file without overwriting, use `>>`.

- **Error Redirection**: The `2>` symbol is used to redirect error messages (stderr) to a file, separating them from the normal output (stdout). You can also redirect both stdout and stderr using `&>`.

## Pipelines
Pipelines (`|`) allow you to connect multiple commands by passing the output of one command as input to another. This is useful for chaining commands together to process data in steps. For example, you can list files and filter the results using `grep` by writing `ls | grep "pattern"`.

## Permissions
Permissions in the CLI control who can read, write, or execute a file or directory. There are three types of permissions:

- **Read (r)**: Allows reading the file or directory contents.
- **Write (w)**: Allows modifying or deleting the file or directory.
- **Execute (x)**: Allows running the file as a program (for files) or entering the directory (for directories).

Permissions are represented as a series of three groups: owner, group, and others. For example, `rwxr-xr--` means the owner has read, write, and execute permissions, the group has read and execute permissions, and others have read-only permissions.

## Changing Permissions
You can change the permissions of a file or directory using the `chmod` command. For example, to give the owner full permissions (read, write, execute) and others read and execute permissions, you can use `chmod 755 filename`. You can also add or remove specific permissions using symbolic notation, such as `chmod u+x filename` to add execute permission for the owner.

## Superuser (Root)
The superuser, or root, has elevated privileges, allowing them to perform administrative tasks like installing software, changing system settings, and managing users.

To execute a command as the superuser, use `sudo`. For example, `sudo command` allows a regular user to temporarily gain superuser privileges to run a single command. You can also start a root session with `sudo -i` or switch to the root user with `su`.

## Text Editors
Text editors are used to create and edit files from the command line.

- **nano**: A simple, user-friendly text editor. It's easy to learn and commonly available in most Linux distributions.
- **vim**: A more powerful editor with different modes for inserting text and navigating. It has a steeper learning curve but is favored by many advanced users.
- **emacs**: A highly customizable editor that can be extended with various packages and features.

## Shell Scripts
A shell script is a file containing a sequence of commands that can be executed as a script to automate tasks. Scripts typically start with a "shebang" (`#!/bin/bash`), which tells the system which interpreter to use. After that, you can include any sequence of commands, loops, conditionals, and variables.

To run a shell script, make sure the file is executable (`chmod +x script.sh`), then run it with `./script.sh`.

## Downloading Files (wget & curl)
- **wget**: A simple tool for downloading files from the web. Use `wget URL` to download a file from the specified URL.
- **curl**: A more flexible tool that can send data to and from a server. To download a file with `curl`, use `curl -O URL`. You can also retrieve just the headers of a webpage using `curl -I URL`.

## Searching with grep
The `grep` command is used to search for patterns in files. For example, `grep "pattern" filename` searches for lines containing the pattern in the specified file. Common options include:

- `-i`: Ignore case sensitivity.
- `-r`: Recursively search directories.
- `-v`: Invert match to find lines that do not contain the pattern.
- `-n`: Show line numbers alongside matching lines.

For example, `grep -i "error" logfile.txt` will search for "error" in the log file, ignoring case sensitivity.
