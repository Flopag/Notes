# Page fault

A page fault is an [Interrupt](Interrupt.md) that is trowed by the [MMU](MMU.md) when a [Page fault](Page%20fault.md) hits an invalid [frame](Concepts/Paging.md)

There is two types of page fault :

- Hard page fault : the [page](Concepts/Paging.md) is not in the [Main memory](Main%20memory.md)
- Sorf page fault : the [page](Concepts/Paging.md) is already in the [Main memory](Main%20memory.md)

if the page is shared, use of [COW](Concepts/COW.md)

## Handling hard page fault

1. If there is a reference to a [page](Concepts/Paging.md), first reference to that [page](Concepts/Paging.md) will [trap](Interrupt.md) to [Operating system](Operating%20system.md)
2. [Operating system](Operating%20system.md) looks at another table to decide :
	- has an invalid reference = abort
	- is not in [Virtual address space](Virtual%20address%20space.md) yet and its [page](Concepts/Paging.md) is not in the [Main memory](Main%20memory.md)
3. Find free [frame](Concepts/Paging.md)
	- It can be done thanks to a **free [frame](Concepts/Paging.md)** that is a pool of free [frames](Concepts/Paging.md) that the [Operating system](Operating%20system.md) fill with all free [frames](Concepts/Paging.md) available 
	- If there is no free [frames](Concepts/Paging.md), [search a frames that is not use and replace it](Concepts/Page%20replacement.md).
1. [Swap](Concepts/Swapping.md) the wanted [page](Concepts/Paging.md) into the free [frame](Concepts/Paging.md) via [Scheduler disk operation](Concepts/Scheduler%20disk%20operation.md)
2. Reset [Page table](Page%20table.md) to indicate [page](Concepts/Paging.md) now in [Main memory](Main%20memory.md) and set [validation bit](Virtual%20address%20space.md) to valide
3. Restart the instruction that caused the page fault

## Handling soft page fault

1. If there is a reference to a [page](Concepts/Paging.md), first reference to that [page](Concepts/Paging.md) will [trap](Interrupt.md) to [Operating system](Operating%20system.md)
2. [Operating system](Operating%20system.md) looks at another table to decide :
	- has an invalid reference = abort
	- is not in [Virtual address space](Virtual%20address%20space.md) yet and its [page](Concepts/Paging.md) is already in the [Main memory](Main%20memory.md)
3. Reset [Page table](Page%20table.md) to indicate [page](Concepts/Paging.md) now in [Main memory](Main%20memory.md) and set [validation bit](Virtual%20address%20space.md) to valide
4. Restart the instruction that caused the page fault

![](attachments/Pasted%20image%2020230612140645.png)