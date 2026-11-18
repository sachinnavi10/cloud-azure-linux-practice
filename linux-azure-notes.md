# Linux Fundamentals - Day 2

## What is Linux?

Linux is an open-source operating system used to manage computer hardware, software, files, users and processes.

Common distributions include:

- Ubuntu
- Red Hat Enterprise Linux (RHEL)
- Debian
- CentOS Stream

## Why Linux matters in Azure

Linux is widely used in cloud environments for:

- Hosting websites and services
- Running Python applications
- Managing databases
- Running cloud-native applications
- Automating server administration tasks

Azure Virtual Machines can run Linux distributions such as Ubuntu. Learning the command line helps with configuring, maintaining, and troubleshooting those virtual machines.

## Linux and Windows

| Linux | Windows |
|---|---|
| Open-source kernel; distributions may include additional software and licensing terms | Proprietary operating system |
| Frequently administered through a terminal, with graphical desktops also available | Commonly used with a graphical interface; command-line tools are also available |
| Commonly used for cloud servers | Commonly used for desktops and also available for servers |
| File names and paths are generally case-sensitive | File names and paths are generally case-insensitive on typical Windows file systems |

## Basic Linux commands

| Command | Purpose |
|---|---|
| `pwd` | Show the current directory |
| `ls` | List files and folders |
| `cd` | Change directory |
| `mkdir` | Create a folder |
| `touch` | Create an empty file or update a file's timestamp |
| `cat` | Display file contents |
| `cp` | Copy files or folders |
| `mv` | Move or rename files or folders |
| `rm` | Delete files or folders; use carefully |
| `clear` | Clear the terminal display |

These commands can be practiced in an Ubuntu Terminal or Git Bash on Windows.

## Hands-on: create a folder and file

Run the commands one at a time:

1. Check your current location:

   ```sh
   pwd
   ```

2. List the files and folders:

   ```sh
   ls
   ```

3. Create a practice folder:

   ```sh
   mkdir linux-practice
   ```

4. Enter the folder:

   ```sh
   cd linux-practice
   ```

5. Create a file:

   ```sh
   touch hello.txt
   ```

6. Confirm that it exists:

   ```sh
   ls
   ```

Expected output:

```text
hello.txt
```

## Git Bash practical training

### Practical 1: Open Git Bash

1. Press the Windows key.
2. Search for **Git Bash**.
3. Open Git Bash. A terminal window should appear.

If Git Bash is not installed, install Git for Windows from the official Git website before continuing.

### Practical 2: Run five basic commands

Run each command separately:

1. Show your current location:

   ```sh
   pwd
   ```

2. List files and folders:

   ```sh
   ls
   ```

3. Show detailed file information:

   ```sh
   ls -l
   ```

4. Clear the terminal display:

   ```sh
   clear
   ```

5. Show your current username:

   ```sh
   whoami
   ```

### Practical 3: Create a project folder and files

Start from your home directory and create a dedicated practice folder. The `-p` option lets you repeat this step if the folder already exists.

```sh
cd ~
mkdir -p linux-day-2-practice
cd linux-day-2-practice
pwd
```

Create three files:

```sh
touch notes.txt
touch commands.txt
touch practice.txt
```

List the files:

```sh
ls
```

Expected output:

```text
commands.txt
notes.txt
practice.txt
```

### Practical 4: Write to and read a file

Write a line to `notes.txt`:

```sh
echo "I am learning Linux for Azure Cloud Computing" > notes.txt
```

Display the file:

```sh
cat notes.txt
```

Expected output:

```text
I am learning Linux for Azure Cloud Computing
```

Append another line and display the file again:

```sh
echo "Today I learned Linux commands" >> notes.txt
cat notes.txt
```

- `>` replaces the file's existing contents.
- `>>` adds a line to the end of the file.

### Practical 5: Copy, rename, and delete

Run these commands from inside `linux-day-2-practice`:

| Task | Command |
|---|---|
| Copy `notes.txt` | `cp notes.txt backup.txt` |
| Rename the copy | `mv backup.txt linux-backup.txt` |
| Delete the renamed copy | `rm linux-backup.txt` |
| Create a folder | `mkdir -p practice` |
| Remove the empty folder | `rmdir practice` |

Be careful with `rm`: deleted files may not go to the Recycle Bin. Check the filename and your current directory with `pwd` and `ls` before deleting anything.

## Summary

Linux is an important operating system family for cloud computing. Practicing basic terminal commands in Git Bash builds skills for working with Azure Linux virtual machines and other cloud servers.

# Linux Fundamentals - Day 3

## File permissions

Linux file permissions control who can read, write, or execute a file. There are three permission types:

| Permission | Meaning | Symbol |
|---|---|---|
| Read | View file content | `r` |
| Write | Modify file content | `w` |
| Execute | Run a file | `x` |

The numeric permission format uses these values:

- `4` = read
- `2` = write
- `1` = execute

For example:

```sh
chmod 755 script.sh
```

This grants the owner read, write, and execute permissions, while the group and others receive read and execute permissions.

### Practical exercise

```sh
touch test.txt
ls -l test.txt
chmod 644 test.txt
ls -l test.txt
```

The expected permissions pattern is:

```text
-rw-r--r--
```

Git Bash emulates Linux permissions over the Windows filesystem, so exact permission behavior can differ from a native Linux server.

## User management

Useful user commands include:

| Command | Purpose |
|---|---|
| `whoami` | Show the current username |
| `id` | Show user and group IDs |
| `who` | Show logged-in users |
| `passwd` | Change a password |
| `sudo` | Execute a command with elevated privileges |

Try these in Git Bash:

```sh
whoami
id
who
```

Commands such as `sudo`, `useradd`, and `passwd` require a complete Linux user-management system and may not work as in a native Linux environment.

## Process management

A process is a running program or application.

| Command | Purpose |
|---|---|
| `ps` | Display processes |
| `ps aux` | Display detailed process information |
| `top` | Monitor processes interactively |
| `kill` | Terminate a process |
| `jobs` | Display background jobs |

```sh
ps
ps aux
```

## Disk and memory management

Check disk space:

```sh
df -h
```

Check folder size:

```sh
du -sh .
```

Check the current directory:

```sh
pwd
```

Check available memory on Linux:

```sh
free -h
```

These commands help cloud engineers identify disk pressure, large directories, and memory usage on servers.

## Day 3 practical assignment

```sh
mkdir day3-practice
cd day3-practice
touch server.sh
echo "My Azure Linux Server" > server.sh
cat server.sh
chmod 644 server.sh
ls -l
```

Practice system monitoring:

```sh
whoami
ps
df -h
du -sh .
```
