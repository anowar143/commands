# 🔹 Tutorial: Install WSL and Ubuntu 24.04 on Windows 11

This guide will help you install **Windows Subsystem for Linux (WSL)** and **Ubuntu 24.04** on **Windows 11** for development.

---

## 1️ Enable WSL and Install Ubuntu

Open **PowerShell** or **Command Prompt** as **Administrator**.

Right-click the **Start button** and select:

```
Terminal (Admin)
```

or

```
Windows PowerShell (Admin)
```

---

### Check Available Linux Distributions

Run the following command to see available distributions:

```powershell
wsl --list --online
```

This will display available Linux distributions such as:

```
Ubuntu
Ubuntu-22.04
Ubuntu-24.04
Debian
Kali Linux
```

---

### Install Ubuntu 24.04

Run the command below:

```powershell
wsl --install -d Ubuntu-24.04
```

This command will:

- Enable **WSL**
- Download **Ubuntu 24.04**
- Install the Linux environment automatically

The installation may take a few minutes depending on your internet speed.

---

## 2️ Initialize the Operating System

Once the download finishes, a **new Ubuntu terminal window** will open automatically.

### Wait for Decompression

You may see a message like:

```
Installing, this may take a few minutes...
```

Ubuntu will **decompress the installation files**, which may take a minute.

---

### Create a Linux User

After installation, you will be asked to create a **UNIX user account**.

#### Username

Enter a username for your Linux environment.

Example:

```
Enter new UNIX username: anowar
```

This username does **not need to match your Windows username**.

---

#### Password

Next, create a password:

```
Enter new UNIX password:
Retype new UNIX password:
```

⚠️ **Note**

- You **will not see characters while typing**
- This is a **normal Linux security feature**

---

## 3️ Verify the WSL Version

To ensure your Ubuntu installation is using **WSL Version 2**, open **Windows PowerShell** and run:

```powershell
wsl --list --verbose
```

Example output:

```
NAME            STATE           VERSION
Ubuntu-24.04    Running         2
```

If the version shows **2**, your setup is correct.

---

### Convert to WSL 2 (If Needed)

If the version shows **1**, convert it using:

```powershell
wsl --set-version Ubuntu-24.04 2
```

This may take a few minutes to complete.

---

## 4️ Essential Post-Installation Steps

Once Ubuntu is installed, open the **Ubuntu terminal**.

It is recommended to update your system packages.

---

### Update and Upgrade Packages

Run:

```bash
sudo apt update && sudo apt upgrade -y
```

This command will:

- Update package lists
- Upgrade installed software
- Install the latest security updates

---

### Install Development Tools

If you plan to develop applications using **Python, PHP, Node.js, or C/C++**, install the essential development tools.

Run:

```bash
sudo apt install build-essential -y
```

This installs:

- GCC compiler
- Make tools
- Standard development libraries

---

# ✅ Success!

You now have:

- **WSL installed**
- **Ubuntu 24.04 running**
- **Linux development environment ready**

You can now use Ubuntu on Windows for:

- Django development
- Node.js development
- PHP / Laravel projects
- Docker & DevOps tools

---

## 📌 Useful WSL Commands

Start WSL:

```bash
wsl
```

List installed distributions:

```bash
wsl --list
```

Stop all WSL instances:

```bash
wsl --shutdown
```

Exit Ubuntu terminal:

```bash
exit
```

---

## 📌 Quick Command Summary

```bash
wsl --list --online
wsl --install -d Ubuntu-24.04
wsl --list --verbose
wsl --set-version Ubuntu-24.04 2
sudo apt update && sudo apt upgrade -y
sudo apt install build-essential -y
```
