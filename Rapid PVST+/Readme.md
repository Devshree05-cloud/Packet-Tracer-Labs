I followed the following instructions for this lab, answers are well demonstrated with screenshot in the pdf attached. 

1. Which switch is the root bridge?
   
    Use the CLI to examine the port role/state of each interface on the root.
   
    What appears different than what you have learned about the root bridge?
    Answer - Backup Port. 
   
    What is the cause of this?
    Answer - Shared hub flooding the root bridge bpdu to its own port.

2. Without using the CLI, determine the port role/state of each remaining switch interface.
   
    Use the CLI to confirm.

3. Manually configure the appropriate RSTP link type on each interface.
   
    What do you think is the correct link type for SW1's F0/24?
    Answer - It is shared edge.

I observed in Pakcet Tracer:

Problem faced – The F0/3 port was being set to the designated port repeatedly. This is a Cisco Packet Tracer error.

Solution – Enable Rapid PVST using the command in global config mode:

#spanning-tree mode rapid-pvst

This sets back the F0/3 status to the backup port.

If it doesn’t work, use the command in interface config mode for F0/3.

Recheck using #show spanning-tree in privileged exec mode 

