# Virtual address space

Virtual address space is the separation between [Logical address space](Logical%20address%20space.md) and [Physical address space](Physical%20address%20space.md)

it allows [Address space](Address%20space.md) to be shared between several [Processes](Process.md)

## implementation

### Demand paging

we can bring [Pages](Concepts/Paging.md) into memory only when it is needed. It use a [pager](Concepts/Swapping.md) to do it.

If the page is already in the [Page table](Page%20table.md), that juste works normally. 
If the needed [page](Concepts/Paging.md) is not in the[Page table](Page%20table.md) :
- if [page](Concepts/Paging.md) on [Secondary storage](Secondary%20storage.md), load it into [frames](Concepts/Paging.md) in [Main memory](Main%20memory.md)
- if page is already in a [frames](Concepts/Paging.md) in [Main memory](Main%20memory.md), update [Page table](Page%20table.md) entry to point to frame

To know if the page is in memory or not, a [Page table](Page%20table.md) is associated to each [frame](Concepts/Paging.md) in the [Page table](Page%20table.md) :

- Valid $\rightarrow$ in memory
- Invalid $\rightarrow$ not in virtual address space

Initially valid–invalid bit is set to invalid on all entries

if a [Page table](Page%20table.md) in the [MMU](MMU.md) hit a frame with the invalid bit, it throw a [Page fault](Page%20fault.md)

![](attachments/Pasted%20image%2020230612135059.png)

### Demand segmentation

a
