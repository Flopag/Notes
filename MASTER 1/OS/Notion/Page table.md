# Page table

A page table translate [Logical address space](Logical%20address%20space.md) into [Physical address space](Physical%20address%20space.md) using [Paging](Concepts/Paging.md) (see picture to know how). It is located in the [Main memory](Main%20memory.md). Two register permit to locate it :

- **Page-table base register (PTBR)** : register that points to the page table
- **Page-table length register (PTLR)** : register that indicate the size of the page table

![](attachments/Pasted%20image%2020230612095619.png)

![](attachments/Pasted%20image%2020230612095812.png)

![](attachments/Pasted%20image%2020230612095845.png)

Memory protection implemented by associating protection bit with each [frame](Concepts/Paging.md) to indicate if read-only or read-write access is allowed. To do so, **Valid-invalid** bit are attached to each entry :

- Valid indicates that the associated [page](Concepts/Paging.md) is in the [Process](Process.md)’ [Logical address space](Logical%20address%20space.md), and is thus a legal page
- invalid indicates that the [page](Concepts/Paging.md) is not in the [Process](Process.md)' [Logical address space](Logical%20address%20space.md)

![](attachments/Pasted%20image%2020230612104548.png)

## Structure of a page table

Page table can be very big, to avoid it, we can divide it into smaller tables. The is different methods to do it :

### Hierarchical paging

Break up the [Logical address space](Logical%20address%20space.md) into multiple page tables (using two-level table)

![](attachments/Pasted%20image%2020230612105443.png)

![](attachments/Pasted%20image%2020230612105646.png)

### Hashed page tables

The virtual page number is hashed into a page table. This page table contains a chain of elements hashed to the same location. Each element contains :

- the virtual page number
- the value of the mapped page frame
- a pointer to the next element

To find the right [Physical address](Physical%20address%20space.md), Virtual page numbers are compared in this chain searching for a match

![](attachments/Pasted%20image%2020230612110051.png)

### Inverted page table

instead of having each [Process](Process.md) page in the page table, the page table will store each frames of the [Physical address space](Physical%20address%20space.md) and the corresponding [pid](PCB.md) of the [Process](Process.md). Explanations in the following image :

![](attachments/Pasted%20image%2020230612110915.png)