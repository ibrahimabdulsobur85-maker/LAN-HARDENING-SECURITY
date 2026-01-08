<h1>PROJECT: LAN-Hardening - Port Security Configuration</h1>

## 1. Enter the range of user-facing access ports
- <B>#:interface range fastEthernet0/2 - 24
  
  ## 2.Set the port to Access Mode (Port security cannot run on Trunk ports)
- <B>#:switchport mode access
  
## 3.Enable Port Security
- <B>#:switchport port-security
  
  ## 4.Define the maximum number of MAC addresses allowed per port
  This prevents users from connecting unauthorized mac address content.
- <B>#: switchport port-security maximum 1
  
  ## 5.Enable mac address
   The switch learns the first MAC address it sees and adds it to the 
   running configuration automatically.
 - <B>#: switchport port-security mac-address "the mac address of the pc"
  
  ## 6.Define the Violation Action
   there are three violaation for port security
   <ol>
    <li>protect
    <li>restrict
    <li>shutdown
   </ol>
   <ul>
 <li>#: switchport port-security violation shutdown


## 7.Global Hardening: Disable unused ports
- <b>#:interface range GigabitEthernet0/25 - 48</b>
<ul>
 <li>#:shutdown</li>
