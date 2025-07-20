# OSPF Multi-Area with BGP Redistribution Lab

This lab demonstrates a multi-area OSPF network integrated with external BGP using Cisco Packet Tracer. The topology is designed to simulate a scalable enterprise network using backbone (Area 0), internal areas (Area 1, 2), and route redistribution to an external autonomous system.

---

## 🧠 Objective

- Configure and verify OSPFv2 across multiple areas (0, 1, 2)
- Understand the roles of ABR (Area Border Router) and ASBR (Autonomous System Boundary Router)
- Implement BGP at the edge and redistribute BGP routes into OSPF
- Visualize LSA propagation, DR/BDR election, and neighbor adjacency
- Use hierarchical design to segment the network and ensure scalability

---

## 🔧 Components

- **Cisco 2911 Routers** (13+ routers)
- **Multiple OSPF Areas**  
  - Area 0 (Backbone)  
  - Area 1  
  - Area 2  
- **BGP Autonomous System** for external connectivity
- **Switches and PCs (optional)** for end-device simulation
- **Serial & Gigabit links** to represent WAN and LAN segments
- Color-coded topology for easy area identification

---

## 🛠️ Key Configurations

- OSPF routers assigned to respective areas using `network` statements
- ABRs connect non-backbone areas to Area 0
- ASBR redistributes BGP into OSPF using `redistribute bgp`
- DR/BDR election observed on broadcast segments
- Loopback or physical interfaces used as router IDs
- Manual router ID configuration for consistency and clarity

---

## 📂 Files Included

- `OSPF.pkt` – Packet Tracer file with complete topology and configurations (OSPF + BGP)
- `README.md` – This file
- Topology screenshots:
  - `topology-full.png`
  - `topology-left.png`
  - `topology-right.png`

---

## ✅ Outcomes

- OSPF adjacencies form within and across areas
- ABRs enable inter-area route communication
- BGP peer established and redistributed into the OSPF domain
- DR/BDR election verified on multi-access links
- All routers share a consistent routing table using LSDB synchronization

---

## 💻 Verification Commands

```bash
show ip ospf neighbor
show ip ospf interface brief
show ip ospf database
show ip route ospf
debug ip ospf adj
debug ip ospf events
```

---

## 📌 Notes

- Use loopback interfaces for router IDs to avoid conflicts if physical links go down  
- OSPF area 0 is mandatory for multi-area networks — all other areas must connect to it via ABRs  
- Make sure BGP and OSPF processes use consistent metric handling during redistribution  
- If show ip ospf neighbor shows empty output, check IP mismatches or interface passive settings  
- Packet Tracer may not support full BGP functionality — basic redistribution is simulated
