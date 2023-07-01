# Data plane

Data plane is part of a [Router](Router.md) that forwards packets where the [RIB](RIB.md) says to :

1. Get the longest prefix in the table that matches the packet destination IP address
2. Forward the packet to the output interface associated to the prefix

![](attachments/Pasted%20image%2020230617090847.png)