
## **Linux Overview**

### **What is Linux?**
- Linux is an open-source operating system modeled on Unix and developed in the **C programming language**.
- Some of the most popular Linux distributions include **Ubuntu, Fedora, Debian, CentOS**.

---

## **Features of Linux**
- **Open Source** – Linux is freely available and can be modified by anyone.
- **Cost-Effective** – Significantly reduces monitoring and licensing costs.
- **Multi-User and Multi-Tasking** – Supports multiple users and can run multiple processes simultaneously.
- **Security** – Known for strong security features, including user permissions, firewalls, and encryption.
- **Wide Range of Distributions** – Different distros for desktop computing, servers, development, and embedded systems.

---

## **Common Uses of Linux**
- **Servers** – Widely used in web servers, database servers, and cloud infrastructure.
- **Desktops** – Preferred by enthusiasts and professionals for its flexibility and control.
- **Embedded Systems** – Used in routers, smart TVs, IoT devices.
- **Development** – Many developers prefer Linux for programming due to its powerful command-line tools.
- **Supercomputing** – The majority of the world's fastest supercomputers run on Linux.

---

## **Components of a Linux System**
- **Kernel** – The core of the OS, managing hardware resources and system processes.
- **Shell** – A command-line interface that allows users to interact with the system.
- **Software Libraries** – A set of programming code used to develop and design software applications.
- **Package Management** – Tools for installing, removing, configuring, and upgrading software.
  - **Examples**: `dpkg`, `RPM`
- **Bootloader** – A program that loads the OS when the system starts.
  - **Examples**: `GNU GRUB`, `Syslinux`

---

## **Architecture of Linux OS**
- **Hardware** – CPU, RAM, ROM, Hard Disk.
- **Kernel** – Acts as an interface between applications and hardware.
- **Shell** – Takes user commands and forwards them to the kernel.
- **Applications** – User-level programs and utilities.

---

## **How the Shell Works?**
- The shell receives a command or script, converts it into binary, and sends it to the kernel.
- **Example:**
  ```
  cat or grep → bash → 101010011 → Linux kernel
  ```

---

## **Types of Files in Linux**
- `-` **Normal file**
- `d` **Directory**
- `l` **Symbolic link**

---

## **Runlevels in Linux**
Runlevels (or **systemd targets** in modern Linux) control the system's state by managing which services and processes run at startup.

| Runlevel | Description |
|----------|-------------|
| **0** | Halt (Shutdown the system) |
| **1** | Single-user mode (Maintenance mode, no networking) |
| **2** | Multi-user mode without networking |
| **3** | Multi-user mode with networking (Text-based interface) |
| **4** | Unused (Can be customized) |
| **5** | Multi-user mode with GUI (Graphical mode) |
| **6** | Reboot |

---