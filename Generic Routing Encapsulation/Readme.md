Instructions and actions:

1.	Configure a GRE tunnel to connect R1 and R2.
   
2.	Configure OSPF on the tunnel interfaces of R1 and R2 to allow PC1 and PC2 to communicate.

It is literally fun to search and configure everything on your own without any cheat sheet of commands.

I used OSPF commands in the global configuration mode of R1, SPR1, R2 and SPR2.

(For the screenshots of network topology, commands ,and proofs, kindly review the PDF. It is clean and organized)

After the OSPF default route and network commands - 

PC1 can ping 100.0.0.1, and PC2 can ping 200.0.0.1. Therefore, individual networks are established.

Also, R1 can ping 200.0.0.2 (public IP of R2) and R2 can ping the public IP of R1 (100.0.0.2)

But PC1 can’t ping PC2. So here we have the solution – GRE tunnels.

The I configured GRE at R1 and R2. 

Lab worked successfully, PC1 and PC2 are able to ping each other. 

Basically, GRE tunnels use the same path, but they are created virtually so that traffic is encapsulated in a GRE header over the entire route.

Once again, kindly review the PDF. 

