# Installing Ubuntu 24.04 LTS via WSL2 on Windows 11

Installing **Ubuntu 24.04 LTS** using **WSL2 (Windows Subsystem for Linux)** on **Windows 11** is one of the easiest ways to get a full Linux development environment without installing a virtual machine or dual booting.

Windows 11 already includes WSL features, so you can usually install Ubuntu with **a single command**.

This guide will walk you through the complete setup.

---

# Table of Contents

- [Prerequisites](#prerequisites)
- [Step 1 — Enable WSL and Install Ubuntu](#step-1--enable-wsl-and-install-ubuntu)
- [Step 2 — Initialize Ubuntu](#step-2--initialize-ubuntu)
- [Step 3 — Verify WSL Version](#step-3--verify-wsl-version)
- [Step 4 — Update Ubuntu Packages](#step-4--update-ubuntu-packages)
- [Step 5 — Install Development Tools](#step-5--install-development-tools)
- [Pro Tips for Windows 11 Users](#pro-tips-for-windows-11-users)
- [Conclusion](#conclusion)

---

# Prerequisites

Before starting, make sure:

- You are using **Windows 11**
- Your system supports **virtualization**
- You have **Administrator access**

You will also need an internet connection to download Ubuntu.

---

# Step 1 — Enable WSL and Install Ubuntu

First, open **PowerShell** or **Command Prompt** as an **Administrator**.

### Open Terminal as Administrator

1. Right-click the **Start Button**
2. Click **Terminal (Admin)**

---

## View Available Linux Distributions

Run the following command to see the Linux distributions available for installation:

```powershell
wsl --list --online
