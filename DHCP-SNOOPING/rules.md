! ###########################################################
! PROJECT: LAN-Hardening - DHCP Snooping Implementation
! DESCRIPTION: Prevents Rogue DHCP Servers and Man-in-the-Middle
! ###########################################################

! 1. Global Enablement
! Enable DHCP snooping globally on the switch
ip dhcp snooping

! 2. VLAN Specific Configuration
! Apply snooping to specific VLANs (e.g., VLAN 10 and 20)
ip dhcp snooping vlan 10,20

! 3. Option 82 Handling
! Disabling Option 82 if your DHCP server is on the same subnet
! (Prevents drops on some legacy DHCP server implementations)
no ip dhcp snooping information option

! 4. Configure Trusted Interfaces (Uplinks/Servers)
! The interface connected to your REAL DHCP server must be trusted.
interface GigabitEthernet0/1
  description UPLINK-TO-DHCP-SERVER
  ip dhcp snooping trust
exit

! 5. Configure Untrusted Interfaces (End-User Ports)
! All user-facing ports are untrusted by default.
! We add Rate Limiting to prevent DHCP Starvation attacks.
interface range GigabitEthernet0/2 - 24
  description USER-ACCESS-PORTS
  
  ! Limit to 15 DHCP packets per second to prevent DoS
  ip dhcp snooping limit rate 15
  
  ! Ensure the port is in the correct VLAN
  switchport mode access
  switchport access vlan 10
  
  ! Additional Hardening: Enable Port-Security
  switchport port-security
  switchport port-security maximum 2
exit

! 6. Database Persistence
! Save the DHCP binding database to flash memory.
! This ensures the switch remembers bindings after a reboot.
ip dhcp snooping database flash:snooping-db.bin

! 7. Verification Commands (For your Documentation)
! Use these to verify the binding table and statistics:
! show ip dhcp snooping
! show ip dhcp snooping binding
! show ip dhcp snooping statistics

! END OF CONFIGURATION
