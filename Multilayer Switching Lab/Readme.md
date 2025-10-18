The trunk between SW1 and SW2 is preconfigured and R1 is configured using ROAS, now - 

Instructions and actions:

1. Replace the ROAS configuration on R1-SW2 with a point-to-point Layer 3 connection.
I used the “#no interface [subinterface id]” command under the global configuration mode for interface g0/0

2. Use the IP addresses given in the network diagram.
First, I used the “#default int g0/0” command to remove the previous IP address so we can assign the new IP address 10.0.0.194

3. Configure a default route on SW2, with R1's G0/0 interface as the next hop.
CLI, global configuration mode:
#default int g1/0/2
#int g1/0/2 – entered in global interface configuration mode
#ip routing [enabling routing] – entered in global configuration mode
#int g1/0/2 – once again, we needed to enter the global interface configuration mode
#no switchport – configured the interface as a routing port 
#ip address 10.0.0.193 255.255.255.252
exit – back to global configuration (because a static route is not an interface property)
#ip route   0.0.0.0 0.0.0.0 10.0.0.194 – 0’s to indicate that when you have no specific destination, just go to the next hop as default route.

4. Configure SVIs on SW2, one for each VLAN. 
Used the commands in global configuration mode
#int vlan 10
#ip address 10.0.0.62 255.255.255.192 (gateway for vlan10)
#no shutdown

5. Test inter-VLAN connectivity by pinging between VLANs.
PC1 can ping to all the PC’s from different VLANs

6. Test connectivity to the Internet by pinging 1.1.1.1
(Routes have already been configured on R1 and the Internet router and access ports are configured on SW1)
Working well.
