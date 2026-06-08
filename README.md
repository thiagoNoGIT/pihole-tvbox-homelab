# Pi-hole on H3 TV Box (Armbian)

Repurposing a low-cost H3-based TV box into a production-ready DNS server using Armbian and Pi-hole.

---

## Overview

This project documents the process of converting an unused H3 TV box into a fully functional DNS server for a home network.

Instead of relying on traditional hardware or cloud-based filtering, this setup uses a lightweight ARM device to provide network-wide ad and tracker blocking at the DNS level.

The goal was simple: build a stable, low-power, always-on solution that improves privacy and control over network traffic.

---

## Hardware

* Generic H3-based TV Box
* microSD card (tested with 8GB and 64GB)
* Ethernet connection

---

## Software Stack

* Armbian (Debian-based Linux)
* Pi-hole
* DNSMasq (embedded in Pi-hole)

---

## Features

* Network-wide ad and tracker blocking
* DNS-level filtering for all connected devices
* Low power consumption (always-on capable)
* Centralized DNS control

---

## Architecture

```
[ Client Devices ]
        ↓
      Router
        ↓
   Pi-hole (DNS)
        ↓
   Upstream DNS
```

All DNS queries are routed through the Pi-hole instance before reaching external resolvers.

---

## Setup

### Hardware

![Hardware](images/hardware.jpg)

### Pi-hole Dashboard

![Dashboard](images/dashboard.png)

---

## Deployment Summary

1. Flashed Armbian to SD card
2. Booted and accessed system via SSH
3. Fixed broken repositories and dependencies
4. Installed Pi-hole
5. Configured router to use Pi-hole as primary DNS
6. Validated DNS filtering across the network

---

## Results

* Successful DNS resolution through Pi-hole
* Blocking of known ad domains (e.g. `doubleclick.net`)
* Improved browsing experience across devices
* Stable operation under continuous use

---

## Challenges

This was not a plug-and-play setup. Some issues encountered:

* Broken `sources.list` and package repositories
* Missing or incompatible packages
* Kernel instability during initial setup
* Manual network configuration required

All issues were resolved through manual troubleshooting and system adjustments.

---

## Future Improvements

* Enforce DNS usage (prevent clients from bypassing Pi-hole)
* Configure Pi-hole as DHCP server
* Add VPN for secure remote access
* Implement monitoring and logging improvements

---

## Project Status

* Running in production (home network)
* Stable
* Low resource usage

---

## Why this project matters

This project demonstrates practical skills in:

* Linux system administration
* Network configuration (DNS, DHCP concepts)
* Troubleshooting real-world issues
* Infrastructure thinking using low-cost hardware

It’s a simple setup, but it reflects how much value can be extracted from limited resources when you understand the stack.

---

## License

This project is open for study and adaptation.
