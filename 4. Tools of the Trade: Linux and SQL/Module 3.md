# Navigating the Linux File System

The File System Hierarchy Standard (FHS) defines the structure and organization of files and directories.  File locations are described by *file paths*, where levels in the hierarchy are separated by forward slashes (`/`).

## Root Directory

The root directory is the top-level directory in Linux, represented by a single forward slash (`/`). All other directories branch from the root.

## Standard FHS Directories

Located directly under the root directory are standard FHS directories.  Here are some key examples:

*   `/home`:  Contains individual home directories for each user on the system.
*   `/bin`:  (Binaries) Contains executable files (programs).
*   `/etc`:  Stores system configuration files.
*   `/tmp`:  Stores temporary files.  This directory is often targeted by attackers due to its world-writable permissions.
*   `/mnt`:  (Mount) Used for mounting external storage devices like USB drives and hard drives.

**Pro Tip:** Use the command `man hier` to learn more about the FHS and its standard directories.

## User-Specific Subdirectories

Within `/home`, each user has their own directory (e.g., `/home/analyst`, `/home/analyst2`).  Users can further organize their files into subdirectories like `projects`, `logs`, or `reports`.

**Note:**  The tilde (`~`) can represent a user's home directory.  So, `/home/analyst/logs` can also be written as `~/logs`.

## Absolute and Relative File Paths

*   **Absolute File Path:** The complete path starting from the root directory (e.g., `/home/analyst/projects`).
*   **Relative File Path:** The path relative to the current working directory.  Relative paths can use a dot (`.`) for the current directory and two dots (`..`) for the parent directory (e.g., `../projects`).

## Key Navigation Commands

### `pwd`

Prints the current working directory (e.g., `/home/analyst`).

**Pro Tip:** Use the `whoami` command to determine the current user's username.

### `ls`

Lists the files and directories in the current working directory.  You can also use `ls` with an absolute or relative path to list the contents of another directory (e.g., `ls /home/analyst/projects` or `ls projects`).

### `cd`

Changes the current working directory.  Use `cd` followed by a directory name (relative path) to move to a subdirectory (e.g., `cd projects`).  Use `cd` followed by an absolute path to move to any directory (e.g., `cd /home/analyst/logs`).

**Pro Tip:** Use `cd ..` to go up one level in the directory hierarchy.

## Reading File Content

### `cat`

Displays the entire contents of a file (e.g., `cat updates.txt`).

### `head`

Displays the beginning of a file (first 10 lines by default).  Use `head -n <number>` to specify the number of lines (e.g., `head -n 5 updates.txt`).

### `tail`

Displays the end of a file (last 10 lines by default).  Useful for viewing recent log entries.

### `less`

Displays file content one page at a time, allowing for navigation within the file.

*   Spacebar: Move forward one page.
*   `b`: Move back one page.
*   Down arrow: Move forward one line.
*   Up arrow: Move back one line.
*   `q`: Quit.

# Working with `grep` and `find`

This document describes the `grep` and `find` commands, essential tools for searching and filtering data in Linux.

## `grep`

The `grep` command searches a file for lines containing a specified string or pattern and prints those lines.  It typically takes two arguments: the search string (or pattern) and the file to search.

**Example:** `grep OS updates.txt`  This command searches the `updates.txt` file for lines containing "OS" and displays those lines.

**Another Example:** `grep error time_logs.txt` This command searches the `time_logs.txt` file for lines containing "error" and prints them.

## Piping (`|`) with `grep`

The pipe character (`|`) redirects the output of one command as input to another command.  This is a powerful way to combine commands for complex operations.

**Example:** `ls /home/analyst/reports | grep users`

1.  `ls /home/analyst/reports`: Lists the files and directories within the `/home/analyst/reports` directory.
2.  `|`:  The pipe sends the output of the `ls` command to the `grep` command.
3.  `grep users`: Filters the output from `ls`, displaying only the lines (file/directory names) that contain "users".

**Note:** Piping is a general redirection mechanism in Linux and has various uses beyond filtering.

## `find`

The `find` command searches for files and directories based on specified criteria.  It offers a wide range of options for filtering by name, size, modification time, and more.

The basic syntax is: `find <starting_directory> <options>`

The first argument specifies the directory to begin the search. Subsequent arguments define the search criteria.

### `-name` and `-iname`

These options search for files and directories by name. `-name` is case-sensitive, while `-iname` is case-insensitive.  The search string is enclosed in quotes and can include wildcards.

**Example:** `find /home/analyst/projects -name "*log*"`

This command searches the `/home/analyst/projects` directory (and its subdirectories) for files and directories whose names contain "log" (case-sensitive). The asterisks (`*`) act as wildcards, matching any characters before or after "log".

