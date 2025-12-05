I configured the EIGRP protocol which is a distance vector protocol in IGP. For the Autonomous System number 100.

Refer to the pdf attached for network topology. 

In the first step, hostnames and ip addresses to the router interfaces were given. They were enabled using the "no shutdown" command.

Then, the virtual loopback interfaces were configured on each router with the subnet mask 255.255.255.255

Under the router eigrp command, ip addresses with wildcard masks were configured using the network command. These would be advertised to the neighboring router.
#network [ip address] [wildcard mask]

Loopback interface and other interfaces with no important router were made passive interfaces to avoid unnecessary messaging. 

At last, the command "variance 2" in the config-router mode was used to configure the alternate path if the best path link in eigrp fails. The command states that the feasible distance of the feasible successor must be lesser than or equal to twice of the feasible distance of the successor.


