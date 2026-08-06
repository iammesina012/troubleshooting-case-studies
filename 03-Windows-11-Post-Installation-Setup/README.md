# Windows 11 Post-Installation Setup

## Summary

> **Situation:** After completing a clean Windows 11 installation, the laptop still needed drivers, updates, and essential software before it was ready for everyday use.
>
> **Goal:** Restore full hardware functionality, install the required software, and verify that the system was ready for normal use.
>
> **Result:** Windows Update installed most of the required drivers, the remaining graphics driver was installed manually, and the laptop was successfully prepared for daily use.

---

## Overview

After installing Windows 11, the laptop was missing several drivers and was not yet ready for normal use. This scenario documents how I restored internet connectivity, installed Windows updates and drivers, verified that all hardware was working correctly, and installed the essential software needed for daily use.

---

## Environment

**Device:** Acer Aspire 7 A715-42G

**Operating System:** Windows 11

**Storage:** SSD

---

## Setup Process

### 1. Connected the Laptop to the Internet

After reaching the Windows desktop, I noticed that the Wi-Fi option was unavailable because the wireless driver had not yet been installed.

To temporarily connect the laptop to the internet, I used **USB tethering** from my phone so Windows could access Windows Update.

---

### 2. Installed Windows Updates

After connecting to the internet, I opened:

**Settings → Windows Update → Check for updates**

Windows downloaded and installed the latest updates, including several hardware drivers.

Once the Wi-Fi driver was installed, the Wi-Fi option appeared in Windows.

I then disconnected USB tethering, connected to my home Wi-Fi network, and continued installing the remaining Windows updates.

I repeated the update process until there were no more available updates.

---

### 3. Verified Installed Drivers

After Windows Update finished, I opened **Device Manager** to verify that the required drivers had been installed successfully.

I checked for any devices with a yellow exclamation mark that might indicate a missing or failed driver.

After updating Windows, Device Manager showed no missing devices or driver warnings.

---

### 4. Installed Graphics Drivers

Although Windows Update installed most of the required drivers, I still manually installed the latest graphics drivers for both GPUs.

For the AMD integrated graphics, I downloaded and installed **AMD Software: Adrenalin Edition** from AMD's official website, and used it to install the latest AMD graphics driver.

For the NVIDIA dedicated graphics, I downloaded and installed the **NVIDIA App** from NVIDIA's official website, then used it to install the latest graphics driver.

This ensured both the integrated and dedicated graphics drivers were fully updated after the Windows installation.

---

### 5. Installed Acer Care Center

After installing the required drivers, I installed **Acer Care Center**.

This restored Acer's built-in management software, allowing me to monitor system information, run hardware checks, manage recovery features, and receive Acer driver and software updates when available.

---

### 6. Installed Essential Applications

Once the system was fully updated, I installed the applications I use every day.

The first applications I installed were:

- Brave Browser
- Microsoft Office Home and Student 2019

After confirming that Windows was working properly, I installed my other applications and games, including:

- Steam
- Discord
- Spotify
- My games

---

### 7. Tested the System

After completing the setup, I used the laptop normally to make sure everything was working correctly.

This included:

- Browsing the internet.
- Installing applications.
- Playing games.
- Using the laptop for everyday tasks.

Although the installation was successful, the BSOD returned after about a day of normal use.

This confirmed that the Windows installation itself was not the cause of the problem. I continued troubleshooting and eventually found that cleaning and reseating the RAM resolved the issue.

---

## Resolution

The Windows installation and post-installation setup were completed successfully.

The laptop was fully updated, the required drivers were installed, and Device Manager showed no missing drivers. Wi-Fi connectivity was restored, and the laptop was ready for normal use.

Although the BSOD returned after about a day of normal use, this confirmed that the Windows installation itself was not the cause of the problem. I continued troubleshooting, which eventually led me to identify the RAM as the actual cause of the crashes.

---

## Skills Demonstrated

- Driver Installation using Windows Update
- Graphics Driver Installation (AMD Software: Adrenalin Edition & NVIDIA App)
- Windows Driver Verification (Device Manager)
- Windows 11 Post-Installation Setup

---

## Lessons Learned

- Windows Update can install most of the drivers needed after a clean Windows installation.
- USB tethering is a useful temporary solution when the Wi-Fi driver is not yet available.
- Device Manager is a simple way to verify that drivers have been installed successfully.
- Some drivers, such as AMD and NVIDIA graphics drivers, still need to be installed manually using the manufacturer's official software.
- Successfully reinstalling and setting up Windows does not always resolve system problems. If the issue continues, further troubleshooting is needed to identify the real cause.
