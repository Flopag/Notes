# InterProcess Communication (IPC)

There is two kind of communication between [processes](../Process.md) :

![](attachments/Pasted%20image%2020230611150442.png)

## Shared memory

An area of memory shared among the [processes](../Process.md) that wish to communicate. This communication is under the control of the users [processes](../Process.md) and not the [Operating system](../Operating%20system.md)

it can be done by give a copy of the address space from fork

The major issues is concurrency (see parallel programming course) 

## Message passing

[Processes](../Process.md) does not share them memory but communicate trough a **communication link** (though the [Kernel](../Kernel.md))

Message passing can be :

- **Blocking** : sender/receiver is blocked until the message is received/available (if both, sender and receiver are blocking, it is called a **rendezvous**)
- **Non-blocking** : sender/receiver sends/receiver the message and continue (the receiver receives NULL if there is no message)

**Direct communication** are made automatically between two [Processes](../Process.md). It communicate tanks to :

- `send(P, message)` : send a message to [Process](../Process.md) P
- `receive(Q, message)` : receive a message from [Process](../Process.md) Q

**Indirect communication** is using a **mail box** as intermediate. Each mailbox has a unique id. [Processes](../Process.md) can communicate only if they share a mailbox. Operations are :

- Create a new mailbox
- Delete a mailbox
- `send(A, message)` : send a message to mailbox A
- `receive(A, message` : receive a message from mailbox A

If a mailbox received a message to share, who gets the message? :

- Allow a link to be associated with at most two processes
- Allow only one process at a time to execute a receive operation
- Allow the system to select arbitrarily the receiver. Sender is notified who the receiver was.