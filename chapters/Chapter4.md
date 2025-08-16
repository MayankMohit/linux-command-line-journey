
# Chapter 4 – File Permissions and Ownership

Welcome back!  
So far we’ve learned how to navigate the file system and manage files.  
Now it’s time to understand **file permissions** — one of the most important concepts in Linux security.

---

## 1. Why Permissions Matter
Linux is a multi-user system.  
Permissions decide **who can read, write, or execute** a file or directory.  
This prevents unwanted changes or access to sensitive files.

---

## 2. Users and Groups
Every file and directory in Linux has:
- **Owner** → usually the user who created the file.
- **Group** → a set of users with shared access.
- **Others** → everyone else.

---

## 3. Permission Types
Permissions are divided into three categories:
- **r (read)** → view contents of a file / list a directory.
- **w (write)** → modify contents of a file / create, delete, rename inside a directory.
- **x (execute)** → run a file as a program / enter a directory.

---

## 4. Viewing Permissions
Use the `ls -l` command:
```bash
ls -l
````

Example output:

```
-rwxr-xr--  1 user group  1024 Aug 15 09:30 script.sh
```

Breakdown:

* `-` → file type (`-` = file, `d` = directory)
* `rwx` → owner permissions
* `r-x` → group permissions
* `r--` → others permissions

So here:

* Owner can **read, write, execute**.
* Group can **read, execute**.
* Others can only **read**.

---

## 5. Changing Permissions

Use `chmod` (change mode):

* Add permission:

```bash
chmod +x file.sh   # Give execute permission to all
```

* Remove permission:

```bash
chmod -w notes.txt # Remove write permission from all
```

* Set specific permissions with numbers:

  * `r = 4`, `w = 2`, `x = 1`
  * Add them up for each category.

Example:

```bash
chmod 755 script.sh
```

Meaning:

* Owner: 7 → read (4) + write (2) + execute (1)
* Group: 5 → read (4) + execute (1)
* Others: 5 → read (4) + execute (1)

---

## 6. Changing Ownership

Use `chown` (change owner):

```bash
sudo chown newuser file.txt
```

To change both owner and group:

```bash
sudo chown user:group file.txt
```

---

## 7. Changing Group Ownership

Use `chgrp`:

```bash
sudo chgrp developers project/
```

---

## 8. Exercises

1. Create a file `test.txt` and list its permissions:

   ```bash
   touch test.txt
   ls -l test.txt
   ```
2. Remove write permission for others.
3. Make a script executable.
4. Change the owner of a file to another user (if available).
5. Practice using both symbolic (`+x`, `-w`) and numeric (`755`, `644`) methods.

---

**Date Learned:** 16 August 2025

**Source:** _The Linux Command Line_, Chapter 4

