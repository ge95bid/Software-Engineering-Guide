
# WSL-Installation-on-Windows-Guide

This repository is a guide to install WSL with the Linux Distribution Ubuntu on Windows 10 and 11.

## Table of Contents
- [Installing WSL2 with Ubuntu on Windows 10](#installing-wsl2-with-ubuntu-on-windows-10)
  - [Step 1: Enable WSL (Windows Subsystem for Linux)](#step-1-enable-wsl-windows-subsystem-for-linux)
  - [Step 2: Enable Virtual Machine Platform](#step-2-enable-virtual-machine-platform)
  - [Step 3: Set WSL2 as Default Version](#step-3-set-wsl2-as-default-version)
  - [Step 4: Install a Linux Distribution (Ubuntu)](#step-4-install-a-linux-distribution-ubuntu)
  - [Step 5: Launch Ubuntu and Set It Up](#step-5-launch-ubuntu-and-set-it-up)
  - [Step 6: Verify Installation](#step-6-verify-installation)
- [Installing WSL2 with Ubuntu on Windows 11](#installing-wsl2-with-ubuntu-on-windows-11)
  - [Step 1: Open Windows Terminal (or PowerShell) as Administrator](#step-1-open-windows-terminal-or-powershell-as-administrator)
  - [Step 2: Install WSL and Set Default to WSL2](#step-2-install-wsl-and-set-default-to-wsl2)
  - [Step 3: Set Up Ubuntu](#step-3-set-up-ubuntu)
  - [Step 4: Verify Installation](#step-4-verify-installation)

## Installing WSL2 with Ubuntu on Windows 10

To install **WSL2 (Windows Subsystem for Linux 2)** with Ubuntu on **Windows 10**, follow these steps:

### Step 1: Enable WSL (Windows Subsystem for Linux)
1. **Open PowerShell as Administrator:**
   - Right-click the **Start menu** button and select **Windows PowerShell (Admin)**.

2. **Enable WSL:**
   Run the following command to enable WSL:
   ```powershell
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   ```

### Step 2: Enable Virtual Machine Platform
1. **Still in PowerShell (Admin), enable the Virtual Machine Platform (required for WSL2):**
    ```powershell
    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
    ```

### Step 3: Set WSL2 as Default Version
1. **After enabling WSL and the Virtual Machine Platform, set WSL2 as the default version:**
    ```powershell
    wsl --set-default-version 2
    ```

### Step 4: Install a Linux Distribution (Ubuntu)
1. **Open Microsoft Store: Go to the Microsoft Store and search for Ubuntu.**
2. **Install Ubuntu:**
   - There are many versions of Ubuntu but choose the default one called Ubuntu
   - Click Get or Install
   - Wait for the installation to complete

### Step 5: Launch Ubuntu and Set It Up
1. **Open Ubuntu: After installation, launch the Ubuntu app from the Start menu.**
2. Initial Setup:
   - The first time Ubuntu launches, it will take a few minutes to set up. **Do not disrupt this process if possible**
   - After set up, you will be prompted to create a new user account and set a password for root privileges.

### Step 6: Verify Installation
1. **Check WSL Version:**
   - In Powershell, run the following command to check the version of the installed Linux distributions:
     ```powershell
     wsl -l -v
     ```
   - `-l` lists all Linux Distributions in WSL
   - `-v` shows more details and it is better formatted than without
   - If the command is successful, it should show Ubuntu running under WSL2

## Installing WSL2 with Ubuntu on Windows 11

### Step 1: Open Windows Terminal (or PowerShell) as Administrator
Open **Windows Terminal (Admin)** (or **PowerShell** as Administrator if you don't have Terminal installed).

### Step 2: Install WSL and Set Default to WSL2
In the Terminal window, run the following command to install WSL and set WSL2 as the default version:

```powershell
wsl --install
```

This command does three things automatically:
- Installs WSL.
- Enables the Virtual Machine Platform.
- Sets WSL2 as the default version.

By default, the installation will also include **Ubuntu** as the default Linux distribution.

Restart your computer when prompted.

### Step 3: Set Up Ubuntu
After restarting, launch **Ubuntu** from the Start menu or from the terminal using:

```powershell
wsl
```

#### Initial Setup:
- The first time Ubuntu launches, it will take a few minutes to set up.
- You will be prompted to create a new user account and set a password for Ubuntu.

### Step 4: Verify Installation
To check which version of WSL you are using and verify the distribution, run:

```powershell
wsl -l -v
```

This will show **Ubuntu** running under WSL2.
