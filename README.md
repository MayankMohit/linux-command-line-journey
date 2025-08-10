# Linux Command Line Journey

This repository documents my day-by-day progress as I work through *The Linux Command Line* by William Shotts.  
Each chapter includes detailed notes, practical examples, and scripts you can run in your own terminal.

---

## My Environment

I am learning Linux commands inside **WSL (Windows Subsystem for Linux)** on Windows 11.  
This means all commands here are tested on Ubuntu running inside WSL.

### Installing WSL

If you are on **Windows 10 or 11**, you can install WSL like this:

1. Open **PowerShell** as Administrator.
2. Run:
   ```powershell
   wsl --install
   ```
3. Restart your PC when prompted.
4. Open a terminal and run:
   ```powershell
   wsl --list --online
   wsl --install -d Ubuntu
   ```
5. Once Ubuntu is installed, set up your username and password.
6. Launch Ubuntu from your Start menu and you are ready.

> **Note:** If you are on Windows 10 older than build 2004, follow Microsoft's WSL docs:  
> https://learn.microsoft.com/windows/wsl/install

---

## Goals
- Learn Linux deeply by doing.
- Share clear, reproducible examples.
- Build a professional knowledge log.

---

## Structure
- `chapters/` — Chapter-based notes and commands.
- `examples/` — Supporting scripts and files.
- `daily-log/` — Personal "What I learned today" entries.
- `scripts/` — General helper scripts.

---

## How to Follow Along
1. Set up WSL or any Linux environment.
2. Pick a chapter file from `chapters/`.
3. Try out the commands and exercises in your own terminal.
4. Read the daily logs for tips and progress tracking.

---

*Start Date:* 10 August 2025
