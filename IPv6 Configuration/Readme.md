1.	R1 interface g0/0 MAC address - 0030.F236.4501
   
IPv6 calculated using EUI-64 – 0230:F2FF:FE36:4501

Interface g0/1 MAC –  0030.F236.4502

IPv6 – 0230:F2FF:FE36:4502

2.	R2 interface g0/0 MAC address – 0001.63B0.B801
   
IPv6 calculated using EUI-64 – 0201:63FF:FEB0:B801

Interface g0/1 MAC –  0001.63B0.B801

IPv6 – 0201:63FF:FEB0:B802

3.	Routers CLI – Enabled routing using the command:
   
#ipv6 unicast-routing

And configured the IPv6 addresses for int g0/1

4.	Configured the default gateways and IPv6 addresses on PC1 and PC2.
   
5.	Enabled IPv6 routing on the interface g0/0 of both routers using the interface config command:
    
#ipv6 enable

This enabled the “link-local” address on the interface.

6.	Then I configured IPv6 routes on the g0/0 interfaces:
    
#ipv6 route <destination ipv6> <interface id> <next hop (link-local address)>

7.	PC’s are able to ping each other.
