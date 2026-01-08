
<H1>PROJECT: LAN-Hardening - DHCP Snooping Security Rules</H1>
<B>DESCRIPTION: Layer 2 mitigation for Rogue DHCP & Starvation</B>

## RULE 1: GLOBAL ACTIVATION</H2>
- <B>Enable the snooping engine and define protected VLANs.
- <B>ip dhcp snooping
- <B>ip dhcp snooping vlan 1

## RULE 2: TRUST BOUNDARY ENFORCEMENT
Explicitly permit DHCP server traffic ONLY on authorized uplinks.
- <B>interface GigabitEthernet0/1
  description UPLINK_TO_DHCP_SERVER
- <B>  ip dhcp snooping trust

## RULE 3: RATE LIMITING (ANTI-STARVATION)
Restrict the number of DHCP packets per second on untrusted ports.
This prevents CPU exhaustion and IP pool depletion.
- <B>interface range GigabitEthernet0/2 - 24
  description ACCESS_PORTS
  - <B>ip dhcp snooping limit rate 15
  

