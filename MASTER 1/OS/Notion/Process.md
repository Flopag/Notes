# Process

A process (active entity) is the [Operating system](Operating%20system.md) representation of a program (passive entity). A program become a process when an [executable](Linker.md) file is [loaded](Loader.md) into  [memory](Main%20memory.md)

Process in memory :

![](attachments/Pasted%20image%2020230611135304.png)

Process execution progresses in sequential (for single [Thread](Thread.md))

One program can be several processes (exemple : chrome). These processes are **cooperating**, they communicates with [IPC](Concepts/IPC.md). this communication permit to : share informations, speedup, modularity and convenience

All information associated with a process is stored in a [PCB](PCB.md)

A process can be in five state :

- New : The process is being created
- Running : Instructions are being executed
- Waiting : The process is waiting for some event to occur
- Ready : The process is waiting to be assigned to a processor
- Terminated : The process has finished execution

![](attachments/Pasted%20image%2020230611135619.png)

