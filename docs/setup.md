# Setup Guide

This document describes the full deployment process of Pi-hole on an H3-based TV box running Armbian.

---

## 1. Flash Armbian

* Download a compatible Armbian image for H3 devices
* Flash the image to a microSD card using tools like Balena Etcher
* Insert the SD card into the TV box and power it on

---

## 2. Initial Access

* Connect the device to the network via Ethernet
* Identify its IP address from the router
* Access via SSH:

```bash
ssh root@<device-ip>
```

* Complete initial setup (password, locale, etc.)

---

## 3. System Preparation

Update package lists:

```bash
apt update && apt upgrade -y
```

If repository issues occur, manually fix:

```bash
nano /etc/apt/sources.list
```

Then re-run:

```bash
apt update
```

---

## 4. Install Pi-hole

Run the official installer:

```bash
curl -sSL https://install.pi-hole.net | bash
```

During installation:

* Set a **static IP** (e.g. 192.168.100.37)
* Choose an upstream DNS provider
* Enable web interface
* Enable query logging (optional based on privacy preference)

---

## 5. Network Configuration

Access your router settings and:

* Set Pi-hole IP as **primary DNS**
* If required, duplicate the same IP as secondary DNS
* Disable external DNS bypass if possible

---

## 6. Validation

Test DNS resolution:

```bash
nslookup google.com <pihole-ip>
```

Test ad blocking:

```bash
nslookup doubleclick.net <pihole-ip>
```

Expected result:

```bash
0.0.0.0
```

---

## 7. Access Web Interface

Open in browser:

```bash
http://<pihole-ip>/admin
```

Monitor queries, blocked domains, and system performance.

---

## Notes

* System stability depends on SD card quality
* Ethernet is strongly recommended over Wi-Fi
* Keep the system updated regularly

---
