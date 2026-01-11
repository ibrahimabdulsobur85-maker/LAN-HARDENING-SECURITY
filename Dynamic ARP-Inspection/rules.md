
<H1> PROJECT: LAN-Hardening - Dynamic ARP Inspection (DAI) Rules</H1>

## DESCRIPTION: Security logic for preventing ARP Poisoning & MitM

## RULE 1: THE BINDING DATABASE RULE
Enable the validation engine for specific VLANs. 
The switch will now check every ARP packet against the server.
- <B> ip arp inspection vlan 1

## RULE 2: THE TRUST BOUNDARY RULE

Infrastructure ports are trusted and skip inspection.
- <B> interface GigabitEthernet0/1
  - <B> ip arp inspection trust
exit

## RULE 3: CONTROL PLANE PROTECTION (RATE LIMITING)

Prevent ARP flooding from untrusted ports to protect Switch CPU.
If a port exceeds 15 ARP packets/sec, it is automatically disabled.
- <B> interface range GigabitEthernet0/2 - 24
  - <B> ip arp inspection limit rate 15 burst interval 1
exit

## RULE 4: LOGGING & AUDIT RULES

Record violations for forensic analysis.
- <B> ip arp inspection log-buffer entries 1024
- <B> ip arp inspection log-buffer logs 5 interval 10

## RULE VERIFICATION COMMANDS

 - <B> show ip arp inspection----------------Verify overall rule status
 - <B> show ip arp inspection interfaces------------Verify Trust Boundary (Rule 2)
 - <B> show ip arp inspection statistics-------- Verify Rule 1 Enforcement
 - <B> show log | include ARP-------------Audit violations of Rule 4
