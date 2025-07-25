# Linux System Management Suite

#version 25.7.25

A comprehensive collection of Linux system administration tools and utilities designed for system administrators, cybersecurity professionals, and power users. This suite provides essential tools for battery management, system information gathering, package management, and advanced system maintenance operations.

## 🚀 Features

- **🔋 Battery Management** - Advanced battery monitoring, analysis, and intelligent notifications
- **📊 System Information** - Comprehensive system analysis, file examination, and reporting tools  
- **📦 Package Management** - Advanced package installation, dependency management, and environment control
- **⚙️ System Management** - Network monitoring, service control, temperature monitoring, and process management

## 📋 Prerequisites & Installation

```bash
# Clone the repository
git clone https://github.com/YanivHaliwa/linux-admin-toolkit.git
cd linux-admin-toolkit

# Install required system packages
sudo apt update
sudo apt install -f < linux_packs_needed.txt

# Install required Python packages
pip install -r pip_needed.txt

# Make all scripts executable
chmod +x battery-management/* system-info/* package-management/* system-management/*
```

### Required Dependencies
- **System packages**: `acpi`, `upower`, `sensors`, `lsof`, `fuser`, `binwalk`, `steghide`, `exiftool`, `mpg123`
- **Python packages**: `ast`, `importlib.metadata`, `stdlib_list`, `Xlib`
- **Optional**: `lsd` (enhanced ls), `batcat` (syntax highlighting)

## 🔋Battery Management

Advanced battery monitoring and analysis tools for laptop users and system administrators.

### `batcon` - Battery Analytics Engine ⭐
**Purpose**: Analyzes battery discharge patterns and predicts remaining battery life using historical data.

**Features**:
- Statistical analysis of discharge/charge cycles
- Time-based battery life prediction
- Automatic log file management and cleanup
- Color-coded output with professional formatting
- Smart duration formatting (hours:minutes vs minutes)

**Usage Examples**:
```bash
# Analyze battery patterns and predict remaining time
./batcon

# Example output:
# Total Recorded Discharge Durations: 15
# Last 10 Discharge Durations: [2:45, 3:12, 2:58, 3:05, 2:50, 3:20, 2:40, 3:15, 2:55, 3:08]
# Average Duration Without Charge: 3:02
# Current State: Discharging
# Time Since Last State Change: 45.3
# Estimated Time Remaining Before Battery is Depleted: 2:17
```

**Use Cases**:
- Laptop battery health monitoring
- Power management optimization
- System administration and maintenance
- Mobile device battery analysis

### `bat-warning` - Intelligent Battery Monitor ⭐
**Purpose**: Real-time battery monitoring with audio and desktop notifications.

**Features**:
- Smart notification system (prevents spam)
- Audio alerts for low battery and full charge
- File locking to prevent overlapping executions
- Configurable battery thresholds
- Desktop environment integration

**Usage Examples**:
```bash
# Run as background service (recommended)
./bat-warning &

# Or add to crontab for automatic monitoring
crontab -e
# Add: */5 * * * * /path/to/bat-warning
```

**Configuration**:
- Low battery threshold: 25% (customizable)
- Audio files: `charge_now.mp3`, `battery_full.mp3`
- Notifications work with most desktop environments

**Use Cases**:
- Automated laptop battery monitoring
- Preventing unexpected shutdowns
- Battery health maintenance
- System administration alerts

### `batstat` - Battery State Logger
**Purpose**: Logs battery state changes for analysis and troubleshooting.

**Features**:
- Automatic state change detection
- Timestamp logging for analysis
- Integration with `batcon` for historical data
- Minimal resource usage

**Usage Examples**:
```bash
# Log battery state changes
./batstat

# View battery log
cat ~/.cache/battery_state_log.txt
# 2025-06-14 09:30:15 - State changed to: discharging
# 2025-06-14 12:45:22 - State changed to: charging
```

**Use Cases**:
- Battery behavior analysis
- System power management debugging
- Historical battery usage tracking
- Integration with monitoring systems

## 📊 System Information Tools

Comprehensive system analysis and file examination utilities for security professionals and system administrators.

### `fil` - Forensic File Analyzer ⭐⭐
**Purpose**: Multi-tool file analysis for cybersecurity, forensics, and system administration.

**Features**:
- Comprehensive file analysis using multiple tools
- Hash calculation (SHA-256, MD5)
- Binary analysis with binwalk and steghide
- Metadata extraction with exiftool
- Hex dump and string analysis
- Color-coded professional output

**Usage Examples**:
```bash
# Analyze suspicious file
./fil suspicious_file.exe

# Analyze image for hidden data (steganography)
./fil image.jpg

# Examine binary for embedded files
./fil firmware.bin
```

