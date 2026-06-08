# Armbian Versions and Hardware Compatibility Guide

This document explains how to choose the correct Armbian version based on hardware, focusing on CPU architecture, board support, and system stability.

---

## Why this matters

Unlike standard PCs, ARM-based devices (such as TV boxes) do not have universal OS support.

Each device depends on:

* Specific SoC (System on Chip)
* Board configuration
* Kernel compatibility

Choosing the wrong image can result in:

* Boot failure
* Missing drivers (Ethernet, HDMI, USB)
* System instability

---

## Understanding Your Hardware

Before selecting an Armbian image, identify:

### 1. SoC (CPU)

Common examples:

* Allwinner H3
* Allwinner H5
* Amlogic S905 / S905X
* Rockchip RK3318 / RK3328

In this project:

```text
SoC: Allwinner H3
```

---

### 2. Board / Device Type

TV boxes are often **generic and not officially supported**.

This means:

* No guaranteed compatibility
* Requires community-supported images
* May need manual adjustments

---

## Armbian Image Types

Armbian provides different builds depending on stability and use case:

---

### Stable (Recommended)

* Fully tested
* Lower risk of bugs
* Best for production environments

Use this when:

* You want reliability
* Your hardware is already working

---

### Current

* Newer kernel
* More hardware support
* May introduce instability

Use this when:

* Stable version lacks support for your device

---

### Edge

* Latest kernel (experimental)
* Highest risk of bugs

Use this when:

* You need cutting-edge support
* You are troubleshooting hardware compatibility

---

## Kernel Considerations

Kernel version directly affects:

* Hardware drivers
* Network stability
* Performance

Older kernels:

* More stable
* Less hardware support

Newer kernels:

* Better compatibility
* Potential instability

---

## How to Choose the Correct Image

### Step 1 — Identify SoC

Check device specifications or PCB markings.

---

### Step 2 — Search Armbian Support

Look for your SoC or similar boards in:

* Official Armbian downloads
* Community forums

---

### Step 3 — Start with Stable

Always try:

```text
Armbian Stable (Debian-based)
```

If it fails:

* Move to "Current"
* Then "Edge" as last resort

---

### Step 4 — Test Basic Functionality

After boot:

* Network (Ethernet)
* Storage (SD card)
* CPU stability

If any fails:

* Try a different kernel version

---

## Version Used in This Project

```text
SoC: Allwinner H3  
OS: Armbian (Debian-based)  
Build: Stable  
Installation: SD card boot  
```

---

## Practical Advice

* Always keep a backup SD card with a working image
* Avoid upgrading kernel blindly
* Lock working kernel versions in production systems
* Prefer Ethernet over Wi-Fi for stability

---

## Common Pitfalls

* Using an image for a different SoC
* Assuming all TV boxes are the same
* Updating kernel without validation
* Ignoring community compatibility notes

---

## Final Notes

Working with ARM devices requires experimentation.

There is no universal solution — only compatible combinations of:

* Hardware
* Kernel
* OS build

This project demonstrates a working combination, but replication may require adjustments depending on the device.

---
