# Autonomous System (AS)

AS is a collection of routers and end-hosts under a common administrative control

There is tree types of business relationships between AS :

- Provider : you pay them to transit your traffic
- Peer : unpaid exchange of traffic
- Customer : they pay you to transit their traffic

Each AS is identified by an AS number

All router in an AS all run the same routing algorithm (intra-AS routing protocol) :

- OSPF, IS-IS
- RIP

AS are connected between them through [ASBR](Router.md). It use inter-AS routing protocol :

- [BGP](BGP.md)

![](attachments/Pasted%20image%2020230617090152.png)