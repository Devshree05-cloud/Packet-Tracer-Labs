This lab was my first step in understanding the functionality and configuration of Wireless networks and this was an amazing experience. 

1. In the Network Topology, we have a WLC connected through a trunk port to a multilayer switch. The multilayer switch is connected with two access points and one PC, which is used by me to access the GUI of WLC via HTTPS request in the Web Browser.

Username: admin 

Password: Cisco123

2. I configured the interfaces for WLANs on WLC first. They are generally referred as Internal and Guest WLANs, the VLAN IDs here were 100 and 200 respectively.

3. Then, I created the Guest and Internal WLANs on the WLC and used WPA2+PSK security policies.

4. Finally, I associated a wireless device with an AP, entered SSID and password and the devices were successfully connected.

5. The allotted IP address to the wireless device was not from the internal VLAN subnet even though I configured the wireless device in the internal VLAN. It was rather from the Management VLAN subnet. But this is the default error in Cisco Packet Tracer, it works different in industry tools

This is how wireless technology works. There are CAPWAP connections between both Access Points and the WLC for data transfer, and the WLCs are connected to a wired network.

For a detailed document with screenshots, kindly review the attached PDF.
