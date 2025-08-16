# Chapter 5 — Working with Commands 🧠⚙️

You’ve been running commands like a champ. Now let’s lift the hood and learn **what a command actually is**, how the shell decides **what to run**, and how to **find great docs fast**. By the end, you’ll debug “why isn’t this command running?” in seconds.

---

## 🧩 What *is* a command?

On a typical Linux system, a command can be one of four things:

1. **Executable program**
   A real file on disk (often in `/usr/bin`, `/bin`, `/usr/local/bin`, etc.).
   Examples: `ls`, `cp`, `python3`, `grep`.

2. **Shell builtin**
   Implemented *inside* Bash itself — faster, always available.
   Examples: `cd`, `echo`, `pushd`, `history`.

3. **Shell function**
   A tiny script loaded into your shell environment. You can write your own later.

4. **Alias**
   A nickname that expands to another command (e.g., `ll` → `ls -alF`).

We’ll learn how to **identify which one you’re calling** and where it lives.

---

## 🔎 `type` — How Bash will interpret a name

**What it does:** Tells you what *kind* of command Bash would execute for a given name.

```bash
type cd
type ls
type foo
```

**Typical outputs:**

* `cd is a shell builtin`
* `ls is aliased to 'ls --color=auto'`
* `cp is /usr/bin/cp`
* `bash: type: foo: not found`

**Pro moves:**

```bash
type -a ls    # show ALL resolutions (alias, builtin, function, PATH hits)
type -t ls    # show only the type: alias/builtin/file/function
```

**Why it matters:** If `ls` is aliased or shadowed by a function, `type` reveals it instantly.

---

## 📍 `which` — Where is the executable?

**What it does:** Shows the path of the **executable file** that would run.
**Important:** `which` only knows about executables in `$PATH`. It **won’t** show builtins, aliases, or functions.

```bash
which ls
which cp
which cd        # likely “no cd in …” (because `cd` is a builtin)
```

**When to use:**

* You want the *file path* (`/usr/bin/ls`).
* You’re debugging PATH issues (“why is my custom tool not running?”).

**Gotcha:** If a name is an alias or function, `which` won’t tell you — use `type` for the full picture.

---

## 🆘 `help` — Help for Bash builtins

**What it does:** Built-in docs for **builtins only**.

```bash
help cd
help history
help -m cd    # alternate (manpage-like) formatting
```

You’ll see syntax like:

* Square brackets `[]` = optional
* Pipes `|` = “one of”
* `...` = repeatable

Use `help` when `man` shows generic info but you need the **Bash-specific** behavior.

---

## 📚 `man` — The manual pages

**What it does:** Shows the canonical *manual page* for commands, files, syscalls, etc.

```bash
man ls          # program reference
man 5 passwd    # section 5 (file formats) for /etc/passwd
```

**Sections you’ll see a lot:**

* `1` User commands
* `5` File formats
* `8` System admin commands

**Navigation (via `less`):**

* `q` quit
* `/word` search forward
* `n` next match
* `Shift+G` end
* `g` start
* `h` help

**Tips:**

* `man -k keyword` ≈ `apropos keyword` (search titles/descriptions)
* `man -f name` ≈ `whatis name` (one-line description)

---

## 🔍 `apropos` — “What commands match this idea?”

**What it does:** Searches manpage **names and short descriptions**.

```bash
apropos partition
apropos network time
```

Use it when you **don’t know the exact command** but you know the topic.
(Under the hood, same DB as `man -k`.)

---

## 🏷️ `whatis` — One-line summary

**What it does:** Prints the short description for a man page entry.

```bash
whatis ls
whatis passwd
```

Great for a quick sanity check: “is this the command I think it is?”

---

## ℹ️ `info` — Hyperlinked manuals (GNU style)

**What it does:** Shows **Info** documents (often more tutorial-ish than man pages) for GNU tools.

```bash
info coreutils 'ls invocation'   # jump straight to ls section
info ls                          # open the ls entry (if present)
```

**Navigation keys:**

* `Space` / `Backspace` page forward/back
* `n` next node
* `p` previous node
* `u` up (parent)
* `Enter` follow link (the `*` items)
* `q` quit
* `?` help

Tip: Many GNU tools (like coreutils) have **richer examples** in `info` vs `man`.

---

## 🏷️ `alias` — Create your own commands

**What it does:** Defines a shortcut.

```bash
alias ll='ls -alF'
alias gs='git status'
alias ...='cd ../..'
```

View all aliases:

```bash
alias
```

Remove an alias:

```bash
unalias ll
```

**Persistence:** Put aliases in `~/.bashrc` (or `~/.bash_aliases` if you source it) so they load in every shell.

**Caution:** If you alias over a real command name, you can still reach the original with a leading backslash:

```bash
alias ls='ls --color=auto'
\ls    # runs the real ls, bypassing the alias
```

---

## 🧠 Putting it together — How Bash decides what to run

When you type a name, Bash resolves in this order:

1. **Alias**
2. **Function**
3. **Builtin**
4. **Executable in `$PATH`** (first match wins)

Use `type -a <name>` to see the full chain.

---

## 🧪 Mini-Lab (5 minutes)

**Goal:** Diagnose what each name resolves to, then make your own.

```bash
# 1) What are these?
type cd
type ls
type echo
type grep
which grep

# 2) Add and test aliases
alias ll='ls -alF'
alias ls='ls --color=auto'
type ls
\ls -l                # bypass alias

# 3) Check docs three ways
help cd
man ls
whatis ls
apropos directory
info coreutils 'ls invocation'
```

---

## 🧯 Troubleshooting Playbook

* “My command runs the wrong thing.” → `type -a name`
* “It says ‘command not found’.” → Check `$PATH`, or typo? Try `which name`
* “Docs are too terse.” → Try `info`, not just `man`
* “Builtin vs external behavior differs.” → `help` (for builtin specifics)
* “I want to *temporarily* bypass an alias.” → `\command args`

---

## 📝 Exercises

1. Create two useful aliases in `~/.bashrc`, reload with `source ~/.bashrc`, and test them.
2. Use `apropos` to find a tool that can **compare files**. Read its `man` page and try it.
3. Show the **file path** of `python3` and the **type** of `echo`.
4. Use `man 5 passwd` and explain, in one sentence, what each field in `/etc/passwd` means.

---

**Date Learned:** 17 August 2025

**Source:** *The Linux Command Line*, Chapter 5

