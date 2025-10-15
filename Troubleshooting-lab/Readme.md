In this lab, there was one problem in the configuration on each router, due to which, PC1 was unable to ping PC2. 
I used two commands to check:
"show ip route" in the privelege exec mode to review the directly connected interfaces, ip addresses to them and static routes configured.
"do sh run | include ip route" under a specific router interface (the config-if mode).
I corrected the wrong ip addresses or interfaces in the routers. 
I learnt using the "no" command appropriately.
PC1 was able to ping PC2.
