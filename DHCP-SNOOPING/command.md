
<h1> PROJECT: LAN-Hardening - DHCP Snooping Implementation</h1>
! DESCRIPTION: Prevents Rogue DHCP Servers and Man-in-the-Middle


 - <h2> 1. Global Enablement
 Enable DHCP snooping globally on the switch


- <b> ip dhcp snooping



- <h2> 2. VLAN Specific Configuration
Apply snooping to VLAN 1 because all the interface are all on default vlan and that is VLAN 1

- <b> ip dhcp snooping vlan 1


- <h2> 3. Configure Trusted Interfaces
The interface connected to your REAL DHCP server must be trusted.


   - <b>  interface GigabitEthernet0/1
    - <b>  ip dhcp snooping trust

- <h2> 4. Configure limit rate (End-User Ports)
We add Rate Limiting to prevent DHCP Starvation attacks.
  
 Limit to 15 DHCP packets per second to prevent DoS


 - <b> ip dhcp snooping limit rate 15
  
   Ensure the port is in the correct VLAN

   
- <h2> 5.enabling port security 
  
   Additional Hardening: Enable Port-Security
- <b>  switchport port-security
 - <b> switchport port-security maximum 2




- <h2> 6. Verification Commands
 Use these to verify the binding table and statistics:
- <b> show ip dhcp snooping
- <b> show ip dhcp snooping binding
- <b> show ip dhcp snooping statistics

 END OF CONFIGURATION
