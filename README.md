# OSPF---Open-Shortest-Path-First

![unnamed](https://user-images.githubusercontent.com/79013111/112276117-5a289180-8ca6-11eb-9e1b-d78a1cd4390d.png)

The OSPF protocol is a link-state routing protocol, which means that the routers exchange topology information with their nearest neighbors. The topology information is flooded throughout the AS, so that every router within the AS has a complete picture of the topology of the AS. This picture is then used to calculate end-to-end paths through the AS, normally using a variant of the Dijkstra algorithm. Therefore, in a link-state routing protocol, the next hop address to which data is forwarded is determined by choosing the best end-to-end path to the eventual destination.
