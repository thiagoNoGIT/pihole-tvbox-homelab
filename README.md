# Pi-hole on H3 TV Box (Armbian)

Repurposing a low-cost TV box into a network-wide DNS sinkhole using Pi-hole.

## Overview

This project documents the process of converting an unused H3-based TV box into a functional DNS server using Armbian and Pi-hole.

The goal was to create a low-power, always-on solution to filter ads and trackers at the network level.

## Hardware

- Generic H3 TV Box
- microSD card (8GB / 64GB tested)
- Ethernet connection

- ## Software Stack

- Armbian (Debian-based)
- Pi-hole
- DNSMasq (embedded)

- ## Features

- Network-wide ad and tracker blocking
- DNS-level filtering
- Low power consumption
- Always-on service

- ## Setup

### Hardware
![Hardware](images/hardware.jpg)

### Pi-hole Dashboard
![Dashboard](images/dashboard.png)

## Results

- Stable DNS resolution through Pi-hole
- Successful blocking of advertising domains (e.g. doubleclick.net)
- Improved browsing experience across all devices
