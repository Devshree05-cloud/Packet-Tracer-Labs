Problem Statement – What if the main path to the internet via R1 breaks or goes down? When the alternate path comes in, how will it be recognised by the PC’s? Here, we will learn about HSRP. 

1.	Both PC1 and PC2 are using R1 to reach the internet (observed through the simulation mode).
   
2.	The default gateway in the configuration of both is 10.0.1.253 (R1 g0/0).
   
3.	We can also check it using the “tracert 8.8.8.8” command on the PC’s command prompt.
   
4.	Configured HSRP version 2 on both R1 and R2.
   
5.	The priority of R1 is set more than R2 (200 and 50).
    
6.	The Same Virtual IP address is assigned to both the routers, 10.0.1.254 and it has been set as the default gateway for both PC’s.
    
7.	Now, the running configuration on R1 is saved as the startup configuration, and R1 is turned off.
    
8.	PC1 and PC2 can ping 8.8.8.8 (the internet, R3), using R2 this time. So automatically, R2 became the active router.
    
9.	R1 is turned on again. Preemption was enabled on both routers.
  
10.	R1 becomes the active router again.
