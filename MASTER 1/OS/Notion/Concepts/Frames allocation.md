# Frames allocation

Fixed allocation :
- Equal allocation : each [Process](../Process.md) gets the same amount of [frame](Paging.md)
- Proportional allocation : each [Process](../Process.md) gets an amount of [frame](Paging.md) propositional to its size

## Buddy system allocation

[Main memory](../Main%20memory.md) is allocated using power-of-2 size

Satisfies requests in units sized as power of 2

Request rounded up to next highest power of 2

When smaller allocation needed than is available, current chunk split into two buddies of next-lower power of 2

![](attachments/Pasted%20image%2020230612163913.png)

## Slap allocation (used by malloc)

A slab is one or more [frames](Paging.md). a slab can be filled with multiple object (exemple : structure, etc)

A cache consists of one or more slabs

when a slab is created, it is mark as free

When an object is stored in a slab, it is mark as used

if there is no empty slap, creation of new empty slab

![](attachments/Pasted%20image%2020230612164917.png)