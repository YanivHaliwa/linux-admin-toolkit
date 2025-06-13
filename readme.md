
# System Management and Utilities Linux

Welcome to my collection of simple yet powerful Linux tools! These are just everyday scripts and commands I've put together to make life easier when working with Linux. Whether you're managing your system, handling files, or doing some network stuff, you'll find something here to save you time and effort.

Think of these as your handy toolbox for common Linux tasks. They're not fancy – just practical. I use these regularly to simplify my workflow, and I hope they'll do the same for you.

The files linux_packs_needed.txt and pip_needed.txt contain lists of pip or apt packages needed for some files to work.

## Battery Management
- **batcon**: Analyzes battery discharge patterns and estimates remaining battery time.
- **batlow**: Monitors battery level and sends notifications for low battery or full charge.
- **batstat**: Logs battery state changes (charging/discharging) with timestamps.


## Info
- **aptsi**: Search installed packages, optionally filter for manually installed ones.
- **bati**: Display binary file contents using bat.
- **cati**: Display binary file contents using cat.
- **fil**: Comprehensive file examination tool (type, hashes, content preview, etc.).
- **fiup**: Find files modified within a specified time frame.
- **lf**: List files or directories using lsd.
- **myusers**: Display user account information.
- **sysinfo**: Show system information (hostname, ID, version, etc.).

## Package Management
- **aptf**: Installs packages listed in a specified file.
- **getpiplist**: Generates a clean list of installed pip packages, saving to 'pip_list.txt'.
- **getpixlist**: Creates a list of packages installed via pipx, saving to 'pix_list.txt'.
- **installdeb**: Installs `.deb` packages using `dpkg` and resolves dependencies.
- **pix**: Installs a Python package using pipx with dependencies.
- **pixfile-i**: Installs multiple Python packages from a file using pipx.
- **pixfile-u**: Uninstalls multiple Python packages from a file using pipx.
- **reqs**: Analyzes Python files to generate a requirements.txt file, identifying external dependencies.
- **updatepips**: Upgrades all installed pip packages and logs any errors.

## Search and File Tools
- **comparef**: Compares files between two folders, identifying unique and common files while ignoring specific directories (like .git and .trash). Provides colorful output for easy visualization.
- **dupl**: Bash script to remove duplicates from a file while preserving order.
- **loc**: Bash script to search for files in a directory using the `locate` command.
- **psearch**: Bash script to search for packages in the APT cache, with optional installed package filtering.
- **readqr**: Reads and decodes QR codes from image files using a barcode recognition API.
- **reversefile**: Reverses Hebrew text in a given file, creating a new file with reversed content.
- **search**: Bash script for flexible file and folder searching with various options.
- **swd**: Python script to search for text in files within a directory, with regex support.
- **swf**: Python script to search for a word or pattern in a file, displaying line numbers.
- **txtf**: Bash script to find specific types of sensitive files in a target directory.
- **list**: Creates a file list from a specified directory, with recursive options and exclusions.
- **compr**: Versatile compression/decompression tool supporting various formats (7z, gzip, bzip2, xz, zstd, zip, rar, lz4, tar).

## Subtitle Management Tools
- **movef**: Moves files from subdirectories to a destination directory.
- **trf**: Translates text files (including subtitles) from English to Hebrew using various translation services, including AI models.
- **trsub**: Downloads subtitles using subliminal and translates them for multiple video files in a folder (using scripts: trf, vidsubs).
- **trw**: Translates words or phrases from English to Hebrew using multiple translation services, including AI models.
- **vidsubs**: Matches video files with their corresponding subtitle files and renames them for consistency.
- **whis**: Transcribes audio files using OpenAI's Whisper model with optional GPT enhancement.
- **whisi**: Transcribes audio using various Whisper models, including Ivrit-AI and faster-whisper versions.
- **vidl**: Downloads any video from website.
- **vidlsub**: Downloads any video from website and transcribes it (using script: whis).

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