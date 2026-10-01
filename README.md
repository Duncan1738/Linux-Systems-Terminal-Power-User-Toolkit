# Linux Systems & Terminal Power User Toolkit

A curated collection of shell scripts, system administration workflows, and terminal configurations designed for performance monitoring, automation, and daily Linux operations.

---

## Overview

This repository serves as a practical handbook and repository of scripts for managing Linux environments efficiently. Whether you are managing remote Linux servers, configuring laboratory workstations, or optimizing terminal workflows, this collection provides tested configurations and automation scripts.

---

## Repository Structure

```text
.
├── scripts/
│   ├── system_health.sh        # Resource monitoring script (CPU, RAM, Disk, GPU)
│   ├── network_diag.sh         # Network connectivity and socket status checker
│   └── backup_rsync.sh         # Incremental rsync backup utility
├── config/
│   ├── .bashrc_aliases         # Production-ready shell aliases
│   └── tmux.conf               # Custom tmux terminal multiplexer layout
└── docs/
    ├── networking_cheatsheet.md # Essential IP, port, and SSH routing commands
    └── storage_management.md   # Guide to storage quotas, mounting, and permissions
```

---

## Quick Start: Core Workflows

### 1. System Diagnostics & Monitoring

Check active hardware load, memory consumption, and disk usage in real time:

```bash
# Monitor system resources
top -b -n 1 | head -n 20

# View disk usage in human-readable format
df -h --total

# Inspect running processes filtered by memory usage
ps aux --sort=-%mem | head -n 10
```

---

### 2. File & Directory Management

Efficiently locate large files and update directory permissions:

```bash
# Find files larger than 100MB in the current directory
find . -type f -size +100M -exec ls -lh {} \;

# Recursively grant read/write permissions to owner and read-only to group
chmod -R 750 /path/to/target_directory
```

---

### 3. Remote Server Management (SSH)

Establish secure sessions, port forwarding, and background multiplexing:

```bash
# Connect with persistent SSH keys and compression enabled
ssh -C -i ~/.ssh/id_ed25519 user@remote-hostname

# Port forward a local web app interface to a remote server
ssh -L 8080:localhost:8080 user@remote-hostname

# Start a detached tmux session to keep background jobs running after disconnection
tmux new -s workflow_session
```

---

## Essential Shell Aliases

Add these productivity shortcuts to your `~/.bashrc` or `~/.zshrc` file:

```bash
# Safety guards against accidental overwrites
alias rm='rm -i'
alias cp='cp -i'
alias mv='mv -i'

# Enhanced list viewing
alias ll='ls -lh --group-directories-first'
alias la='ls -lah --group-directories-first'

# Quick networking checks
alias myip='curl -s https://ifconfig.me'
alias ports='netstat -tulpn'
```

---

## Recommended CLI Tools

Enhance your default command-line interface with these modern tools:

| Category | Standard Tool | Modern Alternative | Purpose |
| :--- | :--- | :--- | :--- |
| **System Monitor** | `top` | `htop` / `btop` | Interactive process viewer and resource usage chart |
| **File Search** | `find` | `fd` | Fast, user-friendly directory search |
| **Text Search** | `grep` | `ripgrep` (`rg`) | Blazing fast recursive line searches |
| **File Viewer** | `cat` | `bat` | File viewer with syntax highlighting and Git integration |

---

## License

This project is open-source under the [MIT License](LICENSE). Feel free to adapt and share.
