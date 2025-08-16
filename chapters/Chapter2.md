
# Chapter 2: Navigating the Linux Filesystem

In the previous chapter, we learned how to open the terminal and run simple commands.  
Now, let’s explore **where things are stored** in Linux and how to move around.

---

## 1. Understanding the Filesystem Structure

Linux organizes files in a **tree-like structure** starting from `/` (called the **root directory**).

Here’s a simplified map of important directories:

```

/
├── bin/     → Essential commands (like `ls`, `cp`, `mv`)
├── home/    → User folders (e.g., `/home/alex`)
├── etc/     → System configuration files
├── var/     → Logs, temporary files, caches
├── usr/     → Applications, libraries, documentation
├── tmp/     → Temporary files (deleted on restart)
└── root/    → Home directory of the root (admin) user

````

Think of `/` as the **top-level folder** where everything begins.

---

## 2. Checking Your Current Location

Run:

```bash
pwd
````

* **pwd** = **P**rint **W**orking **D**irectory
* It shows the **full path** to where you are.

Example:

```bash
/home/alex
```

This means you are in your personal folder inside `/home`.

---

## 3. Listing Files and Folders

Run:

```bash
ls
```

* Lists everything in the current directory.

For more details:

```bash
ls -l
```

* Shows permissions, owner, size, and date modified.

To also see hidden files:

```bash
ls -a
```

* Hidden files start with a dot (`.`), like `.bashrc`.

---

## 4. Moving Around

**Change Directory:**

```bash
cd Documents
```

Moves you into the `Documents` folder (must exist in your current location).

**Go up one folder:**

```bash
cd ..
```

**Go back to your home directory:**

```bash
cd ~
```

**Go to root directory:**

```bash
cd /
```

---

## 5. Absolute vs Relative Paths

* **Absolute path** → Starts from `/` and specifies the full location.
  Example: `/home/alex/Documents`

* **Relative path** → Starts from where you are right now.
  Example: `Documents` (if you’re already in `/home/alex`).

---

## 6. Quick Navigation Shortcuts

* `cd -` → Go to the previous directory you were in.
* `cd ~username` → Go to another user’s home directory.
* `cd .` → Stay in the same folder (basically “do nothing” here).

---

## 7. Practice

1. Open your terminal.
2. Run:

   ```bash
   pwd
   ls -a
   ```
3. Move into a folder using `cd`.
4. Go back using `cd ..`.
5. Try both absolute and relative paths.

---

**Date Learned:** 13 August 2025

**Source:** _The Linux Command Line_, Chapter 2
