Through this lab, my understanding of the IGP link state protocol OSPF (Open Shortest Path First or Dijkstra Algorithm) truly increased. 

1. Kindly refer to the pdf attached to see all the CLI commands I used for this lab.

2. First, I gave the correct IP addresses to the router’s interfaces and enabled them.

3. Then configured a loopback interface on each router.

4. Advertised the neighbouring routers to enable OSPF, also advertised the loopback interface:
   
   #router ospf [process id]
   #network [ip address of the connected interface, not local] [wildcard mask] [area 0]
   the above command was used for loopback interface too

   Note - Process ID for routers in the same OSPF area can be different but area number should be the same.

5. Configured the passive interfaces.

6. As the internet link was connected to R1 g0/3 interface, it became ASBR and advertised the default interface in the OSPF domain.
   On the R1 CLI:
   #ip route 0.0.0.0 0.0.0.0 203.0.113.2 (next hop for internet link)
   #router ospf 1       (I had forgotten to make this command and got errors)
   #default-information originate
   
8. The default route is saved on the neighbouring routers.

9. When PC1 tried to ping 0.0.0.0, ICMP travelled between PC1-SW1-R4 cause R4 is the default gateaway for PC1. (Checked using simulation mode)  
