# Chapter 3 – Exploring the System 🔍

Now that you can run commands, let’s go sightseeing inside Linux.
We’ll explore files, directories, and the weird but powerful concept of **links**.

---

## 📂 Listing Files with `ls`

The `ls` command shows files and directories.

Basic usage:

```bash
ls
```

Useful options:

```bash
ls -l     # long listing (permissions, size, owner, date)
ls -a     # show hidden files (those starting with .)
ls -lh    # human-readable sizes
ls -lt    # sort by modification time (newest first)
ls -R     # list recursively into subdirectories
```

💡 Combine options → `ls -lha` shows *everything* in a readable way.

---

## 🧾 What’s This File? (`file`)

Linux doesn’t rely on extensions like `.txt` or `.exe`.
To know what something is:

```bash
file /bin/ls
```

Output example:

```
/bin/ls: ELF 64-bit LSB executable
```

It tells you if it’s a **binary, script, image, text file, etc.**

---

## 📖 Viewing Files with `less`

Open a file to scroll through:

```bash
less /etc/passwd
```

Controls:

* `↑ ↓` → move line by line
* `PgUp / PgDn` → scroll pages
* `/word` → search forward
* `?word` → search backward
* `n` → next match, `N` → previous
* `q` → quit

💡 `less` doesn’t load the whole file at once → perfect for giant logs.

---

## 🗂️ Key Linux Directories

Linux follows the **Filesystem Hierarchy Standard (FHS)**. Some key spots:

* `/` → root of everything
* `/bin` → essential binaries (like `ls`, `cat`, `cp`)
* `/usr/bin` → user applications (editors, compilers, etc.)
* `/etc` → system configuration files
* `/home` → user directories (`/home/you`)
* `/var` → variable data (logs, spool, caches)
* `/tmp` → temporary files
* `/lib` and `/usr/lib` → libraries programs depend on
* `/dev` → device files (disks, terminals, etc.)
* `/proc` → virtual system info (kernel, processes)

Run:

```bash
ls /bin /etc /usr /var
```

to see how different they look.

---

## 🔗 Links: Hard vs Symbolic

Linux lets you make **multiple names** for the same file.

### Hard Links

* A hard link is **another directory entry** pointing to the same file data.
* Both names are equal — delete one, the data still exists until all are gone.

```bash
ln original.txt hardlink.txt
```

### Symbolic (Soft) Links

* A symlink is a **shortcut** that points to another file.
* If the target disappears, the symlink breaks.

```bash
ln -s /lib/libc-2.6.so libc.so.6
```

Example from a real system:

```
lrwxrwxrwx 1 root root 11 2007-08-11 07:34 libc.so.6 -> libc-2.6.so
```

Here:

* `l` at the start means “link”
* `libc.so.6` is the symlink
* It points to → `libc-2.6.so`

---

## 🏋️ Exercises

1. List everything in `/etc` with details:

   ```bash
   ls -lha /etc
   ```

2. Use `file` to check:

   ```bash
   file /bin/bash
   file /etc/passwd
   ```

3. Open `/etc/passwd` with `less` → search for your username.

4. Explore directories:

   ```bash
   ls /bin
   ls /usr/bin
   ls /var/log
   ```

5. Create a hard link and symbolic link to a file:

   ```bash
   echo "hello" > test.txt
   ln test.txt hard.txt
   ln -s test.txt soft.txt
   ls -l
   ```

   Now delete `test.txt` and see what happens to `hard.txt` vs `soft.txt`.

---

**Date Learned:** 15 August 2025

**Source:** *The Linux Command Line*, Chapter 3
