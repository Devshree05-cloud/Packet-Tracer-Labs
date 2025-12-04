Refer to the pdf attached

Instructions and actions:

1. Which dynamic routing protocol is Enterprise A using?

   #sh ip route
OSPF (O)

2. Which route will be used if PC1 tries to access SRV1 or vice versa?

   PC1-SW1-R1-R2-SW2-SRV1   (checked using simulation mode)

3. Ping 1.1.1.1 on PC1 and SRV1

   PC1's message reaches ISPBR1 (nearest path to internet)

   SRV1's message reaches ISPBR2

4. Configure floating static routes and shutdown the g0/2/0 interface on both R1 and R2.

   The administrative distance (AD) of the configured static route should be lesser than the OSPF (AD = 110)

CLI command on the routers (R1, SPR1, SPR2 and R2):

#ip route [destination ip] [subnet mask] [next hop] [AD<110]

PC1 is able to reach SRV1 and vice versa through the longer route (R1-SPR1-SPR2-R2)

This was checked via simulation mode.
