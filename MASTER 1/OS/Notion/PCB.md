# Process Control Block (PCB)

A PCB contains all information associated with a [Process](Process.md) (is located in the [Kernel](Kernel.md))

It is composed of :

- Process state (running, waiting, ...)
- Process ID (**pid**)
- Program counter
- CPU registers : copy of contents of all register of the process
- [CPU scheduling](Concepts/CPU%20scheduling.md) information
- Memory management information : memory allocated to the process
- Accounting information : CPU used, clock time elapsed since start, ...
- [I/O](I%20O%20devices.md) status information : [I/O devices](I%20O%20devices.md) allocated to process, list of open files

![](attachments/Pasted%20image%2020230611140617.png)