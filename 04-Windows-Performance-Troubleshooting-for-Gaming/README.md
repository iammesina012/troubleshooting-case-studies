# Windows Performance Troubleshooting for Gaming

## Summary

> **Situation:** My games experienced random FPS drops even though my laptop had good gaming specifications.
>
> **Goal:** Identify the cause of the FPS drops and improve gaming performance through software troubleshooting.
>
> **Result:** After testing different software settings and monitoring system performance, I improved stability in several games by limiting the frame rate to match my laptop's 100 Hz display. Although the issue was reduced, it was not completely resolved, suggesting that further hardware maintenance may be needed.

---

## Overview

While playing games on my Acer Aspire 7, I noticed that the FPS would suddenly drop for a few seconds before returning to normal. Since my laptop has a Ryzen 7 processor, NVIDIA GeForce RTX 3050 Ti and a 16GB RAM, I expected more consistent performance.

This scenario documents the steps I took to investigate possible software causes before considering that the remaining issue might be hardware related again.

---

## Environment

**Device:** Acer Aspire 7 A715-42G

**Operating System:** Windows 11

**CPU:** AMD Ryzen 7

**GPU:** NVIDIA GeForce RTX 3050 Ti Laptop GPU + AMD Radeon Integrated Graphics

**Memory:** 16 GB RAM

**Storage:** SSD

**Games Tested:**

- Valorant
- Minecraft
- Genshin Impact
- Wuthering Waves
- League of Legends

---

## Symptoms

While gaming, the FPS would run normally most of the time, but every so often it would suddenly drop for around **3–5 seconds** before returning to normal.

This happened in multiple games, making me suspect that the problem was not limited to a single game.

---

## Investigation

### 1. Monitored System Temperatures

Since the FPS drops usually happened after playing for a while, I first suspected that the laptop might be overheating.

I monitored the CPU and GPU temperatures using **HWMonitor** while playing games to check whether thermal throttling could be causing the performance drops.

---

### 2. Monitored System Usage

While gaming, I also monitored:

- CPU usage
- GPU usage
- RAM usage

using **Task Manager**, **Xbox Game Bar**, and the **NVIDIA Performance Overlay**.

The goal was to check whether one of the system components suddenly reached unusually high usage whenever the FPS dropped.

---

### 3. Updated Graphics Drivers

To rule out driver-related problems, I updated both graphics drivers.

I:

- Installed the latest AMD graphics driver using **AMD Software: Adrenalin Edition**.
- Installed the latest NVIDIA graphics driver using the **NVIDIA App**.

---

### 4. Tested Different Graphics Settings

I experimented with different in-game graphics settings, including lowering graphics quality, changing FPS limits, and testing V-Sync.

The purpose was to determine whether reducing the GPU workload would improve performance.

---

### 5. Adjusted NVIDIA Settings

I also tested different performance settings in the **NVIDIA Control Panel** and **NVIDIA App**.

I tried multiple recommended settings found during my research, but the random FPS drops continued.

---

### 6. Changed Windows Power Settings

I changed the Windows power plan to **Ultimate Performance** to prevent the laptop from switching to power-saving behavior while gaming.

Despite the change, the FPS drops still occurred.

---

### 7. Considered Cooling and Hardware

After testing multiple software solutions, I considered whether the issue might be related to the laptop's cooling system.

Possible causes included:

- Dust buildup inside the laptop
- Aging thermal paste
- Cooling performance under heavy gaming load

At the time, I was unable to continue this part of the troubleshooting because it required opening the laptop for further maintenance.

---

### 8. Tested FPS Limits

While testing different games, I noticed that **Valorant** became much more stable after limiting the frame rate to **100 FPS**, which matched my laptop's **100 Hz** display.

After seeing the improvement, I also applied the same FPS limit to:

- League of Legends
- Minecraft (without shaders)

These games also showed more stable performance after limiting the frame rate.

---

## Resolution

I tried many software fixes to improve the FPS drops, including updating drivers, changing NVIDIA settings, using the Ultimate Performance power plan, and testing different game settings.

These changes helped a little, but they didn't completely fix the problem. The biggest improvement I found was limiting the FPS to **100**, which matches my laptop's **100 Hz** display. This made Valorant, League of Legends, and Minecraft feel much smoother.

Although the FPS drops still happened in some games, I was able to rule out many common software causes. At this point, I believed the next step would be hardware maintenance, such as cleaning the cooling system or replacing the thermal paste, so I ended the software troubleshooting there.

---

## Skills Demonstrated

- Gaming Performance Optimization
- Performance Monitoring
- HWMonitor
- Graphics Driver Installation & Updates
- NVIDIA Control Panel
- Windows Power Plans

---

## Lessons Learned

- Monitoring temperatures and system usage helps identify possible performance bottlenecks.
- Updating graphics drivers is an important troubleshooting step, but it does not always resolve performance issues.
- Testing one change at a time makes it easier to understand which settings improve performance.
- Matching the FPS limit to the monitor's refresh rate can improve frame consistency in some games.
- If software troubleshooting does not fully resolve the issue, hardware maintenance may be the next area to investigate.
