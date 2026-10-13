# Linux Systems & Terminal Power User Toolkit

A professional, zero-dependency collection of modular Bash utilities designed for Linux system administrators, power users, and DevOps engineers. This toolkit provides essential tools for resource diagnostics, performance monitoring, and automated system maintenance.

## Key Features

- **Zero External Dependencies**: Built entirely with standard POSIX/GNU Linux utilities (`bash`, `journalctl`, `find`, `awk`).
- **Modular Design**: Utility scripts function independently or can be chained together in automated pipelines.
- **Production-Grade**: Includes strict error handling, non-destructive default modes, and execution checks.
- **Clean Documentation**: Structured and accessible without unnecessary visual bloat or non-standard formatting.

## Repository Structure

```text
Linux-Systems-Terminal-Power-User-Toolkit/
│
├── README.md         # Toolkit documentation and user guide
├── sys_tune.sh       # System diagnostics and resource monitoring utility
└── log_cleaner.sh    # Log retention, systemd journal, and cache maintenance script
```

## Utility Overview

### 1. `sys_tune.sh` — Resource Diagnostics & Tuning

`sys_tune.sh` provides high-level diagnostic metrics for system health, including memory distribution, top CPU-consuming processes, disk usage, and load averages.

**Capabilities:**
- Memory utilization breakdown (total, used, free, available).
- Dynamic load average analysis ($1$-minute, $5$-minute, and $15$-minute metrics).
- Identification of top resource-consuming processes by CPU and Memory usage.
- Disk usage summary across all mounted filesystems.

**Basic Usage:**
```bash
# Make the script executable
chmod +x sys_tune.sh

# Run diagnostic scan
./sys_tune.sh
```

---

### 2. `log_cleaner.sh` — System Maintenance & Cleanup

`log_cleaner.sh` manages system log accumulation, rotates oversized log files, and cleans up old systemd journal entries to recover disk space safely.

**Capabilities:**
- Vacuum `journalctl` logs by size or age threshold.
- Safely clear or truncate system log files under `/var/log`.
- Clear package manager and user cache directories.
- Safe execution options preventing accidental data loss.

**Basic Usage:**
```bash
# Make the script executable
chmod +x log_cleaner.sh

# Run log maintenance (requires elevated permissions for system logs)
sudo ./log_cleaner.sh
```

## Requirements

- **Operating System**: Linux (Ubuntu, Debian, RHEL, CentOS, Fedora, Arch, or similar)
- **Shell**: Bash 4.0 or higher
- **Permissions**: Standard user access for diagnostics (`sys_tune.sh`); `root` or `sudo` privileges for log maintenance (`log_cleaner.sh`).

## Installation & Setup

Clone the repository to your local machine:

```bash
git clone https://github.com/Duncan1738/Linux-Systems-Terminal-Power-User-Toolkit.git
cd Linux-Systems-Terminal-Power-User-Toolkit
chmod +x *.sh
```

## License

This project is open-source and available under the [MIT License](LICENSE).
