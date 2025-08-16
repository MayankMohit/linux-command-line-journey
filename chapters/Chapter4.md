# Chapter 4 — Manipulating Files and Directories 🗂️

Time to get our hands dirty — Linux isn’t just about looking at files, it’s about **making, breaking, moving, and linking them like a boss**.

In this chapter, you’ll learn:

* How to create directories (`mkdir`)
* How to copy stuff (`cp`)
* How to move and rename stuff (`mv`)
* How to delete (danger zone!) with `rm`
* How to link files together with `ln`
* How to use wildcards to work with **many files at once**

And yes… we’re going to build a **playground** so you don’t blow up your system while practicing. 😏

---

## 🎮 Step 1: Build a Playground

Let’s not experiment on important files — that’s like learning to drive by practicing in a Ferrari showroom.

Make a safe place in your home directory:

```bash
cd ~
mkdir playground
cd playground
```

From now on, all examples happen in `~/playground`.

---

## 🏗️ `mkdir` — Make New Directories

Think of `mkdir` as “summon a new folder.”

```bash
mkdir new_folder
```

Cool tricks:

* `mkdir -p project/src/assets` → makes a **whole tree** at once 🌳
* `mkdir -v demo` → Linux politely tells you what it made

👉 Try:

```bash
mkdir test1 test2 test3
ls
```

---

## 📋 `cp` — Copy Files Like a Wizard

`cp` = duplicate files. It doesn’t teleport them, it clones them.

```bash
cp source.txt copy.txt
```

Useful options:

* `-i` → ask before overwriting (`cp -i a b`)
* `-r` → copy folders recursively (`cp -r dir1 dir2`)
* `-u` → only copy if newer

👉 Playground Test:

```bash
echo "Hello" > hello.txt
cp hello.txt hello_copy.txt
ls
```

---

## 🚚 `mv` — Move or Rename

This one is sneaky: it both **renames** and **moves**.

```bash
mv old.txt new.txt   # rename
mv file.txt dir/     # move into a folder
```

Options:

* `-i` → ask before overwriting

👉 Try this:

```bash
mkdir stuff
mv hello_copy.txt stuff/
ls stuff
```

---

## 💀 `rm` — Remove (Danger Zone!)

The most feared command. `rm` **permanently deletes** things. There’s no recycle bin. No undo. Just void.

```bash
rm file.txt
rm -r folder/
```

Options:

* `-i` → confirm before deleting
* `-r` → delete folders recursively
* `-f` → force delete, no questions asked 😈

⚠️ **Scary Story Time:**
You wanted to delete `.html` files:

```bash
rm *.html     # ✅ correct
rm * .html    # ❌ deletes EVERYTHING, then complains about ".html"
```

👉 Safety Tip: Always test wildcards with `ls` first:

```bash
ls *.html
```

If it shows the right files, then press `↑` and replace `ls` with `rm`.

---

## 🔗 `ln` — Hard & Symbolic Links

Links are like **extra doorways** to the same file.

### 🔹 Hard Links

* Multiple names for one file
* File survives until **all** links are gone
* Can’t cross file systems, can’t link directories

Example:

```bash
ln hello.txt hello_hard
```

Now `hello.txt` and `hello_hard` are the same file. Edit one, the other changes too.

### 🔹 Symbolic Links (Symlinks)

* Modern, flexible
* Works like Windows shortcuts
* Can link across file systems, can point to directories
* If the original dies, the symlink is “broken” (ls often shows it in red)

Example:

```bash
ln -s hello.txt hello_symlink
```

👉 Test it:

```bash
echo "Linked!" >> hello_symlink
cat hello.txt
```

You wrote to the symlink, the original changed. Magic! ✨

---

## 🎭 Wildcards — Work With Many Files at Once

Wildcards = pattern matching for filenames.

| Wildcard      | Meaning                      | Example                                       |
| ------------- | ---------------------------- | --------------------------------------------- |
| `*`           | Matches any characters       | `ls *.txt` → all `.txt` files                 |
| `?`           | Matches a single character   | `ls file?.txt` → file1.txt but not file10.txt |
| `[abc]`       | Matches a, b, or c           | `ls [abc]*`                                   |
| `[!0-9]`      | Matches anything not a digit | `ls [!0-9]*`                                  |
| `[[:upper:]]` | Uppercase letters            | `ls [[:upper:]]*`                             |

👉 Try:

```bash
touch file1.txt file2.txt fileA.txt test.TXT
ls f*
ls file?.txt
ls [[:upper:]]*
```

---

## ✅ Recap

* `mkdir` makes folders
* `cp` copies
* `mv` moves/renames
* `rm` deletes (handle with care!)
* `ln` makes links (hard vs symlink)
* Wildcards let you target groups of files like a pro

And remember: always **practice inside your playground** before unleashing these commands on your real system.

---

