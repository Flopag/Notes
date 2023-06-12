# Multiple allocation

The [Physical address space](../Physical%20address%20space.md) size is limited, so, we need a way to minimise the free space. To do it, we define some concepts :

- **Variable block** : [Address space](../Address%20space.md) of a [Process](../Process.md) that can be variable given its needs
- **Hole** : variable block that contains free space (multiple adjacent hole congratenates)

When a [Process](../Process.md) arrives, it is allocated memory from a hole large enough to accommodate it. When a [Process](../Process.md) exiting, it frees its memory (its block) and it become a hole

![](attachments/Pasted%20image%2020230612092030.png)

How to find a hole big enough to fit a new block size allocation ?

- **First-fit** : Allocate the first hole that is big enough
- **Best-fit** : Allocate the smallest hole that is big enough (produce the smallest leftover hole)
- **Worst-fit** : Allocate the largest hole (produces the largest leftover hole)

These methods can lead to [Fragmentation](Fragmentation.md). To avoid this, we can use [multiple fixed sized block](Paging.md) instead of uniques fixed sized blocks