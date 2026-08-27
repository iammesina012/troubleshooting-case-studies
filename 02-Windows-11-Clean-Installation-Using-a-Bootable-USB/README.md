# Windows 11 Clean Installation Using a Bootable USB

## Summary

> **Issue:** Windows could not be reinstalled using the built-in recovery options.
>
> **Solution:** Created a Windows 11 bootable USB using Microsoft's Media Creation Tool and performed a clean installation.
>
> **Result:** Windows 11 was successfully installed, and the laptop was ready for driver installation, Windows updates, and normal use.

---

## Overview

After several attempts to reinstall Windows using the built-in recovery options, the installation kept failing. Since the built-in methods were no longer reliable, I decided to perform a clean Windows 11 installation using a bootable USB.

This scenario documents how I created the installation media, configured the BIOS, installed Windows 11, and completed the initial setup.

---

## Environment

**Device:** Acer Aspire 7 A715-42G

**Operating System:** Windows 11

**Storage:** SSD

**USB Drive:** SanDisk USB Flash Drive

**Installation Tool:** Microsoft Windows 11 Media Creation Tool

---

## Installation Process

### 1. Tried Windows Cloud Download

Before creating a bootable USB, I first tried reinstalling Windows using **Reset this PC**.

I selected:

- Remove Everything
- Cloud Download

I chose **Cloud Download** because it downloads a fresh copy of Windows from Microsoft instead of using the files already stored on the laptop. Since I suspected the current Windows installation might already be corrupted, I wanted to use a fresh installation source.

However, the installation never completed successfully.

During different attempts:

- Windows displayed **"There was a problem resetting your PC."**
- Another attempt reached about **99%**, but instead of reinstalling Windows, it returned to the Windows Recovery Environment (WinRE).
- I was still able to sign in using my existing PIN afterward, confirming that Windows had not been reinstalled.

After several failed attempts, I decided to use a bootable USB instead.

---

### 2. Created a Windows 11 Bootable USB

Since the Acer laptop wasn't reliable enough to prepare the installer, I used another computer.

I:

- Downloaded the official Windows 11 Media Creation Tool from Microsoft.
- Inserted a SanDisk USB flash drive.
- Selected **Create installation media**.
- Waited for Windows 11 to download and create the bootable USB.

After the process finished, I safely removed the USB drive.

---

### 3. Enabled the F12 Boot Menu

I connected the USB drive to the Acer laptop and tried pressing **F12** during startup.

Nothing happened, and Windows started normally.

To fix this, I:

- Restarted the laptop.
- Entered the BIOS by pressing **F2**.
- Enabled the **F12 Boot Menu** option.
- Saved the changes using **F10**.
- Restarted the laptop.

After enabling the option, pressing **F12** displayed the Boot Menu.

---

### 4. Booted from the USB

From the Boot Menu, I saw:

- Windows Boot Manager
- USB HDD: SanDisk

I selected **USB HDD: SanDisk**.

Windows Setup loaded and displayed two options:

- Install Windows 11
- Repair your PC

Since I wanted a fresh installation, I selected **Install Windows 11**.

---

### 5. Selected the Installation Drive

Windows Setup displayed all available disks and partitions.

I carefully identified the correct drives before continuing.

The installer showed:

| Disk / Partition | Total Size | Free Space | Type |
| ---------------- | ---------: | ---------: | ---- |
| **Disk 0 Partition 1** | 100 MB | 100 MB | System |
| **Disk 0 Partition 2** | 16 MB | 16 MB | MSR (Reserved) |
| **Disk 0 Partition 3: Acer** | 475.8 GB | 192.1 GB | Primary |
| **Disk 0 Partition 4** | 1.0 GB | 1.0 GB | Recovery |
| **Disk 1 Partition 1: ESD-USB** | 28.6 GB | 22.3 GB | Primary |

I confirmed that:

- **Disk 0** was my laptop's internal SSD.
- **Disk 1: ESD-USB** was the Windows installation USB.

Since I wanted a completely fresh installation, I deleted every partition on **Disk 0**.

After deleting them, the installer showed:

| Disk / Partition | Total Size | Free Space | Type |
| ---------------- | ---------: | ---------: | ---- |
| **Disk 0 Unallocated Space** | ~476.9 GB | ~476.9 GB | Unallocated |
| **Disk 1 Partition 1: ESD-USB** | 28.6 GB | 22.3 GB | Primary |

Before clicking **Next**, I checked the selected drive one more time to make sure I was installing Windows on the SSD and not on the USB drive.

I selected **Disk 0 Unallocated Space**, clicked **Next**, and Windows automatically created the required partitions before starting the installation.

---

### 6. Installed Windows 11

Windows Setup automatically:

- Copied Windows files.
- Installed Windows features.
- Installed updates.
- Restarted the laptop several times.

I didn't need to do anything during this part except wait for the installation to finish.

---

### 7. Completed the Windows Setup

After Windows finished installing, the Out-of-Box Experience (OOBE) started.

During setup, Windows required an internet connection.

However:

- Only Ethernet was available.
- Wi-Fi wasn't detected.
- There was no option to continue without an internet connection.

To continue the setup offline, I:

- Pressed **Shift + F10**.
- Opened Command Prompt.
- Ran:

```cmd
OOBE\BYPASSNRO
```

The laptop restarted.

After restarting, Windows displayed the **"I don't have Internet"** option.

I continued the installation offline, created my local Windows account, completed the remaining setup screens, and reached the Windows desktop.

---

### 8. Completed the Post-Installation Setup

After confirming that Windows started successfully, I removed the USB drive.

I then prepared the laptop for normal use by:

- Running Windows Update.
- Installing the required drivers.
- Checking Device Manager for missing drivers.
- Installing Acer software and other required applications.

---

## Resolution

The clean Windows installation using a bootable USB completed successfully after the built-in Windows recovery methods failed.

After installing Windows, I updated the system, installed the required drivers, and verified that the laptop was ready for normal use.

---
