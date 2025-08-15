# Chapter 3: Managing Files and Directories

Now that you can move around the Linux filesystem, it’s time to **interact with files and folders**.  
In this chapter, you’ll learn how to create, rename, move, and delete files and directories.

---

## 1. Creating Files

### Using `touch`

```bash
touch file1.txt
```

- Creates an empty file named `file1.txt`.
- You can create multiple files at once:

```bash
touch file1.txt file2.txt file3.txt
```

### Using `echo`

```bash
echo "Hello Linux" > file2.txt
```

- Creates `file2.txt` and writes “Hello Linux” into it.
- `>` **overwrites** the file; `>>` **appends** to the file.

---

## 2. Creating Directories

### Using `mkdir`

```bash
mkdir projects
```

- Creates a new folder named `projects`.

### Creating nested directories

```bash
mkdir -p projects/python/lessons
```

- `-p` allows creating **parent directories** if they don’t exist.

---

## 3. Listing Contents

```bash
ls           # Basic listing
ls -l        # Long listing: permissions, owner, size
ls -a        # Show hidden files
ls -lh       # Human-readable sizes
```

---

## 4. Moving and Renaming Files

### Using `mv`

```bash
mv file1.txt projects/       # Move file1.txt into projects/
mv file2.txt file2_renamed.txt  # Rename file2.txt
```

- `mv` works for both **moving** and **renaming** files or directories.

---

## 5. Copying Files and Directories

### Using `cp`

```bash
cp file1.txt copy_of_file1.txt   # Copy a file
cp -r projects/ projects_backup/ # Copy a directory recursively
```

- `-r` (or `--recursive`) is required for copying directories.

---

## 6. Deleting Files and Directories

### Using `rm`

```bash
rm file1.txt           # Delete a file
rm -i file2.txt        # Prompt before deleting
rm -r projects_backup/ # Delete a directory and its contents
```

- ⚠️ **Be careful!** Deleted files cannot be recovered easily.

---

## 7. Viewing File Content

```bash
cat file2.txt          # Show the entire file
less file2.txt         # Paginated view; use q to quit
head file2.txt         # Show first 10 lines
tail file2.txt         # Show last 10 lines
```

---

## 8. Exercises

1. Create a folder `linux_practice` in your home directory.
2. Inside it, create files: `notes.txt`, `todo.txt`.
3. Create a nested folder: `projects/python/lessons`.
4. Move `notes.txt` into `projects/python`.
5. Copy `todo.txt` into `projects/python` as `todo_backup.txt`.
6. Rename `todo_backup.txt` to `todo_old.txt`.
7. Delete `todo_old.txt`.
8. Use `cat` or `less` to view the contents of `notes.txt`.

---

**Next Chapter Preview:** Learn about **permissions, ownership, and basic file security** in Linux.

**Date Learned:** 15 August 2025

**Source:** _The Linux Command Line_, Chapter 3
