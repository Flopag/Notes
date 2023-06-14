# Magnetic disks

Magnetic disks provide big [Secondary storage](Secondary%20storage.md). It is attached to computer via [I/O bus](I%20O%20devices.md) and communicate to the [host controller](Interrupt%20handler.md) in the computer trough a [disk controller](Device%20controller.md) (all connected by [FC](FC.md) or [SCSI](SCSI.md)). [HDD](HDD.md) uses magnetic disks

magnetic disks are characterised by :

- **Rotation speed** (at 60 to 250 times per second)
- **Transfer rate** : rate at which data flow between drive and computer
- **Positioning time** (random-access time) : time to move disk arm to desired cylinder (**seek time**) and time for desired sector to rotate under the disk head (**rotational latency**)

![](attachments/Pasted%20image%2020230613171639.png)

## Disk structure

Disk drives are addressed as large 1-dimensional arrays of **logical blocks**, where the logical block is the smallest unit of transfer. The 1-dimensional array of logical blocks is mapped into the **sectors** of the disk sequentially. 

Disk **bandwidth** is the total number of bytes transferred, divided by the total time between the first request for service and the completion of the last transfer

Disk or partition can be used without [File system](File%20system.md) (**raw**) or with a [File system](File%20system.md) (**formatted**). Entity containing [file system](File%20system.md) is known as a **volume**. These volume tracks, each, their [File system](File%20system.md) info in **device [directory](Directory.md)** or **volume table of contents**

## Disk scheduling

see [Disk scheduling](Concepts/Disk%20scheduling.md)

## Disk management

**Low-level formatting** (or physical formatting) is dividing a disk into fixed sized sectors that [disk controller](Device%20controller.md) can read and write. Each sector can hold : 

- Header information
- Data
- Error correction code (ECC)

To use a disk to hold [Files](File.md), the [Operating system](Operating%20system.md) still needs to record its own data structures on the disk. So, it makes **partition** on the disk. A partition is a group of one or more cylinders, each treated as a logical disk 

**Logical formatting** is grouping sectors into clusters to  increase efficiency 

In conclusion :

- Disk [I/O](I%20O%20devices.md) is done with blocks
- [File](File.md) [I/O](I%20O%20devices.md) is done with clusters

To initialise the system, there is some boot blocks in a boot partition that contain the **bootstrap loader** program

![](attachments/Pasted%20image%2020230613210204.png)