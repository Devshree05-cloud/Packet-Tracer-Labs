Tried the basic configuration of SNMP for the first time. 

1. Configured 2 community strings on the router for read only and read/write access.

   Commands used in the global configuration mode:

   #snmp-server community cisco1 ro

   #snmp-server community cisco2 rw

On the MIB Browser of PC1:

3. Used SNMP version 2 on PC1 to utilize the get commands through community string cisco1.

4. Also changed the hostname of R1 from PC1 using the community string cisco2.

All the necessary screenshots are attached in the PDF. 
