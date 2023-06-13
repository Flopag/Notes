# Disk scheduling

The [Operating system](../Operating%20system.md) is responsible for using hardware efficiently. For the [disk drives](../Magnetic%20disks.md), this means having a fast access time and disk bandwidth. So, the [Operating system](../Operating%20system.md) must minimise [seek time](../Magnetic%20disks.md) ($\simeq$ [seek distance](../Magnetic%20disks.md))

An I/O request includes :

- input or output mode
- disk address
- memory address
- number of sectors to transfer

[Operating system](../Operating%20system.md) maintains queue of request (per [disk](../Magnetic%20disks.md) or [device](../I%20O%20devices.md)). The queue is working when the [disk](../Magnetic%20disks.md) is busy, other-while, the queue don't need to working when the [disk](../Magnetic%20disks.md) can immediately handle [I/O request](../I%20O%20devices.md) (if it does nothing) 

_(for the exemples, the request queue is "98,183,37,122,14,124,65,67" and the head pointer start at 53)_

## First-Come, First-Served (FCFC) algorithm

![](attachments/Pasted%20image%2020230613181811.png)

## Shortest Seek Time First (SSTF) algorithm

SSTF selects the request with the minimum seek time from the current head position

![](attachments/Pasted%20image%2020230613181942.png)

## SCAN (or elevator) algorithm

The [disk](../Magnetic%20disks.md) arm starts at one end of the [disk](../Magnetic%20disks.md), and moves toward the other end, servicing requests until it gets to the other end of the [disk](../Magnetic%20disks.md), where the head movement is reversed and servicing continues

![](attachments/Pasted%20image%2020230613182129.png)

## C-SCAN algorithm

The head moves from one end of the [disk](../Magnetic%20disks.md) to the other, servicing requests as it goes. When it reaches the other end, however, it immediately returns to the beginning of the [disk](../Magnetic%20disks.md), without servicing any requests on the return trip

![](attachments/Pasted%20image%2020230613182409.png)

## C-LOOK algorithm

Arm only goes as far as the last request in each direction, then reverses direction immediately, without first going all the way to the end of the [disk](../Magnetic%20disks.md)

![](attachments/Pasted%20image%2020230613182422.png)