**Analysis Tools Used**:
- `stat` - File statistics and permissions
- `file` & `mimetype` - File type detection
- `sha256sum` & `md5sum` - Hash calculation
- `strings` - Readable string extraction
- `binwalk` - Binary analysis and embedded file detection
- `steghide` - Steganography detection
- `exiftool` - Metadata extraction
- `hexdump` & `xxd` - Hex analysis

**Use Cases**:
- Cybersecurity investigations
- Malware analysis
- CTF competitions
- Digital forensics
- File integrity verification

### `aptsi` - Advanced Package Search ⭐
**Purpose**: Enhanced package search with manual vs dependency filtering.

**Features**:
- Search installed packages by name
- Filter manually installed packages (-m flag)
- Exclude dependency packages from results
- Clean, formatted output

**Usage Examples**:
```bash
# Search for all packages containing "python"
./aptsi python

# Search only manually installed packages
./aptsi -m python

# Find manually installed development tools
./aptsi -m dev
```

**Use Cases**:
- System audit and inventory
- Package management and cleanup
- Dependency analysis
- System migration planning

### `fiup` - Time-Based File Finder ⭐
**Purpose**: Find files modified within specified time frames with pattern matching.

**Features**:
- Time-based file filtering
- Pattern matching support
- Enhanced output with `lsd`
- Excludes hidden files by default
- User-specific file filtering

**Usage Examples**:
```bash
# Find files modified in last 7 days
./fiup . 7

# Find Python files modified in last 3 days
./fiup /home/user 3 "*.py"

# Find multiple file types modified recently
./fiup /var/log 1 "*.log" "*.txt"
```

**Use Cases**:
- Security auditing
- Change tracking
- Backup planning
- System troubleshooting
- Development workflow

### `lf` - Enhanced Directory Listing
**Purpose**: Improved directory listing with file/folder separation.

**Usage Examples**:
```bash
# List files in current directory
./lf

# List directories only
./lf d

# List files in specific location
./lf /path/to/directory
```

### `bati` & `cati` - Binary File Viewers
**Purpose**: Quick examination of binary files and executables.

**Usage Examples**:
```bash
# View binary with syntax highlighting
./bati python3

# View binary with plain cat
./cati gcc
```

## 📦 Package Management

Advanced package management tools for system administrators and developers.

### `reqs` - Python Requirements Generator ⭐⭐⭐
**Purpose**: Automatically generate requirements.txt using AST parsing (Advanced Python technique).

**Features**:
- AST-based import analysis (no code execution)
- Distinguishes between stdlib and external packages
- Recursive directory scanning
- Professional error handling
- Supports both files and directories

**Usage Examples**:
```bash
# Generate requirements for single file
./reqs script.py

# Generate requirements for entire project
./reqs /path/to/project

# Generate requirements for current directory
./reqs .
```

**Technical Details**:
- Uses Python AST (Abstract Syntax Tree) parsing
- Leverages `stdlib_list` for standard library detection
- Analyzes import statements without executing code
- Handles both `import` and `from...import` statements

**Use Cases**:
- Python project deployment
- Dependency management
- Docker container optimization
- Virtual environment setup
- Code analysis and auditing

### `updatepips` - Advanced Pip Upgrade Manager ⭐⭐
**Purpose**: Sophisticated pip package upgrade system with retry logic and conflict resolution.

**Features**:
- Comprehensive logging system
- Multiple retry mechanisms
- Dependency conflict detection
- Failed package tracking
- Automatic dependency resolution

**Usage Examples**:
```bash
# Upgrade all pip packages with full logging
./updatepips

# Check logs for issues
cat ~/log.txt
cat ~/unresolved_packages.txt
```

**Process Flow**:
1. Upgrade pip itself
2. List all installed packages
3. Attempt to upgrade each package
4. Log failures and retry
5. Handle dependency conflicts
6. Generate comprehensive reports

**Use Cases**:
- System maintenance
- Development environment updates
- CI/CD pipeline maintenance
- Package dependency management

### `aptf` - Batch APT Installer ⭐
**Purpose**: Install multiple packages from file with comprehensive error handling.

**Features**:
- Batch package installation from file
- Comprehensive file validation
- Failed package tracking
- Progress reporting
- Automatic dependency resolution

**Usage Examples**:
```bash
# Install packages from file
./aptf package_list.txt

# Example package_list.txt:
# vim
# git
# htop
# curl
# wget
```

**Error Handling**:
- File existence verification
- Read permission checking
- Empty file detection
- Failed package logging

### `installdeb` - DEB Package Installer
**Purpose**: Install DEB packages with automatic dependency resolution.

**Usage Examples**:
```bash
# Install single DEB package
./installdeb package.deb

# Install multiple DEB packages
./installdeb *.deb
```

### `pixfile-i` & `pixfile-u` - Pipx Batch Operations
**Purpose**: Batch install/uninstall Python packages using pipx.

**Usage Examples**:
```bash
# Batch install from requirements file
./pixfile-i requirements.txt

# Batch uninstall from list
./pixfile-u packages_to_remove.txt
```

