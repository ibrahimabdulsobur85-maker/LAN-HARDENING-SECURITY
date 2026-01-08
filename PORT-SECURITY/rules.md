 <h1>PROJECT: LAN-Hardening - Port Security Logic
   
 ## DESCRIPTION: Layer 2 Access Control & MAC Filtering Rules

## RULE 1: ACCESS ENFORCEMENT

<h3> Port security only works on static access ports.</h3> 

<ul>
  <li>interface range GigabitEthernet0/2 - 24</li>
  <li>switchport mode access</li>
  </ul>

## RULE 2: DEVICE LIMITATION 

<h3> Define the maximum number of MAC addresses allowed.
 Prevents unauthorized mac address content from being connected.</h3>

  
  <ul>
  <li style="font-size: 50px;">switchport port-security</li>
  <li>switchport port-security maximum 1</li>
  </ul>

## RULE 3: IDENTITY PERSISTENCE 

<h3>Automatically learn the device connected and save 
 it to the running-config so it survives a reboot.</h3>
 
 <ul>
  <li>switchport port-security mac-address</li>
 </ul>

 
## RULE 4: VIOLATION RESPONSE

<h3>If an unauthorized device is detected, the port is 
immediately disabled (shutdown) to protect the LAN.</h3>

<ul>
  <li>switchport port-security violation shutdown</li>
</ul>

## RULE 5: BLACK-HOLE UNUSED PORTS 


<h3>Any port not in use is a security risk. Shut them down</h3>

<ul>
<li>interface range GigabitEthernet0/25 - 48</li>
<li>shutdown</li>
</ul>


 VERIFICATION COMMANDS
<ul>
<li>#:show port-security------------Summary of all ports</li>
 <li>#:show port-security address----------List of learned Sticky MACs</li>
<li>#:show port-security interface gi0/2---------- Detailed violation status</li>
</ul>
