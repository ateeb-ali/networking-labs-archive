# Floating Static Route Lab

This lab demonstrates how to configure **floating static routes** in Cisco routers using Packet Tracer. Floating routes act as **backup routes** that only activate if the primary path becomes unavailable.

---

## 🎯 Objectives

- Configure primary and backup static routes
- Use administrative distance to "float" backup routes
- Test failover behavior by simulating link failures
- Ensure end-to-end connectivity between both LANs

---

## 🛠️ Key Setup

- **PC0 (192.168.1.2)** ↔ **PC1 (192.168.2.2)** across 4 routers  
- Primary path: Router3 → Router0 → Router1 → Router2  
- Backup path: Router3 → Router2 via Serial links (40.0.0.0/30)  
- Floating route configured with higher administrative distance

---

## 🔧 Configuration Highlights

- `ip route` commands used to define both primary and backup routes
- Primary routes have default admin distance (`1`)
- Backup (floating) route uses higher admin distance (e.g., `5`, `10`, or more)
- Link failures can be simulated by shutting down interfaces to trigger failover

---

## 📁 Files Included

- `floating-routing.pkt` — Packet Tracer file with full configured lab
- `README.md` — This file
- `Topology.png` — The Topology's screenshot from the pkt file
---

## ✅ Verification Tips

- Use `show ip route` to confirm which route is active
- Use `ping` between PCs to verify connectivity
- Shutdown interfaces to test failover and floating route behavior

---

## 📌 Notes

- Administrative distance is key: backup routes must have higher values
- Floating routes are useful for redundancy in real-world networks


