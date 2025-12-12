Checked “#do sh ip protocols” in the config-router mode on R1.
   
Networks are pre-configured.
   
Configuring the serial interface between R1 and R2 first.
   
We need to check the DCE and DTE from both routers. Therefore, command -
   
#do sh controllers s0/0/0    (in the config-router mode on R1)

R1 is the DCE, and R2 is the DTE.
    
Through the same command, we came to know the clock rate on R1 – 2000000.
    
Clock rate 128000 is configured in the config-if mode on S0/0/0 of R1.
    
The S0/0/0 of both the routers have no OSPF enabled on them; it is point-to-point, PPP. That means R1 and R2 will share full network adjacency.
    
1. Only R3 has a route to 10.0.2.0/24. Why? Fix the problem.
    
Since the g0/1 interface of R3 is showing a point-to-point network type, but it should be broadcast. 

Command used – (config-if)#no ip ospf network point-to-point

And OSPF is enabled on g0/0 and g0/1 interfaces of R3. 

2. R2 and R4 won't become OSPF neighbours with R5. Why? Fix the problem.
    
Since the hello and dead timers of R5 are different. 

Command used on R5 – (config-if)#ip ospf hello-interval 10

                                #ip ospf dead-interval 40
                                
3. PC1 and PC2 can't ping the external server 8.8.8.8. Why? Fix the problem.
    
R5 needs to advertise the default interface connected to its g0/0/0 interface 


Command used - #router ospf 1

		           #default-information originate
               
               #ip route 0.0.0.0 0.0.0.0 203.0.113.2
               
PC2 can ping 8.8.8.8.
    
*Mistake – I had not checked the s0/0/0 interfaces of both R1 and R2, which led to no OSPF advertisement of 10.0.1.0 connected to R1.
    
I enabled s0/0/0 of both R1 and R2 and assigned IP addresses to them.
    
PC1 can also ping 8.8.8.8 now.

Lab successfully working
