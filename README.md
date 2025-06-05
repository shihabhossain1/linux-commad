# Linux Commands - Basic to Advanced

## Table of Contents
1. [File System Commands](#file-system-commands)
2. [File Handling Commands](#file-handling-commands)
3. [File Permissions](#file-permissions)
4. [Process Management](#process-management)
5. [System Information](#system-information)
6. [Networking](#networking)
7. [User Management](#user-management)
8. [Package Management](#package-management)
9. [Disk Usage](#disk-usage)
10. [Searching](#searching)
11. [Compression/Archiving](#compressionarchiving)
12. [Text Processing](#text-processing)
13. [SSH](#ssh)
14. [Advanced Commands](#advanced-commands)

---

## File System Commands

### Navigation
```bash
pwd                 # Print working directory
cd <directory>      # Change directory
cd ~ or cd          # Go to home directory
cd -                # Go to last directory
cd ..               # Go to parent directory
ls                  # List directory contents
ls -l               # List in long format
ls -a               # List all including hidden files
ls -lh              # List with human readable sizes
tree                # Display directory structure as tree
```

### Directory Operations
```bash
mkdir <dir>         # Create directory
mkdir -p dir1/dir2  # Create nested directories
rmdir <dir>         # Remove empty directory
rm -r <dir>         # Remove directory recursively
mv <old> <new>      # Move/rename file or directory
cp <src> <dest>     # Copy file
cp -r <src> <dest>  # Copy directory recursively
```

---

## File Handling Commands

```bash
touch <file>        # Create empty file or update timestamp
cat <file>          # Display file contents
less <file>         # View file page by page
head <file>         # Show first 10 lines of file
head -n 5 <file>    # Show first 5 lines
tail <file>         # Show last 10 lines
tail -f <file>      # Follow file as it grows (useful for logs)
nano <file>         # Edit file with nano editor
vim <file>          # Edit file with vim editor
rm <file>           # Remove file
rm -i <file>        # Remove with confirmation
```

---

## File Permissions

```bash
chmod 755 <file>    # Change file permissions (owner:rwx, group:r-x, others:r-x)
chmod +x <file>     # Make file executable
chmod -x <file>     # Remove executable permission
chown user:group <file>  # Change file owner and group
chown user <file>   # Change file owner
chgrp group <file>  # Change file group
umask               # Show default permission mask
```

---

## Process Management

```bash
ps                  # Display active processes
ps aux              # Display all processes
top                 # Interactive process viewer
htop                # Enhanced interactive process viewer (needs installation)
kill <PID>          # Terminate process by PID
kill -9 <PID>       # Force kill process
killall <name>      # Kill all processes by name
pkill <pattern>     # Kill processes by pattern
bg                  # Resume suspended job in background
fg                  # Bring job to foreground
jobs                # List active jobs
nice -n 10 <cmd>    # Run command with modified priority
renice 10 <PID>     # Change priority of running process
```

---

## System Information

```bash
uname -a            # Show all system information
hostname            # Show system hostname
uptime              # Show system uptime and load
whoami              # Display current user
date                # Show current date and time
cal                 # Show calendar
free -h             # Show memory usage (human readable)
df -h               # Show disk space (human readable)
lscpu               # Show CPU information
lsblk               # List block devices
lsusb               # List USB devices
lspci               # List PCI devices
dmidecode           # Show hardware information
```

---

## Networking

```bash
ifconfig            # Network interfaces information (deprecated)
ip a                # Show IP addresses
ip route            # Show routing table
ping <host>         # Ping host
traceroute <host>   # Trace route to host
netstat -tulnp      # Show listening ports and processes
ss -tulnp           # Modern replacement for netstat
dig <domain>        # DNS lookup
nslookup <domain>   # DNS lookup (older)
wget <url>          # Download file from web
curl <url>          # Transfer data from/to server
scp <file> user@host:/path  # Secure copy over SSH
rsync -avz <src> <dest>     # Efficient file transfer
```

---

## User Management

```bash
sudo <command>      # Run command as superuser
su                  # Switch to root user
su - <user>         # Switch to specific user
useradd <user>      # Add new user
userdel <user>      # Delete user
usermod <options> <user>  # Modify user
passwd <user>       # Change user password
groupadd <group>    # Add new group
groupdel <group>    # Delete group
id <user>           # Show user information
who                 # Show logged in users
w                   # Show logged in users and their activities
last                # Show last logged in users
```

---

## Package Management

### Debian/Ubuntu (APT)
```bash
apt update          # Update package list
apt upgrade         # Upgrade all packages
apt install <pkg>   # Install package
apt remove <pkg>    # Remove package
apt purge <pkg>     # Remove package and config files
apt search <term>   # Search for package
apt show <pkg>      # Show package information
apt list --installed # List installed packages
apt autoremove      # Remove unused packages
```

### RedHat/CentOS (YUM/DNF)
```bash
yum install <pkg>   # Install package (older)
dnf install <pkg>   # Install package (newer)
yum remove <pkg>    # Remove package
yum update          # Update all packages
yum search <term>   # Search for package
yum info <pkg>      # Show package information
rpm -i <pkg.rpm>    # Install RPM package
rpm -e <pkg>        # Remove RPM package
```

### Arch Linux (Pacman)
```bash
pacman -S <pkg>     # Install package
pacman -R <pkg>     # Remove package
pacman -Syu         # Update system
pacman -Ss <term>   # Search for package
```

---

## Disk Usage

```bash
df -h               # Show disk space usage
du -h               # Show directory space usage
du -sh <dir>        # Show summary of directory size
ncdu                # Interactive disk usage analyzer
fdisk -l            # List disk partitions
mount               # Show mounted filesystems
umount <device>     # Unmount filesystem
```

---

## Searching

```bash
find <dir> -name "<pattern>"  # Find files by name
find <dir> -type f -size +10M # Find files >10MB
grep "<pattern>" <file>       # Search for pattern in file
grep -r "<pattern>" <dir>     # Recursive grep
grep -i "<pattern>" <file>    # Case insensitive grep
locate <file>                 # Find file using database
updatedb                     # Update locate database
which <cmd>                  # Show full path of command
whereis <cmd>                # Show binary, source, and manual for command
```

---

## Compression/Archiving

```bash
tar -cvf archive.tar <files>  # Create tar archive
tar -xvf archive.tar          # Extract tar archive
tar -czvf archive.tar.gz <files>  # Create gzipped tar archive
tar -xzvf archive.tar.gz      # Extract gzipped tar archive
gzip <file>                  # Compress file (creates .gz)
gunzip <file.gz>             # Decompress .gz file
zip archive.zip <files>      # Create zip archive
unzip archive.zip            # Extract zip archive
7z a archive.7z <files>      # Create 7z archive
7z x archive.7z              # Extract 7z archive
```

---

## Text Processing

```bash
cat <file> | sort            # Sort file contents
cat <file> | uniq            # Show unique lines
cat <file> | wc -l           # Count lines in file
cut -d: -f1 /etc/passwd      # Extract first field delimited by :
awk '{print $1}' <file>      # Print first column
sed 's/old/new/g' <file>     # Replace text in file
tr 'a-z' 'A-Z' < file        # Translate characters to uppercase
diff file1 file2             # Compare files
comm file1 file2             # Compare sorted files
join file1 file2             # Join lines of two files
paste file1 file2            # Merge lines of files
```

---

## SSH

```bash
ssh user@host                # Connect to remote host
ssh -p port user@host        # Connect with specific port
ssh-keygen                  # Generate SSH key pair
ssh-copy-id user@host       # Copy SSH key to remote host
scp file user@host:path     # Secure copy file to remote host
sftp user@host              # Secure FTP connection
```

---

## Advanced Commands

```bash
screen                      # Start terminal multiplexer
tmux                        # Start tmux terminal multiplexer
crontab -e                  # Edit cron jobs
at 10:00                    # Schedule one-time job
watch -n 1 <command>        # Run command repeatedly
alias ll='ls -alF'          # Create command alias
nohup <command> &           # Run command immune to hangups
strace <command>            # Trace system calls
ltrace <command>            # Trace library calls
dd if=/dev/zero of=file bs=1M count=100  # Create 100MB file
```

---

## Tips
- Use `man <command>` to view manual pages for any command
- Use `--help` flag with most commands for quick help
- Use `history` to view command history
- Use `!!` to repeat last command
- Use `!$` to refer to last argument of previous command

This README covers most common Linux commands from basic to advanced level. For more details on any command, consult the manual pages (`man <command>`).
