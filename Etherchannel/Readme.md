(End host and SVI IP addresses are pre-configured)

Instructions and CLI commands I used:

1. Configure Layer 2 EtherChannel between ASW1 and DSW1 using LACP.
    Configure it as a trunk.

In global configuration mode on ASW1 

#int range g0/1-2

#channel-group 1 mode active     (active or passive for LACP)

#int po1                  (Once an interface is part of a channel-group, the switch locks certain parameters.
                          L2 commands, like the switchport mode trunk, must be applied only on the Port-Channel.)
#switchport mode trunk

Same set of commands for DSW1 po1.

2. Configure Layer 2 EtherChannel between ASW2 and DSW2 using PAgP.
    Configure it as a trunk.

   For PAgP

   #channel-group 1 mode desirable        (auto or desirable for PAgP)

3. Configure Layer 3 EtherChannel between DSW1 and DSW2 using static EtherChannel.

   In global configuration mode on DSW1 and DSW2

   #int range g1/0/1-2

   #no switchport               (to configure them as routed ports)

   #channel-group 2 mode on        (L3 etherchannel command)

   #ip address 10.0.0.1/10.0.0.2 255.255.255.252         (see the network topology given in the pdf)

4. Configure routes to allow the PCs to reach SRV1.

   Before static routing configuration, enable routing in the global config mode using the command

   #ip routing

5. The pc's and server are able to ping each other.
