In this lab, I tried the extended ACLs which are more precised and can be easily edited.

Screenshots of solutions to the following requirements are attached in PDF:

Configure extended ACLS to fulfil the following network policies:

1. Hosts in 172.16.2.0/24 can't communicate with PC1.

2. Hosts in 172.16.1.0/24 can't access the DNS service on SRV1.

3. Hosts in 172.16.2.0/24 can't access the HTTP or HTTPS services on SRV2.

Mistake – I forgot to give the “permit ip any any” command for the first instruction, which can lead to problems later on that interface. Therefore, we know that ACLs can be edited, so I just entered the access-list ID again and gave the command. 

Add ons I will do later in the same repository:

I will try to use the DNS hostnames instead of IP in the given http browser in Packet Tracer. 



