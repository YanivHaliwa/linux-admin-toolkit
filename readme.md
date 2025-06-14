# Linux System Management Suite

#version 14.6.25

A comprehensive collection of Linux system administration tools and utilities focused on battery management, system information, package management, and system maintenance. This suite provides essential tools for day-to-day Linux system operations and monitoring.

## 🚀 Features

- **Battery Management** - Monitor, analyze, and get notifications for battery status
- **System Information** - Comprehensive system analysis and reporting tools  
- **Package Management** - Advanced package installation, tracking, and dependency management
- **System Maintenance** - Process management, network tools, and system cleanup utilities

## 📋 Prerequisites

```bash
# Clone the repository
git clone https://github.com/YanivHaliwa/Linux-Stuff.git
cd Linux-Stuff

# Install required packages
sudo apt update
sudo apt install -f < linux_packs_needed.txt
pip install -r pip_needed.txt

# Make scripts executable
chmod +x battery_managment/* info/* package_managment/* system-management-scripts/*
```

## 🛠️ Tools Overview

### Battery Management

#### `batcon` - Battery Analysis Tool
Analyzes battery discharge patterns and estimates remaining battery time with historical data.

#### `batlow` - Battery Monitor & Notifications  
Monitors battery level and sends desktop notifications for low battery warnings and full charge alerts.

#### `batstat` - Battery State Logger
Logs battery state changes (charging/discharging) with timestamps for analysis and tracking.

### System Information

#### `aptsi` - Package Search Tool
Search installed packages with optional filtering for manually installed packages vs. dependencies.

#### `bati` - Binary File Viewer (bat)
Display binary file contents using the bat command with syntax highlighting and formatting.

#### `cati` - Binary File Viewer (cat)
Display binary file contents using cat for quick inspection and analysis.

#### `fil` - Comprehensive File Analyzer
Multi-purpose file examination tool providing file type, hashes, content preview, and metadata analysis.

#### `fiup` - Recent File Finder
Find and list files modified within a specified time frame for change tracking.

#### `lf` - Enhanced Directory Listing
List files and directories using lsd with improved formatting and icons.

#### `myusers` - User Account Information
Display comprehensive user account information and system user details.

#### `sysinfo` - System Information Reporter
Show detailed system information including hostname, system ID, version, and hardware details.

### Package Management

#### `aptf` - Package File Installer
Installs packages listed in a specified file, useful for batch package installation.

#### `getpiplist` - Pip Package Lister
Generates a clean list of installed pip packages, saving results to 'pip_list.txt' for backup or replication.

#### `getpixlist` - Pipx Package Lister  
Creates a list of packages installed via pipx, saving to 'pix_list.txt' for environment documentation.

#### `installdeb` - DEB Package Installer
Installs `.deb` packages using `dpkg` and automatically resolves dependencies with apt.

#### `pixfile-i` - Batch Pipx Installer
Installs multiple Python packages from a requirements file using pipx for isolated environments.

#### `pixfile-u` - Batch Pipx Uninstaller
Uninstalls multiple Python packages from a file using pipx for clean environment management.

#### `reqs` - Requirements Generator
Analyzes Python files to generate requirements.txt, automatically identifying external dependencies.

#### `updatepips` - Pip Upgrade Manager
Upgrades all installed pip packages with error logging and dependency conflict resolution.

## System Management Scripts

- **active**: Checks if a specified process is running.
- **clean**: Cleans up unused packages and dependencies.
- **heat**: Monitors system temperatures, calculating averages for CPU, GPU, package, and NVMe.
- **myip**: Displays various IP addresses, including VPN interfaces, WLAN, and public IP.
- **onewin**: Manages multiple windows of a specified process, keeping only one open.
- **port**: A Bash script for checking and managing processes using a specific port.
- **resetnet**: Resets network settings and services.
- **sysa**: Manages system services by enabling or disabling them.
- **update**: Updates and upgrades system packages, including fixing broken dependencies.

## Author

Created by [Yaniv Haliwa](https://github.com/YanivHaliwa) for security testing and educational purposes.
