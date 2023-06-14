# File system

system that handle [Files](File.md) and [Directory](Directory.md) on [disk](Magnetic%20disks.md) or [partitions](Magnetic%20disks.md)

![](attachments/Pasted%20image%2020230614100057.png)
## File Sharing

Sharing can be done through a protection scheme. If the system is used by multiple users, the system needs :

- User IDs to identify users. Permit to manage permission among users
- Group IDs to identify groups of users. Do the same as User IDs but permit to manage multiple users at a time
- Owner of a [File](File.md)/[Directory](Directory.md)

Protection is controlled by the owner. It can be done with a access mode that say if :

- Can read
- Can write
- Can execute

## File system structure

File system is located in [Secondary storage](Secondary%20storage.md) on [disks](Magnetic%20disks.md) and is organised into layers :

- Application programs $\rightarrow$ Logical file system $\rightarrow$ File-organisation module $\rightarrow$ basic file system $\rightarrow$ I/O control $\rightarrow$ devices


**File control block** is a storage structure that contains information about a [file](File.md). A typical file control block contains :

- File permissions
- File dates
- File owner, group, ACL
- File size
- File data blocks or pointers to file data blocks

![](attachments/Pasted%20image%2020230614120149.png)
![](attachments/Pasted%20image%2020230614120200.png)

## Virtual file system (VFS)

VFS provide an object-oriented way of implementing file systems. It allows the same  [System call](System%20call.md) [interface](API.md) to be used for different type of file systems

![](attachments/Pasted%20image%2020230614120451.png)

## Log structured file systems

Log structured (or journaling) file systems record each update to the file system as a transaction. All transaction are written to a **log**. 

A transaction is considered committed once it is written to the log even if  the file system lay not yet be updated

The transactions in the log are asynchronously written to the file system. When the file system is modified, the transaction is removed from the log

So, if the file system crashes, all remaining transactions in the log must still be performed

## Files allocation

see [Files Allocation](Concepts/Files%20Allocation.md)

## Free space management

Two way to do it :

- Using a bit vector of size $i$, $i$ is the number of [block](Magnetic%20disks.md) on [disk](Magnetic%20disks.md). `Vector(i) = 1` if the [block](Magnetic%20disks.md) $i$ is free, other while,  `Vector(i) = 0` if the [block](Magnetic%20disks.md) $i$ is occupied
	- require extra space but permit to get contiguous space easily
- Using a linked list with all free [blocs](Magnetic%20disks.md) on [disk](Magnetic%20disks.md)
	- Don't requires extra space but can not get contiguous space easily

![](attachments/Pasted%20image%2020230614145156.png)