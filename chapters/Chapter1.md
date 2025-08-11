# Chapter 1 – What is the Shell?

Welcome to the Linux world!  
Before we start typing commands like a pro, we need to understand **what’s going on behind the scenes** when we use Linux.

---

## 1. The Big Picture

When you use a computer:
1. **Hardware** is the physical stuff — CPU, memory, disk, keyboard, etc.
2. **Kernel** is the brain of the operating system — it talks directly to the hardware.
3. **Shell** is the program that takes your commands, passes them to the kernel, and shows you the results.

Think of it like:
> **You** → **Shell (translator)** → **Kernel (OS brain)** → **Hardware**

---

## 2. What is a Terminal?

A **terminal** is a text-based interface where you can type commands.  
Originally, terminals were physical devices.  
Today, we use **terminal emulators** — programs that simulate a terminal inside a window.

Examples:
- GNOME Terminal
- Konsole
- **WSL Terminal on Windows** (what I’m using here)

---

## 3. What is Bash?

Bash (**Bourne Again SHell**) is the most common shell in Linux.  
It’s what interprets your commands and gives you output.

> In this course, all examples will use **bash**.

---

## 4. Running Commands

Let’s try a few commands:

```bash
whoami      # Shows your username
pwd         # Shows your current working directory (where you are in the filesystem)
date        # Shows the system date and time
```

💡 **Tips:**
- Commands are **case-sensitive** → `PWD` is different from `pwd`.
- If you make a typo, bash will say:  
  `command not found`

---

## 5. Getting Help

Linux has built-in manuals called **man pages**:

```bash
man pwd
```

Use:
- `q` to quit the manual
- `/` to search inside it

Example: `/directory` → searches for the word “directory”

---

## 6. The Shell Prompt

When you open the terminal, you’ll see something like:

```bash
mayank@PC:~$
```

This is the **prompt** — it’s where the shell waits for your command.

You can temporarily change the prompt:

```bash
PS1="> "
```

---

## 7. Exercises

1. Open your terminal and run:
   ```bash
   whoami
   pwd
   date
   ```
2. Use `man date` and explore different formatting options.
3. Change your prompt to something fun:
   ```bash
   PS1="Linux Rocks> "
   ```
4. Close and reopen the terminal to reset your prompt.

---

*Date Learned: 10 August 2025*  
*Source: The Linux Command Line, Chapter 1*
