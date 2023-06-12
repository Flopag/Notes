# Translation look-aside buffers (TLB) or associative memory

TLB permit to make less [Paging](Concepts/Paging.md) operations to access a data/instruction that just using a [Page table](Page%20table.md). It is a sort of [Cache](Concepts/Caching.md) for the [Page table](Page%20table.md)

![](attachments/Pasted%20image%2020230612102835.png)

TLB take a [Logical address](Logical%20address%20space.md) and look if it has a [Physical address](Physical%20address%20space.md) associated with. If yes, it forward the [Logical address](Logical%20address%20space.md) directly to the [Physical address space](Physical%20address%20space.md). If not, it will forward the [Logical address](Logical%20address%20space.md) to the [Page table](Page%20table.md) and save the result 

![](attachments/Pasted%20image%2020230612103246.png)

Some TLBs store **address-space identifiers (ASID)** in each TLB entry. ASID uniquely identifies each [Process](Process.md) to provide [Address space](Address%20space.md) protection for that [Process](Process.md)

**Effective acces Time (EAT)** $=$ hit ratio $\times$ hit access memory time $+$ miss ratio $\times$ miss access memory time