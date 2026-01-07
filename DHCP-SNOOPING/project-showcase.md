<h1>LAN-Hardening: DHCP Snooping Security Suite
Defend your Layer 2 infrastructure against Rogue DHCP Servers and MitM attacks.</h1>

<h2>Description</h2>
<br>This repository offers a production-ready framework for securing Local Area Networks (LANs) against Man-in-the-Middle (MitM) and DHCP starvation attacks. By establishing a defined trust boundary, the configuration ensures that only authorized DHCP servers can assign IP addresses, while simultaneously maintaining a security database to validate and monitor all network traffic.

## Key features of the implementation/Environments include:

- <B> SIMULATION SOFTWARE (Cisco Packet Tracer) Deployments to minimize hardware costs and physical space usage
- <B> CISCO Switch 2960
- <B> PC's
- <B> Straight through cables
- <B> SERVER </b>


<h2>Project walk-through:</h2>

<p align="center">
Network Diagram: <br/>
<img src="https://imgur.com/8y8Bv9u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
CONFIGURING ON VLAN 1:  <br/>
<img src="https://imgur.com/BkVQRfo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
CONFIGURING THE TRUST ON THE INTERFACE OF DHCP SERVER:  <br/>
<img src="https://imgur.com/FCoMP77.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
CONFIGURING THE LIMIT RATE:  <br/>
<img src="https://imgur.com/HzMiAHH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
SUCCESSFUL DHCP REQUEST:  <br/>
<img src="https://imgur.com/ifDZNk5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
CONFIRMATION OF THE IP ADDRESS ON CMD AND RELEASING/RENEWING OF THE ADDRESS:  <br/>
<img src="https://imgur.com/RSQUQ4u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<h2>Conclusion</h2>

<br>This project marks a significant milestone Implementing DHCP Snooping transforms an otherwise vulnerable, open network into a hardened Zero Trust environment. By explicitly defining trusted and untrusted interfaces, the network enforces strict trust boundaries that prevent rogue DHCP servers from issuing unauthorized IP configurations. In addition, DHCP Snooping applies rate limiting to DHCP traffic, effectively mitigating DHCP starvation attacks that can lead to service outages.

Together, these controls significantly reduce the attack surface within the local network, eliminating common vectors for internal Man-in-the-Middle (MitM) attacks and ensuring the integrity and availability of network services. The result is a more resilient infrastructure that continuously validates device behavior rather than assuming trust based on network location.
<br />
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
