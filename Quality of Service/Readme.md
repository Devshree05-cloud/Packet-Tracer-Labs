I watched the tutorial video and followed along to do this lab, as QoS configuration is not a part of CCNA. 

Instructions:

Configure the following QoS settings on R1 and apply them outbound on interface G0/0/0:

1.	Mark HTTPS traffic as AF31 – Provide a minimum 10% bandwidth as a priority queue.
   
2.	Marh HTTP traffic as AF32 – Provide a minimum 10% bandwidth.
   
3.	Mark ICMP traffic as CS2 – Provide a minimum 5% bandwidth.

Actions:

1. I used a ‘class-map’ to select the traffic and map it to a particular category based on protocol.

2. Now, I will use ‘policy-map’ to exactly configure what is to be done with that selected and mapped traffic.

3. To apply these policies on the selected traffic going through a particular interface physically, we will use the ‘service-policy’ command on the interface.  

4. Outbound packets at g0/0/0 interface of R1 are analysed using the simulation mode for ICMP, HTTP and HTTPS requests from PC1 to SRV1.

Check the PDF attached for the necessary screenshots - commands, results and deeper handwritten explanation. 



