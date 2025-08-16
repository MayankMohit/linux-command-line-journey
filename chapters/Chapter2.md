# Chapter 2 – Navigating the Filesystem 🗂️

Now that you can talk to the shell, let’s figure out **where you actually are** in Linux and how to move around.
Think of this as learning to explore the **map of your new world**.

---

## 🌳 The Linux Filesystem Tree

Linux organizes everything in a **single tree**, starting from `/` (the root directory).

```
/
├── bin/     → Essential commands (like ls, cp, mv)
├── home/    → User folders (e.g., /home/alex)
├── etc/     → System configuration files
├── var/     → Logs, caches, temporary files
├── usr/     → Apps, libraries, documentation
├── tmp/     → Temporary stuff (wiped on reboot)
└── root/    → Admin user’s home directory
```

💡 Unlike Windows (`C:\`, `D:\`), Linux doesn’t have multiple drives —
everything lives inside this **one giant tree**.

---

## 📍 Where Am I?

Find your current spot:

```bash
pwd
```

* **pwd** = **P**rint **W**orking **D**irectory
* Shows your exact location.

Example:

```
/home/alex
```

This means you’re in your own home folder.

---

## 📦 What’s Here?

List what’s inside your current directory:

```bash
ls
```

Useful variants:

```bash
ls -l   # detailed list (permissions, owner, size, date)
ls -a   # show hidden files (start with .)
```

Example:

```
-rw-r--r--  1 alex alex   220 Aug 13  .bash_logout
-rw-r--r--  1 alex alex  3771 Aug 13  .bashrc
drwxr-xr-x  2 alex alex  4096 Aug 13  Documents
```

---

## 🚶 Moving Around

* **Change directory**:

```bash
cd Documents
```

* **Go up one level**:

```bash
cd ..
```

* **Jump home**:

```bash
cd ~
```

* **Go to root**:

```bash
cd /
```

---

## 🧭 Paths: Absolute vs Relative

* **Absolute path** → Always starts from `/`.
  Example: `/home/alex/Documents`

* **Relative path** → Starts from where you are right now.
  Example: `Documents` (if you’re in `/home/alex`).

👉 Think of absolute as a **full GPS address**, relative as **local directions**.

---

## ⚡ Pro Navigation Tricks

* `cd -` → Jump back to the previous folder.
* `cd .` → Stay in the same place (basically no move).
* `cd ~username` → Go to another user’s home directory.

---

## 🏋️ Exercises

1. Open your terminal.
2. Run:

   ```bash
   pwd
   ls -a
   ```
3. Move into a folder (like `Documents`) → then back with `cd ..`.
4. Try going directly to `/` using:

   ```bash
   cd /
   ```
5. Jump back home with `cd ~`.
6. Test `cd -` to hop between two directories.

---

**Date Learned:** 13 August 2025

**Source:** *The Linux Command Line*, Chapter 2
