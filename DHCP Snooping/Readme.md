In this lab, I configured IP DHCP snooping on SW1 and SW2 (network topology available in the PDF attached). 

R1 acted as the DHCP server which would assign addresses from the allotted pool to end hosts. 

Instructions and commands:

1. Configure R1 as a DHCP server. Exclude 192.168.1.1 - 192.168.1.9 from the pool

   Command in the global configuration mode:

   #ip dhcp excluded-address 192.168.1.1 192.168.1.9

   #ip dhcp pool POOL

   #network 192.168.1.0 255.255.255.0

   #default-router 192.168.1.1

2. Configure DHCP snooping on SW1 and SW2

   Commands in config mode:

   #ip dhcp snooping

   #ip dhcp snooping vlan 1   (as only one VLAN is there)

   #no ip dhcp snooping information option

   (to prevent option 82, otherwise, the packet would be dropped)

   #int <interface id>  (uplink interface)

   #ip dhcp snooping trust

The uplink interface refers to traffic from the router, which can be trusted. Downlink interfaces receive traffic from end hosts that cannot be trusted. 

The lab worked successfully and all the end hosts got IP from the targetted pool using <ipconfig /renew> command. 

Please review the PDF for all the necessary screenshots. 
