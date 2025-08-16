# Chapter 5 – Environment Variables and the Shell

## 1. What Are Environment Variables?
Environment variables are like little notes the shell keeps around to configure how programs behave.

- They store information about your environment (session).
- Examples:
  - `HOME` → your home directory
  - `USER` → your username
  - `PATH` → where the shell looks for programs

You can see all environment variables with:
```bash
printenv
````

Or check one specific variable:

```bash
echo $HOME
echo $USER
echo $PATH
```

💡 The `$` is used to access the value of a variable.

---

## 2. Setting Environment Variables

You can create your own variables in the shell.

```bash
MYNAME="LinuxLearner"
echo $MYNAME
```

⚠️ By default, variables you create this way are temporary. They disappear when you close the terminal.

---

## 3. Exporting Variables

If you want a variable to be available to other programs:

```bash
export MYNAME="LinuxLearner"
```

Now any process you run from this shell session will know about `MYNAME`.

---

## 4. The PATH Variable

`PATH` is one of the most important environment variables.

* It’s a list of directories the shell searches to find commands.
* Example:

```bash
echo $PATH
```

If you type `ls`, the shell looks in each directory in `PATH` until it finds `ls`.

You can add new directories to your PATH:

```bash
export PATH=$PATH:/home/user/scripts
```

---

## 5. Shell Configuration Files

To make your environment variables permanent, add them to shell startup files.

Common files:

* `~/.bashrc`
* `~/.profile`
* `~/.bash_profile`

Example: Add this line to `~/.bashrc`:

```bash
export MYNAME="LinuxLearner"
```

Then restart your terminal.

---

## 6. Viewing and Unsetting Variables

* To see a variable:
  `echo $VARIABLE`
* To remove a variable:
  `unset VARIABLE`

Example:

```bash
unset MYNAME
```

---

## 7. Exercises

1. Display your `HOME`, `USER`, and `PATH`.
2. Create a variable called `FAVORITE` with your favorite color.
3. Export it so other processes can access it.
4. Add a custom directory (like `~/bin`) to your PATH and create a test script there.
5. Edit your `~/.bashrc` to make an environment variable permanent.

---

**Date Learned:** 17 August 2025

**Source:** _The Linux Command Line_, Chapter 5
