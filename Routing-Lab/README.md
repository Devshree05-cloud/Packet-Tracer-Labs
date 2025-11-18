Static Routing Configuration

I learnt how to create static routes using IP addresses and the CLI of routers. I started by configuring hostnames for routers and switches.

Initially, the ping command from PC1 to PC2 did not work without static routing. The first step was to assign proper IP addresses to the PCs and the respective router interfaces. I configured IP addresses, gateways, and subnet masks for both PCs using their "config" options.

On the routers, I assigned IP addresses using the CLI command:
ip address [interface network address] [subnet mask]

Router interfaces are administratively down by default, so I manually brought them up with:
no shutdown

Next, I configured static routes using the ip route command. I initially represented it like this to highlight an important learning point:
ip route [destination IP address] [subnet mask] [next hop]

I made some mistakes at first, but after configuring all three routers, I understood the logic and the difference between directly connected networks and static routes.

Finally, the PCs were able to ping each other successfully, confirming the setup was correct.
