
# Chapter 1 – Welcome to the Shell 🎉

So you’ve cracked open Linux. Congrats — you’re entering a world where you command the computer **with words, not clicks**. Think of it like talking to your PC in its native tongue.

Let’s make this fun.

---

## 🖥️ The Big Picture: Who’s Who in Linux

When you use a computer:

1. **Hardware** → the physical stuff (CPU, memory, disk, keyboard).
2. **Kernel** → the OS brain that talks to hardware.
3. **Shell** → your translator. You type a command, shell hands it to the kernel, kernel does the job, you see the result.

> Imagine: **You → Shell (translator) → Kernel (brain) → Hardware (muscles)**.

---

## 💻 What is a Terminal?

A **terminal** is your text-based chat window with Linux.
Back in the day, it was an actual physical device. Today it’s just an app.

Examples:

* GNOME Terminal
* Konsole
* WSL on Windows (Which I am using)

Open one. It’s where all the magic begins. ✨

**If you haven't yet installed WSL yet, install it from [here](../README.md).**

---

## 🐚 What is Bash?

Most Linux systems use **Bash** (Bourne Again SHell).
It’s the interpreter that runs your commands and gives you output.
In this course → we’re sticking with **bash**.

---

## ⚡ Running Your First Commands

Try these out:

```bash
whoami   # your username
pwd      # where you are in the filesystem
date     # system date & time
df -h    # free space on disks
free -h  # free RAM
exit     # close the terminal
```

💡 **Tips**

* Commands are **case-sensitive** → `pwd` ≠ `PWD`.
* Typos? Bash will throw: `command not found`.

---

## 📖 Getting Help

Linux has built-in manuals:

```bash
man pwd
```

Controls:

* `q` → quit
* `/word` → search for something

Example: `/directory` → find mentions of “directory.”

---

## 💡 The Shell Prompt

When you open a terminal, you’ll see something like:

```bash
user@pc:~$
```

That’s the **prompt** → shell waiting for your orders.

Change it temporarily:

```bash
PS1="> "
```

Reset → close & reopen the terminal.

---

## 🎮 Pro Navigation Tricks

### 🔁 Command History

* **↑ (up-arrow)** → brings back your last command.
* **↓ (down-arrow)** → moves forward again.
* Terminals usually remember your **last 1000 commands**.

### ↔️ Cursor Movement

* Use **← →** arrows to move inside a command.
* Fix typos without retyping everything.

### 🖱️ Mouse Copy-Paste

* Highlight text → auto-copied.
* Middle-click → paste it.
* Forget `Ctrl+C` / `Ctrl+V` here — they mean other things (like killing a process ⚔️).

### 🎯 Focus Options

* Most desktops use **click-to-focus** (click a window to make it active).
* Old-school Linux prefers **focus-follows-mouse** → just hover to give focus.
* If supported, try it — smoother copy-pasting.

---

## 🏋️ Exercises

1. Run:

   ```bash
   whoami
   pwd
   date
   df -h
   free -h
   ```
2. Use `man date` → try different date formats.
3. Change your prompt:

   ```bash
   PS1="LinuxRocks> "
   ```
4. Recall your last command using the **↑ arrow**.
5. Practice copy-paste with the mouse.
6. Exit the terminal with:

   ```bash
   exit
   ```

---

**Date Learned:** 11 August 2025

**Source:** *The Linux Command Line*, Chapter 1

