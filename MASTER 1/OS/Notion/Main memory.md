# Main memory

The main memory is the only one large storage that the [CPU](CPU.md) can access **directly**. It is random access and volatile (made of RAM and other fast random access memory)

## Non Uniforme Memory  Access (NUMA)

Speed of access to memory varies. So, the optimal performance comes from [allocating](Concepts/Frames%20allocation.md) memory close to the [CPU](CPU.md) on which the [Thread](Thread.md) is [scheduled](Process%20scheduler.md)

![](attachments/Pasted%20image%2020230612153420.png)