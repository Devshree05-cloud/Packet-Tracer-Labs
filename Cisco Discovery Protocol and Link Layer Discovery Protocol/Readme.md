Instructions and actions:

1.	Use CDP (and other commands) to identify and label the missing IP addresses and interface IDs of the devices in the network.
   
Commands used on the routers:

#show cdp neighbors 

#show cdp neighbors detail

Also, for the IP address, I can use:

#show ip int br

Device ID is the neighboring device, and Port ID is its interface connected to the local interface of the local device. 

For the IP addresses and subnet masks:

#show ip int <interface id>

2.	Disable CDP on the switch interfaces currently connected to PCs.
   
To know the interfaces connected to end hosts on the switches, use the command:

#show int status

And then in the interface config mode, use:

#no cdp enable

3.	Disable CDP globally on each network device.

4.	Enable LLDP on each network device and enable Tx/Rx on the interfaces connected to other network devices.

Mistake – I was panicking when the #sh lldp neighbors command was displaying 0 total entries, but I had configured the lldp run only on R1, and it is disabled on the networking devices by default, so how would the router fill entries until lldp would be enabled on the neighboring devices' interfaces too. 



