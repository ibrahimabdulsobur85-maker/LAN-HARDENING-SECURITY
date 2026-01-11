<h1>LAN-Hardening: DYNAMIC ARP INSPECTION
  
## Defend your Layer 2 infrastructure against unauthorized devices and ARP SPOOFING attacks.

<h2>Description</h2>
<br>Dynamic ARP Inspection (DAI) is a Layer 2 security feature that protects networks from ARP-based attacks. Because ARP lacks authentication, attackers can send forged messages to "poison" ARP tables, allowing them to intercept or disrupt traffic.

DAI neutralizes this threat by inspecting ARP traffic on untrusted ports. It verifies IP-to-MAC mappings against a manually defined ARP Access Control List (ACL). By enforcing strict trust boundaries, DAI ensures that only validated communication is permitted, dropping any malicious or unrecognized ARP packets.
## Key features of the implementation/Environments include:

- <B> SIMULATION SOFTWARE (Cisco Packet Tracer) Deployments to minimize hardware costs and physical space usage
- <B> CISCO Switch 2960
- <B> PC's
- <B> Straight through cables
- <B> Server</b>

<BR>NOTE:DUE TO THE ENVIRONMENT WE USED (PACKET TRACER) SOME FEATURES ARE NOT ABLE TO SHOW UP

<h2>Project walk-through:</h2>

<p align="center">
Network Diagram: <br/>
<img src="https://imgur.com/e8eIyzA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
CONFIGURATION PROCESS(PROTECT):  <br/>
<img src="https://imgur.com/hrRw3pS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<br />
<br />
</p>

<h2>Conclusion</h2>

<br> The implementation of Dynamic ARP Inspection (DAI) represents a fundamental shift in local area network security, moving from a vulnerable "trust-by-default" model to a proactive, Zero-Trust architecture at Layer 2. By addressing the inherent lack of authentication in the Address Resolution Protocol, this project effectively neutralizes one of the oldest and most effective attack vectors in networking: the exploitation of ARP's stateless nature.
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

