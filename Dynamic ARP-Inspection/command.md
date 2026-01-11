<h1>PROJECT: LAN-Hardening Suite (DAI) Dynamic ARP Inspection</h1>
  
## DESCRIPTION: Prevention of ARP Poisoning and Man-in-the-Middle (MitM)

# Enable DAI on specific VLANs
switch(config)#ip arp inspection vlan 1

# Configure a TRUSTED port (Uplinks/Routers)
switch(config)#interface GigabitEthernet0/1
 switch(config-if)# ip arp inspection trust

# Set rate limits on access ports to prevent DoS
switch(config-if)#interface range Gi0/2 - 24
  switch(config-if)#ip arp inspection limit rate 15
