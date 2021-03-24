# OSPF---Open-Shortest-Path-First

![unnamed](https://user-images.githubusercontent.com/79013111/112276117-5a289180-8ca6-11eb-9e1b-d78a1cd4390d.png)

The OSPF protocol is a link-state routing protocol, which means that the routers exchange topology information with their nearest neighbors. The topology information is flooded throughout the AS, so that every router within the AS has a complete picture of the topology of the AS. This picture is then used to calculate end-to-end paths through the AS, normally using a variant of the Dijkstra algorithm. Therefore, in a link-state routing protocol, the next hop address to which data is forwarded is determined by choosing the best end-to-end path to the eventual destination.

To enable OSPF on a Cisco router and advertise interfaces, the following tasks are required:

    Step 1 - Use the command router ospf process ID to start OSPF.
    Step 2 - Use the network command to enable the interfaces.
    Step 3 - Identify area assignments.
    Step 4 - (Optional) Assign the router ID.

There are basically two ways of configuring the OSPF protocol on a router but what is mostly recommended to use is the wildcard mask configuration.
The way how to enable OSPF on a router are shown as follows:

Configuration one (With Subnet Mask)

    R1(config)#router ospf 1
    R1(config-router)#network 192.168.23.0 255.255.255.0 area 1 
    
-------OR--------
 
Configuration two (With Wildcard Mask)

    R1(config)#router ospf 1
    R1(config-router)#network 192.168.23.0 0.0.0.255 area 1 
 
Behind 192.168.23.0 you can see it says 0.0.0.255. This is not a subnet mask but a wildcard mask. 

![two](https://user-images.githubusercontent.com/79013111/112277092-69f4a580-8ca7-11eb-9f8e-dbbd38245d07.png)

A wildcard mask is a reverse subnet mask. When I say reverse subnet mask I mean that the binary 1s and 0s of the wildcard mask are flipped compared to the subnet mask. A subnet mask of 255.255.255.0 is the same as wildcard mask 0.0.0.255. 