## ⚙️ System Management

Advanced system administration tools for monitoring, network management, and service control.

### `heat` - Multi-Sensor Temperature Monitor ⭐⭐⭐
**Purpose**: Advanced temperature monitoring with statistical analysis across multiple sensors.

**Features**:
- Multi-sensor monitoring (CPU, GPU, Package, NVMe)
- Statistical analysis with averages
- Floating-point calculations using `bc`
- Overall system temperature calculation
- Clean, concise output

**Usage Examples**:
```bash
# Monitor system temperatures
./heat

# Example output:
# Avg Temp:
# 42.75°C
```

**Monitored Components**:
- CPU cores (individual and average)
- GPU temperatures
- Package temperatures
- NVMe SSD temperatures
- Overall system average

**Use Cases**:
- System health monitoring
- Performance optimization
- Thermal management
- Server monitoring
- Overclocking safety
- **Status bar integration** - Perfect for desktop status bars and system monitoring widgets

### `myip` - Network Interface Analyzer ⭐⭐⭐
**Purpose**: Comprehensive network interface and IP address detection for security professionals.

**Features**:
- VPN interface detection
- Point-to-point interface analysis
- Public IP detection with fallback services
- IP address validation
- Multi-service redundancy

**Usage Examples**:
```bash
# Display all network information
./myip

# Example output:
# tun0 = 10.10.14.15  vpn1 = 192.168.1.100  wlan0 = 192.168.1.50
# PUBLIC = 203.0.113.42
```

**Detection Methods**:
- Point-to-point interfaces (VPNs)
- WLAN interfaces
- Multiple public IP services (icanhazip.com, ipinfo.io, ifconfig.me)
- IP validation with regex

**Use Cases**:
- Penetration testing
- VPN troubleshooting
- Network security auditing
- System administration
- Remote access setup
- **Status bar integration** - Ideal for desktop status bars to monitor network connections and public IP

### `onewin` - X11 Window Management ⭐⭐⭐
**Purpose**: Advanced window management using X11 programming for duplicate process cleanup.

**Features**:
- X11 window system integration
- Process grouping and analysis
- Duplicate window detection
- Selective process termination
- Desktop environment integration

**Usage Examples**:
```bash
# Kill all duplicate processes
./onewin

# Kill duplicates of specific process
./onewin firefox

# Help information
./onewin -h
```

**Technical Details**:
- Uses Python Xlib bindings
- Interacts directly with X Window System
- Process ID and window correlation
- Excludes system processes (panel, desktop)

**Use Cases**:
- Desktop cleanup and optimization
- Resource management
- System administration
- Development environment maintenance

### `sysa` - Service Management Wrapper ⭐
**Purpose**: Simplified systemctl service management with clear syntax.

**Features**:
- Simple on/off service control
- Automatic enable/disable with start/stop
- Clear status reporting
- Error handling

**Usage Examples**:
```bash
# Enable and start a service
./sysa apache2 on

# Stop and disable a service
./sysa apache2 off

# Control any systemd service
./sysa bluetooth on
./sysa networking off
```

**Use Cases**:
- System administration
- Service management automation
- Boot process control
- System optimization

### `resetnet` - Network Reset for Security Testing ⭐
**Purpose**: Network interface reset specifically designed for penetration testing and wireless security.

**Features**:
- Airmon-ng integration
- Monitor mode cleanup
- Interface renaming and management
- Network service restart
- Wireless adapter reset

**Usage Examples**:
```bash
# Reset network interfaces after penetration testing
./resetnet

# Use after wireless security testing
# Resets wlan0 from monitor mode to managed mode
```

**Process Flow**:
1. Stop monitor mode interfaces
2. Reset interface names
3. Configure managed mode
4. Restart network services
5. Reset DNS resolution

**Use Cases**:
- Penetration testing cleanup
- Wireless security testing
- Network troubleshooting
- Security research
- Ethical hacking workflows

## 📁 Configuration Files

### `linux_packs_needed.txt`
System packages required for all tools to function properly.

### `pip_needed.txt` 
Python packages required for Python-based tools.

## 🛡️ Security Considerations

- **File Permissions**: Ensure scripts are executable only by authorized users
- **Sudo Access**: Some tools require sudo privileges for system operations
- **Network Tools**: `myip` makes external network requests
- **System Modification**: Package management tools modify system state
- **Process Management**: Window management tools can terminate processes

## 📖 Documentation

Each tool includes built-in help and error messages. For detailed information:
- Run tools without arguments to see usage information
- Check individual script comments for technical details
- Review log files in `~/.cache/` and `~/` for debugging

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

Created by [Yaniv Haliwa](https://github.com/YanivHaliwa) for security testing and educational purposes.

---

**⚠️ Disclaimer**: These tools are designed for educational purposes and legitimate system administration. Users are responsible for complying with applicable laws and regulations when using these tools.
