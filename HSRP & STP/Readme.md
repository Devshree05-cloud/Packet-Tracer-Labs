Instructions and actions:

Configure HSRP on DSW1/DSW2, and ensure sychronization with STP.

In VLAN 10:

-DSW1 is HSRP active/STP root

-DSW2 is HSRP standby/STP secondary root

In VLAN 20:

-DSW2 is HSRP active/STP root

-DSW1 is HSRP standby/STP secondary root

*Mistake – I had configured the HSRP IPs the same as SVIs on DSW1 and DSW2. That must be different; otherwise, the HSRP protocol will confuse a real IP address with a virtual IP address

1. STP configuration for DSW1 from the global configuration mode:

   #spanning-tree vlan 10 root primary
   
   #spanning-tree vlan 20 root secondary

2. HSRP configuration on DSW1:

   #int vlan 10

   #standby version 2 
   
   #standby 1 ip 10.0.10.254     (I was confused and had configured the SVI IP for vlan 10 here)
   
   #standby 1 priority 200        (Greater than 100 to make its state active for vlan 10)
   
   #standby 1 preempt             (Enable possibilities for later negotiation after any change)


   #int vlan 20

   #standby version 2

   #standby 2 ip 10.0.20.254

   #standby 2 priority 50         (Less than 100 for standby state)

   #standby 2 preempt

Same configurations were made on DSW2, keeping the group number and IP for vlan 10 and vlan 20 the same as DSW1, but changing priorities. 

Before checking the pings, make sure <ip routing> command is enabled in the global configuration modes of DSW1 and DSW2. 

The lab worked successfully, for all the necessary screenshots of commands and proofs, kindly review the attached PDF.  
