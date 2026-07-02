# Linux Basic Commands and Important Directories

# 1. `pwd`

## Full Form

**Print Working Directory**

## Purpose

Displays the absolute path of the directory you are currently working in.

### Syntax

```bash
pwd
```

### Example

```bash
$ pwd
/home/student
```

### Explanation

The output means that you are currently inside the **student** directory, which is located inside the **home** directory.

---

# 2. `cd`

## Full Form

**Change Directory**

## Purpose

Used to move from one directory to another.

### Syntax

```bash
cd directory_name
```

### Example (Relative Path)

Current directory:

```text
/home/student
```

Command:

```bash
cd Documents
```

New location:

```text
/home/student/Documents
```

### Example (Absolute Path)

```bash
cd /etc
```

This command moves directly to the `/etc` directory regardless of your current location.

---

# 3. `cd ..`

## Purpose

Moves one level up to the parent directory.

### Example

Current location:

```text
/home/student/Documents
```

Command:

```bash
cd ..
```

New location:

```text
/home/student
```

Again:

```bash
cd ..
```

Output:

```text
/home
```

Again:

```bash
cd ..
```

Output:

```text
/
```

![Git Bash](images\Screenshot 2026-07-01 204707.png)
---

# 4. `ls`

## Full Form

**List**

## Purpose

Displays all files and directories inside the current directory.

### Syntax

```bash
ls
```

### Example

```bash
$ ls
Documents Downloads Music Pictures
```

### Explanation

The output shows the names of files and folders present in the current directory.

---

# 5. `ls -l`

## Purpose

Displays files and directories in **long listing format** with detailed information.

### Syntax

```bash
ls -l
```

### Example

```text
drwxr-xr-x 2 student student 4096 Jul 2 Documents
-rw-r--r-- 1 student student 1200 Jul 1 notes.txt
```

### Understanding the Output

| Field | Description |
|--------|-------------|
| `drwxr-xr-x` | File or directory permissions |
| `2` | Number of links |
| `student` | Owner of the file |
| `student` | Group owner |
| `4096` | File size (in bytes) |
| `Jul 2` | Last modified date |
| `Documents` | File or directory name |

---

# 6. `ls -la`

## Purpose

Displays:

- Detailed file information (`-l`)
- Hidden files (`-a`)

### Syntax

```bash
ls -la
```

### Example

```text
.
..
.bashrc
.profile
Documents
Downloads
```

### Hidden Files

Files beginning with a dot (`.`) are hidden.

Examples:

```text
.bashrc
.profile
.gitconfig
```

These files usually store user configuration settings.

---

# 7. `ls -la ..`

## Purpose

Displays the contents of the **parent directory** without leaving the current directory.

### Example

Current location:

```text
/home/student/Documents
```

Command:

```bash
ls -la ..
```

Output:

```text
Documents
Downloads
Pictures
Videos
```

These folders belong to:

```text
/home/student
```

![Git Bash](images\Screenshot 2026-07-01 204731.png)
![Git Bash](images\Screenshot 2026-07-01 204755.png)
---

# Understanding Important Linux Directories

---

# 8. `cd /`

## Purpose

Moves to the **root directory** of the Linux file system.

### Command

```bash
cd /
```

Verify:

```bash
pwd
```

Output:

```text
/
```

### Explanation

The root directory is the top-most directory in Linux.

Every file and folder in Linux starts from this location.

---

# 9. `cd /etc`

## Directory Name

`/etc`

### Purpose

Stores system-wide configuration files.

Examples include:

```text
/etc/passwd
/etc/hosts
/etc/ssh/
/etc/systemd/
```

### Think of it as

The **Settings Folder** of Linux.

System administrators frequently edit files inside `/etc`.

---

# 10. `cd /bin`

## Directory Name

`/bin`

### Purpose

Contains essential executable programs used by all users.

Examples:

```text
ls
pwd
cp
mv
rm
mkdir
cat
echo
```

When you execute:

```bash
ls
```

Linux actually runs:

```text
/bin/ls
```

---

# 11. `cd /usr`

## Directory Name

`/usr`

### Purpose

Contains user applications, libraries, documentation, and utilities.

Common subdirectories:

```text
/usr/bin
/usr/lib
/usr/local
/usr/share
```

Think of `/usr` as the **Applications** folder of Linux.

---

# 12. `cd /usr/bin`

## Directory Name

`/usr/bin`

### Purpose

Stores executable programs installed on the system.

Examples:

```text
python
java
git
vim
nano
gcc
curl
```

When you type:

```bash
python
```

Linux executes:

```text
/usr/bin/python
```

---

# 13. `/usr/local`

## Purpose

Stores software installed manually by the system administrator.

Typical structure:

```text
/usr/local/bin
/usr/local/lib
/usr/local/share
```

Examples:

- Java
- Maven
- Node.js
- Custom applications

Unlike `/usr/bin`, software inside `/usr/local` is generally **not installed by the operating system's package manager**.

---

# 14. `/var`

## Full Form

**Variable**

### Purpose

Stores files whose contents change frequently.

Examples:

```text
/var/log
/var/cache
/var/mail
/var/spool
```

### `/var/log`

Contains important system log files.

Examples:

```text
system.log
boot.log
auth.log
```

These logs help administrators troubleshoot system issues.

---

# 15. `/lib`

## Full Form

**Library**

### Purpose

Contains shared libraries required by executable programs.

Think of libraries as helper files that applications need to run.

Example:

When executing:

```bash
ls
```

Linux loads several shared libraries from:

```text
/lib
```

Without these libraries, many commands would fail to execute.

---

# 16. `/home`

## Purpose

Stores personal directories of normal users.

Examples:

```text
/home/alice
/home/bob
/home/student
```

Each user stores their:

- Documents
- Downloads
- Pictures
- Music
- Videos
- Projects

This is your personal workspace.

---

# 17. `/root`

## Purpose

Home directory of the **root (administrator)** user.

Location:

```text
/root
```

Difference:

Normal user:

```text
/home/student
```

Administrator:

```text
/root
```

---

# 18. `/tmp`

## Full Form

**Temporary**

### Purpose

Stores temporary files created by applications.

Examples:

- Installer files
- Cache files
- Temporary downloads

Many Linux systems automatically clear this directory after reboot.

---

# 19. `/dev`

## Full Form

**Devices**

### Purpose

Contains special files that represent hardware devices.

Examples:

```text
/dev/sda
/dev/null
/dev/random
/dev/tty
```

### Interesting Example

```bash
echo "Hello" > /dev/null
```

The output disappears because `/dev/null` discards everything written to it.

It is often called the **black hole** of Linux.

---

# 20. `/proc`

## Full Form

**Process**

### Purpose

A virtual file system created by the Linux kernel.

It does not contain real files stored on disk.

Instead, it provides live information about:

- Running processes
- CPU
- Memory
- Kernel

Examples:

```text
/proc/cpuinfo
/proc/meminfo
/proc/version
```

### View CPU Information

```bash
cat /proc/cpuinfo
```

### View Memory Information

```bash
cat /proc/meminfo
```

---

![Git Bash](images\Screenshot 2026-07-01 204814.png)
![Git Bash](images\Screenshot 2026-07-01 204831.png)
![Git Bash](images\Screenshot 2026-07-01 204905.png)
![Git Bash](images\Screenshot 2026-07-01 204923.png)
![Git Bash](images\Screenshot 2026-07-02 054859.png)
