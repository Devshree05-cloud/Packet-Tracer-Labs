IPv6 addresses have been pre-configured on the routers.

The serial connections use link-local addresses only.

1.	Using the command #do sh ipv6 int br, I found the ipv6 addresses of R1 and R2 interface connecting with the end hosts. Gave them as IPv6 default gateway on the PC’s and configured their own IPv6 addresses.
   
2.	I enabled the IPv6 routing on R1, R2 and R3 using the command
   
#ipv6 unicast-routing

3.	Then I manually configured static routes on R1 and R3.
   
4.	To configure the route via R2 as a backup route, I used the Administrative Distance at the end of the IPv6 route command:
   
#ipv6 route <destination ipv6> <exit interface> <next hop> <administrative distance>

5.	Since, for Ethernet connection, manually configured routes have an administrative distance of ‘1’, any value more than 1 would be treated as a backup route.
    
6.	I used the link-local address for the route via R2 to give the next hop.
    
7.	Please check out the attached PDF for the screenshots of proper configuration.
    
8.	Even after disabling the link between R1 and R3, PC1 and PC2 can ping each other via R2.
