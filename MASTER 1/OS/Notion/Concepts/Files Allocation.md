# Files allocation

How [disk blocks](../Magnetic%20disks.md) are allocated for [files](../File.md)?

## Contiguous allocation

Each [File](../File.md) occupies a set of contiguous [blocks](../Magnetic%20disks.md) on the [disk](../Magnetic%20disks.md)

advantages :
- Simple, we only need the starting location (the block number) and de length (the number of block) to identifies a [File](../File.md)
- Random access

Disadvantages :
- Wasteful of space, can't do dynamic storage
- [File](../File.md) cannot grow (same reason)

![](attachments/Pasted%20image%2020230614141020.png)
An alternative of contiguous allocation is extent-based system. Extent-based system allocate disk blocks in **extents**. Extent is a contiguous block of [disks](../Magnetic%20disks.md). So, extents are allocated for [File](../File.md) allocation

## Linked allocation

Each [File](../File.md) is a linked list of disk [blocks](../Magnetic%20disks.md). [Blocks](../Magnetic%20disks.md) could be anywhere on the [disk](../Magnetic%20disks.md)

advantages :
- Simple, we just need a starting address
- No waste of space (just a little overhead)

Disadvantages :
- Not random access

![](attachments/Pasted%20image%2020230614142507.png)

We can add a **File-allocation-table (FAT)** that contains entries that correspond to each [cluster](../Magnetic%20disks.md)

![](attachments/Pasted%20image%2020230614142754.png)

## Indexed allocation

Use one [cluster](../Magnetic%20disks.md) (it become an index table) to give all addresses of all [clusters](../Magnetic%20disks.md) where the [file](../File.md) is stored

advantages :
- Random access

Disadvantages :
- Need index table
- Dynamic access without external fragmentation, but have overhead of index [block](../Magnetic%20disks.md).

![](attachments/Pasted%20image%2020230614143504.png)