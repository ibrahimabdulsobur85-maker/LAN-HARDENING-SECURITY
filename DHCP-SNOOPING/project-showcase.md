# 🛡️ LAN-Hardening: DHCP Snooping Implementation

This repository provides production-ready configurations to mitigate **Man-in-the-Middle (MitM)** and **DHCP Starvation** attacks by implementing DHCP Snooping.

---

## 📊 Security Architecture
The following diagram illustrates the boundary between trusted and untrusted network segments.

<p align="center">
  <img src="https://imgur.com/uTN8iDG" alt="DHCP Snooping Diagram" width="700">
  <br>
  <i>Figure 1: Trusted vs. Untrusted port logic for DHCP traffic.</i>
</p>



---

## ⚙️ Step-by-Step Implementation Script

Below is the logic used to harden the switch. Each step is designed to address a specific attack vector.

### Step 1: Global Activation
We must enable the feature globally before the switch starts building the binding database.
```bash
ip dhcp snooping
ip dhcp snooping vlan 10,20  # Apply only to specific user VLANs
