# Enterprise Wireless LAN (ESS) Lab

This lab demonstrates an Extended Service Set (ESS) wireless network setup using Cisco Packet Tracer. The topology simulates a centralized wireless network environment with multiple Lightweight Access Points (LAPs) managed by a Wireless LAN Controller (WLC).

---

## 🧠 Objective

- Understand the architecture of enterprise wireless LANs using a controller-based model.
- Configure a Wireless LAN Controller (WLC) to manage multiple Lightweight Access Points.
- Ensure roaming between LAPs with seamless connectivity for wireless clients (laptops and smartphone).
- Simulate connectivity to backend services (DHCP, DNS, etc.) via a server.

---

## 🔧 Components

- **Wireless LAN Controller (WLC-3504)**
- **14 Lightweight Access Points (LAP-PT)**
- **2 Laptops + 1 Smartphone** as wireless clients
- **2 Switches** for wired distribution
- **1 Server** for IP and service provisioning

---

## 🛠️ Key Configurations

- LAPs are connected to switches and automatically register with the WLC.
- The server provides DHCP services to wireless clients.
- Wireless clients connect to the same SSID and can roam across different access points.
- Network uses VLANs or flat IP addressing (depending on lab settings).

---

## ✅ Outcomes

- All wireless devices receive IP addresses dynamically.
- LAPs register with WLC and broadcast the configured SSID.
- Wireless clients can connect to the network and communicate with the server.
- Mobility between APs works without connection drops.

---

## 📁 Files Included

- `ESS.pkt` — Packet Tracer file with complete topology and configurations
- `Topology.png` — The topology screenshot from the pkt file.
- `README.md` — This file

---

## 📌 Notes

- Ensure WLC DHCP settings and interfaces are properly configured.
- Verify LAP registration via WLC GUI or CLI.
- Some devices may require manual association with the SSID.


