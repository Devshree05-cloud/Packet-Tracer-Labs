Instructions and actions:

Configure port security on the following interfaces

1.	SW1 F0/1, F0/2, F0/3 –
   
Violation mode: Shutdown

Maximum addresses: 1

Sticky learning: Disabled

Ageing time: 1 hour

By default, the first three conditions will be implemented. I have to enable port security for the interfaces and the ageing timer.

Commands used:

SW1(config-if)#int f0/2

SW1(config-if)#switchport mode access

SW1(config-if)#switchport port-security

SW1(config-if)#do sh port-security int f0/2

Port Security : Enabled

Port Status : Secure-up

Violation Mode : Shutdown

Aging Time : 0 mins

Aging Type : Absolute

SecureStatic Address Aging : Disabled

Maximum MAC Addresses : 1

Total MAC Addresses : 0

Configured MAC Addresses : 0

Sticky MAC Addresses : 0

Last Source Address:Vlan : 0000.0000.0000:0

Security Violation Count : 0

SW1(config-if)#switchport port-security aging time 60

(These commands were configured to the interface range f0/1-3)

2.	SW2 G0/1
   
Violation mode: Restrict

Maximum addresses: 4

Sticky learning: Enabled

Commands used:

SW2(config-if)#switchport port-security maximum 4

SW2(config-if)#switchport port-security violation restrict

SW2(config-if)#switchport port-security mac-address sticky

SW2(config-if)#do sh port-security int g0/1

Port Security : Enabled

Port Status : Secure-up

Violation Mode : Restrict

Aging Time : 0 mins

Aging Type : Absolute

SecureStatic Address Aging : Disabled

Maximum MAC Addresses : 4

Total MAC Addresses : 1

Configured MAC Addresses : 0

Sticky MAC Addresses : 1

Last Source Address:Vlan : 0060.471C.1D19:1

Security Violation Count : 0

3.	Checking:
   
When PC1, PC2 and PC3 pinged their default gateway, we could observe that following their MAC addresses were updated in the MAC address table of SW2.

As a maximum of 4 MAC addresses were allowed on the g0/1 interface of SW2, one more can’t ping through it. 

Same for SW1, after manipulating the MAC address of PC1 from configuration mode, PC1 is not able to ping through SW1 as SW1 can’t recognise the MAC. 

4. Lab worked successfully and taught me many things about port security. Please review the PDF attached for the screenshots. 





