# Architecture

[Devices] → [Router] → [Pi-hole DNS] → [Upstream DNS]

All DNS queries are routed through Pi-hole before reaching external resolvers.
