# Troubleshooting

This section documents real issues encountered during deployment and how they were resolved.

---

## Broken Package Repositories

### Issue

`apt update` failed due to invalid or outdated repositories.

### Solution

Manually edit:

```bash
nano /etc/apt/sources.list
```

Replace with valid Debian/Armbian mirrors and run:

```bash
apt update
```

---

## Missing Packages During Installation

### Issue

Some packages required by Pi-hole were not found.

### Cause

Outdated package index or incompatible repo configuration.

### Solution

```bash
apt update --fix-missing
apt upgrade
```

---

## Kernel Instability

### Issue

System instability or unexpected behavior after boot.

### Cause

Incompatible kernel version for H3 hardware.

### Solution

* Lock working kernel version
* Avoid unstable updates
* Use Armbian stable builds only

---

## Network Not Resolving

### Issue

DNS queries failing or not being routed through Pi-hole.

### Solution

* Verify router DNS settings
* Confirm Pi-hole IP is correct
* Test with:

```bash
nslookup google.com <pihole-ip>
```

---

## DNS Bypass

### Issue

Some devices bypass Pi-hole using external DNS (e.g. 8.8.8.8).

### Solution

* Block outbound DNS (port 53) on router except Pi-hole
* Enforce DNS redirection rules (if router supports it)

---

## Pi-hole Not Blocking Ads

### Issue

Domains resolving normally instead of being blocked.

### Solution

* Update gravity list:

```bash
pihole -g
```

* Check blocklists
* Verify query logging for domain activity

---

## Persistence Concerns

### Question

Will configurations be lost after reboot or power outage?

### Answer

No. As long as the SD card is intact, all configurations persist. Pi-hole and system services will start automatically on boot.

---

## Notes

This project required manual troubleshooting across multiple layers:

* OS (Armbian)
* Package management
* Network configuration
* DNS behavior

Understanding these layers was essential for achieving a stable deployment.
