Routing has been preconfigured. The default route on R1, OSPF on all routers with ‘network 0.0.0.0 255.255.255.255 area 0’.

Instructions and Actions:

1.	Configure the software clock on R1, R2, and R3 to 12:00:00 12 Jan 2026 (UTC).
   
Note: The Cisco Packet Tracer doesn’t support calendar commands.

2.	Configure the time zone of R1, R2, and R3 to match your own.
   
I configured Indian Standard Time (IST), which is 5 hours and 30 minutes ahead of the default UTC (Coordinated Universal Time).

3.	Configure R1 to synchronise to NTP server 1.1.1.1 over the Internet. What stratum is 1.1.1.1? What stratum is R1?

R1 is stratum 2.

4.	Configure R1 as a stratum 8 NTP master.

5.	Synchronize R2 and R3 to R1 with authentication.

6.	Why is R1 still stratum 2 and not stratum 8?
   
This behaviour will be shown when the 1.1.1.1 goes down, then R1 will become stratum 8 for R2 and R3. 
