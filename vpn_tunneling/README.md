# 🛡️ Cisco Packet Tracer – Site-to-Site VPN Lab

This lab simulates a **Site-to-Site VPN Tunnel** between two remote office networks using Cisco IOS routers in Cisco Packet Tracer. The goal is to secure communication between two LANs over an untrusted public network (Internet simulation).

---

## 🎯 Objectives

- Establish an **IPSec VPN tunnel** between **Router0** and **Router3**.
- Allow PCs in **10.0.0.0/24** to securely communicate with **20.0.0.0/24**.
- Simulate public WAN using **Router1** and **Router2** as intermediary routers.

---

## 🔧 Configuration Steps

### ✅ Static Routing

Set up routing so all routers can reach both LANs.

**Router0:**
```bash
ip route 20.0.0.0 255.255.255.0 30.0.0.2
```

**Router1:**
```bash
ip route 10.0.0.0 255.255.255.0 30.0.0.1
ip route 20.0.0.0 255.255.255.0 40.0.0.2
```

**Router2:**
```bash
ip route 10.0.0.0 255.255.255.0 40.0.0.1
ip route 20.0.0.0 255.255.255.0 50.0.0.2
```

**Router3:**
```bash
ip route 10.0.0.0 255.255.255.0 50.0.0.1
```

### 🛡️ Configure VPN on Router0 and Router3

**Router0:**
```bash
crypto isakmp policy 10
 encr aes
 hash sha
 authentication pre-share
 group 2
 lifetime 86400

crypto isakmp key cisco address 50.0.0.2

crypto ipsec transform-set TRANS esp-aes esp-sha-hmac

crypto map VPNMAP 10 ipsec-isakmp
 set peer 50.0.0.2
 set transform-set TRANS
 match address 101

interface GigabitEthernet0/0
 crypto map VPNMAP

access-list 101 permit ip 10.0.0.0 0.0.0.255 20.0.0.0 0.0.0.255
```


**Router3:**
```bash
crypto isakmp policy 10
 encr aes
 hash sha
 authentication pre-share
 group 2
 lifetime 86400

crypto isakmp key cisco address 30.0.0.1

crypto ipsec transform-set TRANS esp-aes esp-sha-hmac

crypto map VPNMAP 10 ipsec-isakmp
 set peer 30.0.0.1
 set transform-set TRANS
 match address 102

interface GigabitEthernet0/0
 crypto map VPNMAP

access-list 102 permit ip 20.0.0.0 0.0.0.255 10.0.0.0 0.0.0.255
```

### 🔍 Verification Commands
**On Router0 or Router3:**
```bash
show crypto isakmp sa
show crypto ipsec sa
```

### 📁 Files Included
- `topology.png` – Network diagram
- `README.md` - this file
- `vpn_tunneling.pkt` – Cisco Packet Tracer file

### 📝 Notes
- Ensure interface IPs and subnet masks are set correctly.
- All router interfaces should be up.
- ACLs must accurately reflect the interesting traffic for VPN.
