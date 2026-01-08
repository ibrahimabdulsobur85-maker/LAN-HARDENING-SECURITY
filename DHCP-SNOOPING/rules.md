
<H1>PROJECT: LAN-Hardening - DHCP Snooping Security Rules</H1>
- <B>DESCRIPTION: Layer 2 mitigation for Rogue DHCP & Starvation</B>

<H2>RULE 1: GLOBAL ACTIVATION</H2>
- <B> Enable the snooping engine and define protected VLANs.
- <B> ip dhcp snooping
- <B> ip dhcp snooping vlan 1

<H2> RULE 2: TRUST BOUNDARY ENFORCEMENT ---
Explicitly permit DHCP server traffic ONLY on authorized uplinks.
- <B>interface GigabitEthernet0/1
  description UPLINK_TO_DHCP_SERVER
- <B>  ip dhcp snooping trust

<H2> RULE 3: RATE LIMITING (ANTI-STARVATION) ---
Restrict the number of DHCP packets per second on untrusted ports.
This prevents CPU exhaustion and IP pool depletion.
interface range GigabitEthernet0/2 - 24
  description ACCESS_PORTS
  ip dhcp snooping limit rate 15
exit
  
 <H2> RULE 5: OPTION 82 HANDLING ---
Disable Option 82 if the DHCP server is in the same broadcast domain
 to prevent packet drops due to relay information incompatibility.
no ip dhcp snooping information option

<H2> RULE 6: DATABASE PERSISTENCE ---
! Write the binding table to local flash memory to ensure security 
! mappings survive a system reboot.
ip dhcp snooping database flash:dhcp_bindings.db
