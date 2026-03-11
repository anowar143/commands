# Install WSL and Ubuntu 24.04 on Windows

This guide explains how to install **Windows Subsystem for Linux (WSL)** and **Ubuntu 24.04** on Windows.

---

## 1. Enable WSL and Install Ubuntu

Open **PowerShell** or **Command Prompt** as an **Administrator**.

- Right-click the **Start** button  
- Select **Terminal (Admin)** or **Windows PowerShell (Admin)**

### Check Available Linux Distributions

Run the following command to see available Linux distributions:

```powershell
wsl --list --online
```
### Install Ubuntu 24.04

#### Run the command below:

wsl --install -d Ubuntu-24.04

This will download and install Ubuntu automatically.

2. Initialize the Operating System

Once the download finishes, a new Ubuntu terminal window will open.

Wait for Decompression

It may take a minute while Ubuntu decompresses installation files.

Create a User

You will be asked to create a UNIX user.

Username

Enter a default UNIX username.
This does not need to match your Windows username.

Password

Enter a password.

⚠️ Note: You will not see characters while typing the password.
This is normal in Linux terminals for security reasons.

3. Verify the WSL Version

To make sure Ubuntu is using WSL Version 2, run this command in Windows PowerShell:

wsl --list --verbose

Example output:

NAME            STATE           VERSION
Ubuntu-24.04    Running         2

If the version shows 2, everything is correctly configured.

Convert to WSL 2 (If Needed)

If the version shows 1, convert it with this command:

wsl --set-version Ubuntu-24.04 2
4. Essential Post-Installation Steps

After Ubuntu is installed, open the Ubuntu terminal and update your system.

Update and Upgrade Packages
sudo apt update && sudo apt upgrade -y

This will:

Update the package list

Upgrade installed software

Install Development Tools

If you plan to do development (Python, PHP, Node.js, etc.), install the essential build tools.

sudo apt install build-essential -y

This installs:

GCC compiler

Make

Standard development libraries

✅ Installation Complete

You now have:

WSL installed

Ubuntu 24.04 running

Development tools installed

Your system is ready for Linux development on Windows.

Helpful Commands
Command	Description
wsl	Start WSL
wsl --list	Show installed distributions
wsl --shutdown	Stop all WSL instances
exit	Exit Ubuntu terminal
Resources

Official Microsoft WSL Documentation

Ubuntu Documentation

