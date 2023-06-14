# File

Files are contiguous [Logical address space](Logical%20address%20space.md). There is two types of files :

- Data files :
	- numeric
	- character
	- binar
- Program files

There are three file structure types (the type to use is decide by the user or the [Operating system](Operating%20system.md)) :

- No structure : juste sequence of bytes
- Simple record structure : lines with fixed/variable length
- Complex structure : formatted document, relocatable load file

Files attributes :

- **Name** : the only information that is in human-readable form
- **Identifier** : an unique tag that identifies the file within the [File system](File%20system.md)
- **Type** (extension) : is needed for systems that support different types of file
- **Location** : a pointer to the file location on the device
- **Protection** : says who can read, write and execute the file
- **Time, date and user identification** : are data for protection, security and usage monitoring

Files operations :

- **Create**
- **Write** (to write pointer location)
- **Read** (to read pointer location)
- **Reposition** within file ([seek](Magnetic%20disks.md))
- **Delete**
- **Truncate**
- $\mathbf{Open(F_I)} \rightarrow$ search in the [directory structure](Directory.md) on [disk](Magnetic%20disks.md) for the entry $F_i$ and move the content of the entry to [Main memory](Main%20memory.md)
- $\mathbf{Close(F_i)} \rightarrow$ move the content of the entry $F_i$ in [memory](Main%20memory.md) to the [directory structure](Directory.md) on [disk](Magnetic%20disks.md)

## More information about opening a file

To open a file, we need :

- An **open-file table** to tracks all open files
- The **File-open count** that count the number of time a file is open. it is used to know if there is a [Process](Process.md) that is using it
- The disk location of the file
- The, per-[Process](Process.md), access rights (protection of the file)

For protection, [File system](File%20system.md) can provide locking. There is two type of locks :

- **Shared lock** : several [processes](Process.md) can acquire it, concurrently
- **Exclusive lock** : only one [process](Process.md) can acquire it 

These locks can be **mandatory** (access is strict) or **advisory** ([processes](Process.md) know that there is a lock but it does what it want)

## Access file Methods

![](attachments/Pasted%20image%2020230614094014.png)

Sequential access (no read after last write) :

```
read next
write next
reset
```

Direct Access (file is fixed length) :

```
n = relative block number

read n
write n
position to n
	read next
	write next
rewrite n
```

Other methods use **index** for the file. The index is kept in memory for fast determination of location of data to be operated on

![](attachments/Pasted%20image%2020230614094852.png)