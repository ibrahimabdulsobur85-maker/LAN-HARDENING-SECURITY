<h1>LAN-Hardening: Port-Security
  
## Defend your Layer 2 infrastructure against unauthorized devices and MAC flooding attacks.

<h2>Description</h2>
<br>Port Security is a Layer 2 traffic control mechanism that limits access to a network interface by restricting which MAC addresses are permitted to send traffic through a given port. It acts as a critical first line of defense against unauthorized physical access, MAC flooding attacks, and other threats that attempt to exploit switch MAC ADDRESS tables.

## Key features of the implementation/Environments include:

- <B> SIMULATION SOFTWARE (Cisco Packet Tracer) Deployments to minimize hardware costs and physical space usage
- <B> CISCO Switch 2960
- <B> PC's
- <B> Straight through cables</b>


<h2>Project walk-through:</h2>

<p align="center">
Network Diagram: <br/>
<img src="https://imgur.com/eVghmCK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
ENABLING MODE ACCESS,ENABLING PORT-SECURITY AND ADDING THE MAC ADDRESS OF THE PC:  <br/>
<img src="https://imgur.com/sBz9WMA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
CONFIGURING THE VIOLATION MODE (PROTECT):  <br/>
<img src="https://imgur.com/HOazwgq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
  FOWARDING PACKETS TO SEE THE MAC ADDRESS:  <br/>
<img src="https://imgur.com/1fECBMc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
MAC ADDRESS ENABLED:  <br/>
<img src="https://imgur.com/Ryk7bgS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
SHUTTING DOWN UNUSED INTERFACE:  <br/>
<img src="https://imgur.com/J7UaCRB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<h2>Conclusion</h2>

<br> This project represents a critical step in strengthening Layer 2 access control through the implementation of Port Security. By limiting the number of permitted MAC addresses per switch port and explicitly defining authorized devices, the network prevents unauthorized systems from gaining physical or logical access. Port Security enforces strict access policies at the edge, ensuring that only trusted endpoints are allowed to communicate on the network.

Together, these controls significantly reduce the risk of MAC flooding and unauthorized device insertion, two common techniques used to compromise switch forwarding behavior and intercept traffic. By enforcing device-level trust at the port, Port Security enhances network visibility, preserves MAC ADDRESS table integrity, and reinforces a Zero Trust posture where access is continuously validated rather than implicitly granted.
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
