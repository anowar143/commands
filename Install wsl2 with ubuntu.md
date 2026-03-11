# Installing Ubuntu 24.04 LTS via WSL2 on Windows 11

Installing **Ubuntu 24.04 LTS** via **WSL2 (Windows Subsystem for Linux)** on **Windows 11** is a streamlined process. Since Windows 11 has WSL features built-in, you can usually complete the setup with a single command.

---

## 1. Enable WSL and Install Ubuntu

Open **PowerShell** or **Command Prompt** as an **Administrator**.

> Right-click the **Start button** → Select **Terminal (Admin)**

### Check Available Linux Distributions

```powershell
wsl --list --online
