Instructions and actions:

1.	Configure the following DHCP pools on R2:
   
POOL1: 192.168.1.0/24 (reserve .1 to .10)

DNS 8.8.8.8

Domain: jeremysitlab.com

Default Gateway: R1

POOL2: 192.168.2.0/24 (reserve .1 to .10)

DNS 8.8.8.8

Domain: jeremysitlab.com

Default Gateway: R2

POOL3: 203.0.113.0/30 (reserve .1)

2.	Configure R1's G0/0 interface as a DHCP client.

From my configuration, R1’s g0/0 got the IP address 203.0.113.2

3.	Configure R1 as a DHCP relay agent for the 192.168.1.0/24 subnet.

4.	Use the CLI of PC1 and PC2 to make them request an IP address from their DHCP server.

So, I got the assigned IP address for PC1 as 192.168.1.12 and for PC2 as 192.168.2.11.

