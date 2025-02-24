## Default Folders in Linux

### 1. `/bin` - Essential Command Binaries
This directory stores essential command binaries needed for basic system operation. These commands are available for all users and can be used in single-user mode.

#### Examples:
- **File Management:** `ls`, `cp`, `mv`, `rm`
- **Navigation:** `cd`, `pwd`
- **File Operations:** `cat`, `echo`, `touch`
- **Process Control:** `ps`, `kill`
- **System Info:** `uname`, `df`, `free`
- **Compression:** `gzip`, `tar`

---

### 2. `/etc` - System Configuration Files
This directory contains system configuration files for the entire system, including settings for system services, user management, networking, and applications.

#### Examples:
- **System Configuration:** `/etc/passwd`, `/etc/group`, `/etc/fstab`
- **Network Settings:** `/etc/hosts`, `/etc/resolv.conf`, `/etc/network/interfaces`
- **Service Configs:** `/etc/systemd/`, `/etc/init.d/`
- **Package Configs:** `/etc/apt/`, `/etc/yum.conf`, `/etc/dpkg/`
- **Security & Access:** `/etc/ssh/sshd_config`, `/etc/sudoers`

---

### 3. `/home` - User Home Directories
This directory stores personal files and settings for each user on the system. Every user gets a separate subdirectory inside `/home`.

#### Example Structure:
```
/home/
   ├── user1/
   │   ├── Documents/
   │   ├── Downloads/
   │   ├── .ssh/
   │   ├── .config/
   ├── user2/
       ├── Documents/
       ├── Downloads/
       ├── .ssh/
       ├── .config/
```

---

### 4. `/root` - Root User Home Directory
The home directory of the root (superuser) account. It is separate from `/home` because the root user has special privileges and requires a more secure environment.

#### Characteristics:
- Only accessible by the root user; `sudo` required for others.
- Stores root’s personal files and configurations, similar to `/home/user`.
- Used for system administration tasks like maintenance, backups, and scripts.

#### Example Files:
- **Hidden Config Files:** `.bashrc`, `.profile`, `.ssh/`
- **System Scripts:** `backup.sh`, `monitoring.py`
- **Logs & Reports:** `error.log`, `sys_status.txt`
- **Temporary Files:** `tempfile.txt`, `debug.log`

---

### 5. `/dev` - Device Files
This directory contains device files that represent hardware and virtual devices.

#### Examples:
- **Storage Devices:** `/dev/sda`, `/dev/sdb1`

---

### 6. `/usr` - User-Related System Files
This directory contains user-related system files, applications, and libraries.

#### Examples:
- **Common system binaries:** `/usr/bin/` (`ls`, `grep`, `vim`, `wget`)
- **System administration binaries:** `/usr/sbin/` (`apachectl`, `iptables`)

---

### 7. `/proc` - Virtual Filesystem for System and Process Information
This directory provides real-time system and process information.

#### Examples:
- **CPU Details:** `/proc/cpuinfo` (`cat /proc/cpuinfo`)
- **System Memory Usage:** `/proc/meminfo` (`cat /proc/meminfo`)
- **System Uptime:** `/proc/uptime` (`cat /proc/uptime`)

---

### 8. `/opt` - Optional Software and Third-Party Applications
This directory is used for manually installed software and third-party applications.

---

### 9. `/tmp` - Temporary Files
This directory is used for temporary files, which are cleared on reboot.

---

### 10. `/var` - Variable Data
This directory contains variable data such as logs, caches, mail, and databases.

---
