# Dispacher

Dispatcher module gives control of the [CPU](CPU.md) to the [Process](Process.md) selected by the [CPU scheduler](CPU%20scheduler.md)

It does it work thanks to :

- [Context switch](Concepts/Context%20switch.md)
- Switch to [User mode](Concepts/User%20mode.md)
- Jumping to the proper location in the [user program](Concepts/User%20mode.md) to restart that program

**Dispatch latency** is time it takes for the dispatcher to stop one [Process](Process.md) and start another running

![](attachments/Pasted%20image%2020230613144450.png)