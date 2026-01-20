Instructions and actions:

1.	Connect laptop1 to SW2’s console port:
   
I connected the console port of the laptop with SW2 using a console cable (RS232 from laptop to console port on the switch).

2.	Enable the following configurations:
   
Hostname: SW2

Enable secret: ccna

Username/PW: jeremy/ccna

3.	Now, configure VLAN1 SVI: 192.168.2.253/24
   
Default gateway: R2

Commands in the global configuration mode:

#interface vlan 1

#ip address 192.168.2.253 255.255.255.0

#no shutdown

#exit

#ip default 192.168.2.254 

4.	Configure the following console line security settings on SW2:
   
Authentication: Local user

Exec timeout: 5 minutes 

Command for authentication for the local user in the global configuration mode:

#line console 0

#login local

*What do these commands do?

They tell the switch to use its local user database (usernames/passwords stored on the switch) for authentication when someone connects through that line.

For exec timeout: (user will be logged out after the configured time of inactivity)

5.	Configure SW2 for remote access via SSH:
   
Domain name: jeremysitlab.com

RSA key size: 2048 bits

Authentication: Local user

Exec timeout: 5 mins

Protocols: SSH only

+Limit access to PC1 only

*The difference between access-list and access-class:

An access-list is a set of rules that define who is permitted and who is not; meanwhile, an access-class is a command that applies an access-list to a management plane (Eg, VTY lines, Console port, etc)

Lab done successfully. All the necessary screenshots are attached in the PDF file. 



