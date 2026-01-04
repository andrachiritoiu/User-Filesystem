# User Filesystem Monitor

## Overview

This project implements a **Linux shell script** that monitors active users on a system and creates a filesystem-based representation of their activity.  
For each user, the script maintains a dedicated directory containing information about running processes and login history.

The project simulates a lightweight user monitoring system using standard Linux tools and filesystem operations.

---

## How It Works

The script periodically scans the system for **currently active users** and performs the following actions:

### 🔹 Active Users
For each active user:
- A directory is created (or updated) using the username
- Inside the directory, a file named `procs` is generated
- The `procs` file contains a list of all processes currently running under that user

### 🔹 Inactive Users
For users who are no longer active:
- Their directory is preserved
- The `procs` file is emptied
- A new file named `lastlogin` is created
- The `lastlogin` file stores the date and time of the user's last login session

This approach allows tracking both **current activity** and **historical login information** using only filesystem data.

---

## Directory Structure Example

```text
user_filesystem/
├── alice/
│   ├── procs
│   └── lastlogin
├── bob/
│   ├── procs
│   └── lastlogin
├── charlie/
│   └── procs
```

## Technologies Used

- **Bash / Shell scripting**
- Standard Linux utilities (`who`, `ps`, `awk`, `grep`, etc.)
- Linux filesystem operations

---

## Features

- Detects active and inactive users automatically
- Periodically updates user process information
- Preserves historical login data
- No external dependencies required
- Lightweight and easy to run on any Linux system

