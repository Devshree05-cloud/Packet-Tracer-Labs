Instructions and actions:

1.	Configure a default route to the Internet on R1.
   
In the Global Configuration mode:

#ip route 0.0.0.0 0.0.0.0 203.0.113.2 

2.	Configure PC1, PC2, and PC3 to use 1.1.1.1 as their DNS server.

3.	Configure R1 to use 1.1.1.1 as its DNS server.

4.	Configure host entries on R1 for R1, PC1, PC2, and PC3.

“#ip dns server” is an unrecognised command on Cisco Packet Tracer.

5.	Ping PC1 by name from R1.

The host table on R1 is the device’s local table, which helps the device to find the destination device IP with the configured name in its host table.

6.	From PC1, ping youtube.com by name. Analyse the messages being sent.
   
I used the simulation mode to check what is actually happening here. 

What was happening (viewed via simulation mode):

DNS:

PC1 – SW1 – R1 – Internet – 1.1.1.1

IP address for “youtube.com” is discovered [172.217.6.78]

When PC1 knew the destination IP address but not the destination MAC address, and also where exactly the IP address is?

ARP comes into play and tells the MAC address of the destination IP.

Then ICMP requests and echo responses are made, and data flows.

All the necessary screenshots for this lab are in the PDF attached.
