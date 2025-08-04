# SNMP Lab - Packet Tracer

This repository contains a basic Cisco Packet Tracer lab demonstrating SNMP (Simple Network Management Protocol) configuration in a small-scale network. The topology focuses on monitoring and managing devices using SNMP protocols.

### Devices Used
- **2 Cisco 2911 Routers**
  - R1: 192.168.10.1
  - R2: 192.168.10.2 / 192.168.20.1
- **1 Layer 2 Switch**
  - Switch0: 2960-24TT
- **1 Server**
  - Server0: 192.168.20.2 (Default Gateway: 192.168.20.1)

### Interfaces & Connections
- **R1 (Serial0/0/0)** ↔ **R2 (Gig0/0)** — *SNMP communication line*
- **R2 (Gig0/0)** ↔ **Switch0 (Fa0/2)**
- **Switch0 (Fa0/1)** ↔ **Server0 (Fa0)**

## 🧪 Objective

To simulate a basic SNMP lab setup where:
- R1 and R2 can be monitored through SNMP.
- Server0 acts as an SNMP manager, polling information from the routers.
- The network supports basic SNMP operations like GET and TRAP (if configured).

## 🔧 What’s Included

- `SNMP.pkt` — Packet Tracer file with the configured topology.
- `README.md` — This file.
- `topology.png` — Screenshot of the network topology for quick reference.

## 🧠 Learning Goals

- Understand SNMP architecture (Manager-Agent model).
- Practice device monitoring in Packet Tracer.
- Familiarize with SNMP community strings and basic commands.

---

