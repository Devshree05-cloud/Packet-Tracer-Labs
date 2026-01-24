Instructions and actions:

1. Configure Static NAT on R1

Commands used – 

R1(config)#int g0/1

R1(config-if)#ip nat inside 

R1(config-if)#int g0/0

R1(config-if)#ip nat outside 

R1(config-if)#exit

R1(config)#ip nat inside source static 172.16.0.1 100.0.0.1 

R1(config)#ip nat inside source static 172.16.0.2 100.0.0.2

R1(config)#ip nat inside source static 172.16.0.3 100.0.0.3 

R1(config)#do sh ip nat translations

Pro Inside global Inside local Outside local Outside global

--- 100.0.0.1 172.16.0.1 --- ---

--- 100.0.0.2 172.16.0.2 --- ---

--- 100.0.0.3 172.16.0.3 --- ---

(PC1 is now able to ping SRV1 across the internet)

2.	Ping google.com from PC1, and then check the nat translations on R1

Here, the PC asks SRV1 for the IP address of google.com on port 53, which is used for DNS

3.	Clear the NAT translations on R1. Which entries remain?

   Static entries remain.

Kindly refer to the PDF attached for CLI and Command Prompt screenshots.





