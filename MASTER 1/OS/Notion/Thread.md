# Thread

A thread is a way to execute a single process with multiple program counter. Threads share address the address space of the [Process](Process.md) except the stack and thread-local memory

Single vs multithreaded [Processes](Process.md) :

![](attachments/Pasted%20image%2020230611165006.png)

Benefits of Multithread :

- Responsiveness : may allow continued execution if part of process is blocked, especially important for user interfaces
- Resource sharing : threads share resources of process, easier than [shared memory](Concepts/IPC.md) or [message passing](Concepts/IPC.md)
- Economy : cheaper than [Process](Process.md) creation, thread switching lower overhead than [Context switch](Concepts/Context%20switch.md)
- Scalability : [Process](Process.md) can take advantage of [Multicore](Concepts/Multicore.md) architectures

Thread has some issues :

- Does `fork()` duplicate only the calling thread or all? (`exec()` works as normal, it replace entirely the running [Process](Process.md))
- **Signals** are used to notify a [Process](Process.md) that a particular event has occurred. A **signal handler** is used to process these signals. There is a default signal handler inside the [Kernel](Kernel.md) (user-defined signal handler can override the default one)
	- Where should a signal be delivered for Multithread?
- Thread can be terminated before it has finished (it is called **target thread**). There is two approaches to do it :
	- Asynchronous cancellation : immediate termination
	- Deferred cancellation : say to the target thread that we want it to terminate (it periodically check if we ask it)

There is two types of threads :

- **User threads** : management done by user-level threads library (in the [User space](Concepts/User%20mode.md))
	- **Thread library** provides programmer with [API](API.md) for creating and managing threads (can be in [Kernel](Concepts/Kernel%20mode.md) or [User](Concepts/User%20mode.md) space)
- **Kernel threads** : Supported by the [Kernel](Kernel.md) (in the [Kernel space](Concepts/Kernel%20mode.md))

User and kernel threads must be linked. That can be done by :

- Many to One

![](attachments/Pasted%20image%2020230611170814.png)

- One to One

![](attachments/Pasted%20image%2020230611170825.png)

- Many to Many

![](attachments/Pasted%20image%2020230611170834.png)
