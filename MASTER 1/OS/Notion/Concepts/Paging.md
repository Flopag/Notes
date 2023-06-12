# Paging

The concept is to used multiple fixed sized block instead of uniques [fixed sized blocks](Multiple%20allocation.md) (this is [Multiple allocation](Multiple%20allocation.md) but made in a better way). 

[Physical address space](../Physical%20address%20space.md) is divided into fixes-sized blocks called **frames**

[Logical address space](../Logical%20address%20space.md) is divided into fixed-sized blocks called **pages**

Pages and frames are on the same fixed-size

There is still [internal fragmentation](Fragmentation.md) (if needed space is not a multiple of the pages size)!

To translate [Logical address space](../Logical%20address%20space.md) into [Physical address space](../Physical%20address%20space.md), [Page table](../Page%20table.md) is used. In this scheme every data/instruction access requires two memory accesses (one for the page table and one for the data/instruction). This problem can be solve using [TLB](../TLB.md)

![](attachments/Pasted%20image%2020230612100129.png)

Pages can be shared between multiple [Processes](../Process.md). So pages can also be private

![](attachments/Pasted%20image%2020230612105055.png)