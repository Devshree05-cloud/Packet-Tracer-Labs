Instructions and Actions:

1. Configure the switchports connecting switches as trunk ports.

“switchport mode trunk” command on the g0/1 of SW1, g0/1 and g0/2 of SW2 and g0/1 of SW3

2. Disable DTP on the ports.

For checking the current mode, I used “do sh int g0/1 (the given interface) switchport”

To disable DTP – “switchport no negotiate”

3. Configure SW1 in VTP domain CCNA.
   
In the global configuration mode, first I used the command to check current status 

“do sh vtp status”

Version 2 is active, domain name undefined 

For domain name – “vtp domain CCNA”

4. Create VLANs 10, 20, and 30 on SW1.
   
In the global configuration mode:

#vlan 10

#vlan 20

#vlan 30

To recheck:

#do sh vlan br

5. Have SW2 and SW3 added VLANs 10, 20, and 30?
   
Yes, checked using “do sh vtp status”

6. Configure SW2 in VTP transparent mode.
    
#vtp mode transparent

7. Add VLAN40 to SW2. Is VLAN40 added to the VLAN database of SW1/SW3?
    
No, checked using “do sh vlan br”

8. Configure SW3 in VTP client mode. Try to configure VLAN50 on SW3. Is it added?
    
No, it displayed “VTP VLAN configuration not allowed when device is in CLIENT mode.”

9. Configure all switchports connected to hosts in the correct VLAN.
    
#int (int name)

#switchport mode access     (this is the command which turns off the DTP on the particular interface)

#switchport access vlan (vlan number)
