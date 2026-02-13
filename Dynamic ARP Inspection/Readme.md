In this lab, I configured DHCP server, pool, DHCP snooping and Dynamic ARP Inspection. 

The difference in DAI is all the ports connected to any other network device (and not end host) are configured as trusted ports. 

Commands used for DAI on the Switch:

In the Global Configuration mode - 

#ip arp inspection vlan 1

#ip arp inspection validate dst-mac ip src-mac     (use all these factors for rechecking)

#int <interface id>     (interface connected to a network device)

#ip arp inspection trust

This lab worked successfully, for all the screenshots, commands and checks, kindly review the attached PDF. 
