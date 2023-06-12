internal fragmentation# Fragmentation

There is two type of fragmentations :

- **External fragmentation** : There is enough free space in memory but there is no [hole](Multiple%20allocation.md) big enough to fit the [block](Multiple%20allocation.md)
- **Internal Fragmentation** : The [allocate](Multiple%20allocation.md) space is bigger than the needed space that leads to unused memory

There is three ways to reduce external fragmentation :

- By **compaction** : Shuffle memory contents to place all free memory together in one large [hole](Multiple%20allocation.md) (leads to [I/O](../I%20O%20devices.md) problems)
- by [Swapping](Swapping.md)
- [Paging](Paging.md)