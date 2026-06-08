# Architecture

This document explains how traffic flows through the network with Pi-hole acting as the DNS sinkhole.

---

## High-Level Overview

```text
Client Devices → Router → Pi-hole → Upstream DNS → Internet
```

---

## Components

### Client Devices

All devices connected to the network:

* PCs
* Smartphones
* Smart TVs
* IoT devices

---

### Router

Responsible for:

* Assigning IP addresses (DHCP)
* Forwarding DNS requests to Pi-hole
* Acting as network gateway

---

### Pi-hole (DNS Sinkhole)

Core component of the architecture.

Responsibilities:

* Receive DNS queries from all clients
* Compare domains against blocklists
* Block or resolve queries accordingly
* Forward allowed queries to upstream DNS

---

### Upstream DNS

External DNS providers such as:

* Cloudflare (1.1.1.1)
* Google (8.8.8.8)

Used only when a domain is not blocked.

---

## DNS Flow

1. Client requests domain resolution
2. Request is sent to router
3. Router forwards to Pi-hole
4. Pi-hole checks blocklists:

   * If blocked → returns `0.0.0.0`
   * If allowed → forwards to upstream DNS
5. Response is returned to client

---

## Security Considerations

* DNS filtering reduces exposure to malicious domains
* Centralized control improves visibility
* Can be extended with firewall rules to prevent bypass

---

## Future Enhancements

* Enable Pi-hole as DHCP server (removes router dependency)
* Enforce DNS via firewall rules
* Integrate VPN for remote secure DNS usage
* Add logging/monitoring stack

---

## Design Philosophy

This setup prioritizes:

* Simplicity
* Low resource usage
* Full control over DNS traffic
* Reusability of low-cost hardware

It is intentionally minimal, but extensible.