**Example:** `find /home/analyst/projects -iname "*log*"`

This is the same search as above, but case-insensitive.  It will match "log", "Log", "LOG", etc.

### `-mtime`

This option searches for files and directories based on their modification time.  The time is specified in days.

**Example:** `find /home/analyst/projects -mtime -3`

This command finds files and directories in `/home/analyst/projects` that were modified within the last three days.

*   `-mtime +n`: Modified more than *n* days ago.
*   `-mtime -n`: Modified less than *n* days ago.

**Note:** Use `-mmin` instead of `-mtime` to search based on minutes.

# File and Directory Management in Linux

This document summarizes common Linux commands for managing files and directories.

## Directory Management

### `mkdir`

Creates a new directory.  You can specify either an absolute path (starting from the root `/`) or a relative path (starting from your current directory).

**Example:** `mkdir /home/analyst/logs/network` (absolute path) or `mkdir network` (relative path, if you're already in `/home/analyst/logs`).

**Pro Tip:** Use `ls` to confirm the directory creation.

### `rmdir`

Removes an *empty* directory.  It cannot delete directories containing files or subdirectories.

**Example:** `rmdir /home/analyst/logs/network`

## File Management

### `touch`

Creates a new *empty* file.

**Example:** `touch permissions.txt` (creates `permissions.txt` in the current directory).

### `rm`

Removes (deletes) a file.  Use with caution, as recovery is difficult.

**Example:** `rm permissions.txt`

**Pro Tip:** Use `ls` to verify file creation or deletion.

### `mv`

Moves or renames a file or directory.

*   **Moving:** `mv permissions.txt /home/analyst/logs` (moves `permissions.txt` to `/home/analyst/logs`).  The file is removed from its original location.
*   **Renaming:** `mv permissions.txt perm.txt` (renames `permissions.txt` to `perm.txt` in the same directory).

### `cp`

Copies a file or directory.

**Example:** `cp permissions.txt /home/analyst/logs` (copies `permissions.txt` to `/home/analyst/logs`, leaving the original file in place).

## Text Editors

### `nano`

A simple, beginner-friendly command-line text editor.

*   **Opening/Creating:** `nano permissions.txt` (opens `permissions.txt` for editing, or creates it if it doesn't exist).
*   **Saving:** Ctrl + O
*   **Exiting:** Ctrl + X

**Note:** `vim` and `emacs` are other popular command-line text editors.

## Standard Output Redirection

### `>` (Overwrite)

Redirects the output of a command to a file, *overwriting* the file's contents.

**Example:** `echo "time" > permissions.txt` (writes "time" to `permissions.txt`, overwriting any existing content).

### `>>` (Append)

Redirects the output of a command to a file, *appending* the output to the end of the file.

**Example:** `echo "last updated date" >> permissions.txt` (adds "last updated date" to the end of `permissions.txt`).

**Note:** Both `>` and `>>` will create a new file if it doesn't already exist.  Use `>` with care to avoid accidental data loss.

## Linux File Permissions

In Linux, permissions are represented with a 10-character string.  These permissions control access to files and directories.

### Permissions

There are three basic permissions:

*   **read (r):**
    *   *Files:* The ability to read the file contents.
    *   *Directories:* The ability to list the directory contents (including files and subdirectories).
*   **write (w):**
    *   *Files:* The ability to modify the file contents.
    *   *Directories:* The ability to create new files and subdirectories within the directory.
*   **execute (x):**
    *   *Files:* The ability to execute the file (if it's a program).
    *   *Directories:* The ability to enter the directory and access its contents (files and subdirectories).

### Owners

Permissions are assigned to three types of owners:

*   **user (u):** The owner of the file.
*   **group (g):** A group that the owner is a member of.  Other users in this group may have specific permissions.
*   **other (o):** All other users on the system who are not the owner or a member of the file's group.

### The 10-Character Permission String

Each character in the 10-character string conveys specific information about these permissions.  The string is structured as follows:

## Breakdown of the 10-Character Permission String

The 10-character string representing file permissions in Linux can be broken down as follows:

| Character | Example     | Meaning                                                                    |
| :-------- | :---------- | :------------------------------------------------------------------------- |
| 1st       | `d` or `-` | File type: `d` (directory), `-` (regular file), `l` (symbolic link), etc. |
| 2nd       | `r` or `-` | Read permission for the **user** (owner): `r` (has read), `-` (no read)     |
| 3rd       | `w` or `-` | Write permission for the **user**: `w` (has write), `-` (no write)          |
| 4th       | `x` or `-` | Execute permission for the **user**: `x` (has execute), `-` (no execute)      |
| 5th       | `r` or `-` | Read permission for the **group**: `r` (has read), `-` (no read)            |
| 6th       | `w` or `-` | Write permission for the **group**: `w` (has write), `-` (no write)         |
| 7th       | `x` or `-` | Execute permission for the **group**: `x` (has execute), `-` (no execute)     |
| 8th       | `r` or `-` | Read permission for **others**: `r` (has read), `-` (no read)               |
| 9th       | `w` or `-` | Write permission for **others**: `w` (has write), `-` (no write)            |
| 10th      | `x` or `-` | Execute permission for **others**: `x` (has execute), `-` (no execute)        |

**Example:**

`drwxr-xr--`

This represents a directory (`d`) where:

*   The owner (user) has read, write, and execute permissions (`rwx`).
*   The group has read and execute permissions (`rx`).
*   Others have read permission (`r`).

### Viewing Permissions

The `ls` command lists files and directories.  Several options provide additional details:

*   `ls -a`: Displays hidden files (those starting with a dot ".").
*   `ls -l`: Displays detailed information, including permissions, owner, group, size, and modification time.
*   `ls -la`: Combines both options, displaying detailed information for all files, including hidden files.

### Changing Permissions

The `chmod` command changes file and directory permissions. It requires two arguments:

1.  How to change permissions (add, remove, or set specific permissions).
2.  The target file or directory.

Permissions are assigned to three categories:

*   `u`: User (owner)
*   `g`: Group
*   `o`: Others

Permission changes are specified using operators:

*   `+`: Add permission
*   `-`: Remove permission
*   `=`: Set permission (overwrites existing permissions)

**Examples:**

*   `chmod u+rwx,g+rwx,o+rwx login_sessions.txt`: Adds all permissions (read, write, and execute) for everyone (user, group, and others) to the `login_sessions.txt` file.

*   `chmod u=r,g=r,o=r login_sessions.txt`: Sets read permission only for everyone to the `login_sessions.txt` file.  This command *overwrites* any existing permissions, meaning any write or execute permissions would be removed.

## Authentication and Authorization with `sudo`

The `sudo` command is crucial for managing authentication and authorization in Linux.  Authentication verifies user identity, while authorization grants access to specific resources.  Here's a breakdown of key commands used with `sudo`:

### User Management

*   **`useradd`**: Adds a new user.
    *   `sudo useradd fgarcia`: Adds a user named `fgarcia`.
    *   `-g`: Sets the user's primary group.  `sudo useradd -g security fgarcia` sets the primary group to `security`.
    *   `-G`: Adds the user to supplemental (secondary) groups. `sudo useradd -G finance,admin fgarcia` adds `fgarcia` to the `finance` and `admin` groups.

*   **`usermod`**: Modifies existing user accounts.
    *   `-g`: Changes the user's primary group.  `sudo usermod -g executive fgarcia` changes `fgarcia`'s primary group to `executive`.
    *   `-G`: Adds or modifies supplemental groups. Use with `-a` to append to existing groups.  `sudo usermod -a -G marketing fgarcia` adds `fgarcia` to the `marketing` group *without* removing other supplemental groups.  **Important:** Without `-a`, `-G` *replaces* existing supplemental groups.
    *   `-d`: Changes the user's home directory. `sudo usermod -d /home/garcia_f fgarcia` changes `fgarcia`'s home directory.
    *   `-l`: Changes the user's login name.
    *   `-L`: Locks the user account, preventing login.

*   **`userdel`**: Deletes a user.
    *   `sudo userdel fgarcia`: Deletes the user `fgarcia`.
    *   `-r`: Deletes the user's home directory and files. `sudo userdel -r fgarcia` deletes `fgarcia` and their home directory.  **Caution:** Use with care!
    *   **Recommendation:** Instead of deleting, consider deactivating an account with `usermod -L`. This preserves ownership information and allows for later access if needed.

### Ownership Management

*   **`chown`**: Changes the owner of a file or directory.
    *   `sudo chown fgarcia access.txt`: Changes the user owner of `access.txt` to `fgarcia`.
    *   `sudo chown :security access.txt`: Changes the group owner of `access.txt` to `security`.  The colon `:` is required before the group name.

**Key Considerations:**

*   Always use `sudo` when managing users, groups, and file ownership to ensure proper authorization.
*   Be extremely cautious when using `userdel -r` as it permanently deletes user data.  Deactivating accounts (`usermod -L`) is often a safer alternative.
*   Understand the difference between `-g` (primary group) and `-G` (supplemental groups) with `useradd` and `usermod`.  Remember to use `-a` with `-G` in `usermod` to avoid accidentally removing existing supplemental group memberships.
