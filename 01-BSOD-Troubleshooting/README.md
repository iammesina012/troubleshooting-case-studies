# Windows 11 BSOD Troubleshooting

## Summary

> **Issue:** Recurring Blue Screen of Death (BSOD)
>
> **Root Cause:** Poor RAM contact / improperly seated RAM
>
> **Resolution:** Cleaned and reseated both RAM modules after software troubleshooting did not resolve the issue.

## Overview

This scenario documents how I investigated recurring Blue Screen of Death (BSOD) crashes on my personal Acer Aspire 7 laptop. The system displayed different stop codes during normal use, making the issue difficult to identify. I investigated both software and hardware by checking Windows logs, using diagnostic tools, troubleshooting drivers, reinstalling Windows, and finally inspecting the laptop's RAM, which resolved the issue.

---

## Environment

- **Device:** Acer Aspire 7 A715-42G
- **Operating System:** Windows 11
- **Processor:** AMD Ryzen 7
- **Graphics:** NVIDIA GeForce RTX 3050 Ti Laptop GPU + AMD Radeon Integrated Graphics
- **Memory:** 16 GB RAM (2 × 8 GB)
- **Storage:** SSD
- **Device Type:** Personal Laptop
  
---

## Symptoms

- Recurring BSOD crashes during normal laptop use.
- Different stop codes appeared across separate crashes.
- Some crashes happened while downloading or verifying files.
- The system occasionally displayed **"No bootable device."**
- The issue continued even after several software troubleshooting attempts.

---

## Troubleshooting Process

### 1. Recorded the BSOD stop codes

I recorded the stop codes whenever they appeared to help identify possible causes.

Some of the stop codes included:

- CRITICAL_PROCESS_DIED
- UNEXPECTED_STORE_EXCEPTION
- KMODE_EXCEPTION_NOT_HANDLED
- 0xC000021A

Because the stop codes were different, I knew I needed to investigate several possible causes instead of focusing on just one.

---

### 2. Reviewed Windows logs

To understand why the laptop was crashing, I reviewed the system logs using **Event Viewer** and **Reliability Monitor**.

In **Event Viewer**, I found several important events, including:

- **Kernel-Power (Event ID 41)** – showed that Windows shut down unexpectedly after each BSOD. This confirmed that the system was crashing but did not identify the exact cause.
- **volmgr (Event ID 161)** – appeared after some crashes, indicating that Windows could not create a memory dump file. This meant there was less diagnostic information available to help identify the cause of the BSOD.
- **No WHEA-Logger errors** – I checked for WHEA (Windows Hardware Error Architecture) events but did not find any. This suggested that Windows had not detected a hardware error from components such as the CPU, memory, or motherboard.

I also reviewed **Reliability Monitor**, which showed a history of repeated Windows crashes, unexpected shutdowns, and application failures. This helped me confirm that the problem was recurring over time, although it still did not point to one specific cause.

---

### 3. Repaired the Windows image

Next, I ran:

`DISM /Online /Cleanup-Image /RestoreHealth`

The command completed successfully and repaired the Windows component store.

---

### 4. Checked Windows system files

To check if Windows had corrupted system files, I ran:

`sfc /scannow`

**Result:**

Windows Resource Protection did not find any integrity violations.

Since SFC did not find any problems, I continued with other troubleshooting steps.

---

### 5. Checked the SSD

To make sure the SSD was not causing the crashes, I investigated the drive's health.

I first tried running:

`chkdsk C: /f /r`

However, the initial attempt returned **Access Denied**, so I continued using other diagnostic tools.

Next, I tried using the `wmic` command to check the SSD status, but it was not available on my Windows installation.

Instead, I used PowerShell and ran:

`Get-PhysicalDisk | Select-Object DeviceId, FriendlyName, HealthStatus, OperationalStatus`

**Result:**

The SSD reported:

- **HealthStatus:** Healthy
- **OperationalStatus:** OK

To verify the result further, I also checked the SSD using **CrystalDiskInfo**, which reported the drive health as **Good** (approximately 90%).

Based on these results, the SSD appeared to be working properly.

---

### 6. Tested in Safe Mode

While troubleshooting the BSODs, I noticed that the crashes sometimes happened after using certain programs or features, such as:

- Updating the NVIDIA graphics driver.
- Turning Bluetooth on or off.
- Opening Acer Care Center.

Because of this, I started thinking that one of the background services or startup programs might be causing the problem.

To test this, I started Windows in **Safe Mode** and used **System Configuration (msconfig)** to:

- Hide all Microsoft services.
- Disable non-Microsoft services.
- Check third-party services, including Acer and NVIDIA services.

I also reviewed the startup programs before testing the laptop again.

After making these changes, the laptop worked normally for about a day. However, the BSODs returned, so I ruled out third-party services as the main cause and continued with other troubleshooting steps.

---

### 7. Used Windows Recovery Environment (WinRE)

Since the BSODs continued after the previous troubleshooting steps, I accessed the Windows Recovery Environment (WinRE) to try Windows recovery options before reinstalling Windows.

**Startup Repair**

I first tried **Startup Repair** to see if Windows could automatically fix the startup or system issues that might have been causing the BSODs.

**Result:**

Startup Repair did not resolve the issue, and the BSODs continued.

---

**Reset this PC (Cloud Download & Local Reinstall)**

Next, I tried using **Reset this PC** with both the **Cloud Download** and **Local Reinstall** options.

However, Windows displayed an error message and would not allow either reset option to continue.

Because both reset methods failed, I decided to perform a clean installation of Windows using a bootable USB instead.

---

### 8. Reinstalled Windows

After trying several software troubleshooting methods, I performed a clean installation of Windows 11 using Microsoft's Media Creation Tool.

After reinstalling Windows, I:

- Installed Windows updates.
- Installed the required drivers.
- Verified devices in Device Manager.
- Reinstalled my applications.
- Tested the laptop again.

However, the BSODs still returned, so I started investigating the hardware instead.

---

### 9. Inspected the RAM

Since the software troubleshooting did not solve the issue, I inspected the laptop's RAM.

I:

- Removed both RAM sticks.
- Cleaned the RAM contacts.
- Reseated the RAM.
- Swapped the positions of the RAM sticks.

After putting the RAM back, I continued using the laptop and the BSODs no longer occurred.

This confirmed that the issue was caused by poor RAM contact or seating rather than Windows itself.

---

## Resolution

Cleaning, reseating, and swapping the RAM modules resolved the recurring BSODs. After this, the laptop remained stable during normal use, downloading files, and gaming.

---
