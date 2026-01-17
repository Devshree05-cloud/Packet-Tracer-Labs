Instructions and actions:

1.	Connect to R1's console port using PC2. Configure username – jeremy, password – ccna.
   
Configured the user verification on R1 CLI using the commands:

R1(config)#username jeremy privilege 0 password ccna

                  #line console 0
                  
                  #login local
                  
                  #exit
                  
The above commands enable user verification before the user exec mode. 

To enable double verification while going to privileged exec mode:

R1(config)#enable password ccna

                  #exit

2.	Use the shutdown and no shutdown commands for the g0/0 interface of R1 and monitor the syslog messages:

Level of Severity = 5 

This is a notice/notification

3.	Enable timestamps for logging messages

4.	Use a Telnet connection from PC1 to R1’s g0/0 interface:
   
I will use the Command Prompt of PC1 – The syslog messages don’t appear by default on VTY lines; therefore, we will use the command:

#do terminal monitor

5.	Enable logging to the buffer, and configure the buffer size of 8192 bytes

6.	Enable logging to the syslog server SRV1 with a level of ‘debugging’
   
The default level in Cisco Packet Tracer is debugging, and it doesn’t allow for configuring higher levels.

7. All the instructions were executed and lab worked successfully, check out the PDF file for screenshots of commands and observations. 





