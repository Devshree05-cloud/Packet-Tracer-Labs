Instructions and actions:

1.	Configure dynamic NAT on R1
   
>Translate all traffic from 172.16.0.0/24

>Create a pool of 100.0.0.1 to 100.0.0.2 from the subnet 100.0.0.0/24

Commands used:

R1(config)#int g0/1

R1(config-if)#ip nat inside

R1(config-if)#int g0/0

R1(config-if)#ip nat outside 

R1(config-if)#exit

R1(config)#access-list 1 permit 172.16.0.0 0.0.0.255

R1(config)#ip nat pool POOL1 100.0.0.1 100.0.0.2 netmask 255.255.255.0

R1(config)#ip nat inside source list 1 pool POOL1 

R1(config)#exit

Since only two inside global IP addresses were assigned in the pool, both PC1 and PC2 can ping across the network, but not PC3 at the same time.

2.	Clear the NAT translations and remove the current NAT configuration. Switch the configuration to PAT using R1’s public IP address. (at interface g0/0 – 203.0.113.1)

Commands used:

R1(config)#ip nat inside source list 1 interface g0/0 overload

R1(config)#do sh ip nat translations

R1(config)#do sh run | include ip nat

ip nat outside

ip nat inside

ip nat pool POOL1 100.0.0.1 100.0.0.2 netmask 255.255.255.0

ip nat inside source list 1 interface GigabitEthernet0/0 overload

R1(config)#no ip nat pool POOL1 100.0.0.1 100.0.0.2 netmask 255.255.255.0

R1(config)#do sh run | include ip nat

ip nat outside

ip nat inside

ip nat inside source list 1 interface GigabitEthernet0/0 overload

3.	Now, ping google.com from each PC
   
All the PCs are able to ping google.com simultaneously now; they are being assigned a single inside global address (the IP address of interface g0/0 of R1), and only the port numbers are changed because of the “overload” in the command.

All the PCs are now able to ping google.com simultaneously.

Kindly review the attached PDF for relevant screenshots. 

   

