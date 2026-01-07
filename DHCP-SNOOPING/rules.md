! ###########################################################
! PROJECT: LAN-Hardening - DHCP Snooping Security Rules
! DESCRIPTION: Layer 2 mitigation for Rogue DHCP & Starvation
! ###########################################################

! --- RULE 1: GLOBAL ACTIVATION ---
! Enable the snooping engine and define protected VLANs.
ip dhcp snooping
ip dhcp snooping vlan 10,20

! --- RULE 2: TRUST BOUNDARY ENFORCEMENT ---
! Explicitly permit DHCP server traffic ONLY on authorized uplinks.
interface GigabitEthernet0/1
  description UPLINK_TO_DHCP_SERVER
  ip dhcp snooping trust
exit

! --- RULE 3: RATE LIMITING (ANTI-STARVATION) ---
! Restrict the number of DHCP packets per second on untrusted ports.
! This prevents CPU exhaustion and IP pool depletion.
interface range GigabitEthernet0/2 - 24
  description ACCESS_PORTS
  ip dhcp snooping limit rate 15
exit

! --- RULE 4: MAC ADDRESS VERIFICATION ---
! Ensure the Source MAC in the layer 2 header matches the CHADDR 
! (Client Hardware Address) inside the DHCP packet payload.
ip dhcp snooping verify mac-address

! --- RULE 5: OPTION 82 HANDLING ---
! Disable Option 82 if the DHCP server is in the same broadcast domain
! to prevent packet drops due to relay information incompatibility.
no ip dhcp snooping information option

! --- RULE 6: DATABASE PERSISTENCE ---
! Write the binding table to local flash memory to ensure security 
! mappings survive a system reboot.
ip dhcp snooping database flash:dhcp_bindings.db
