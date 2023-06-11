# Kernel

> The one program present at all times on the computer (when operating) is the kernel

Everything else is either :

- A [System program](System%20program.md) or
- An [Application program](Application%20program.md)

The kernel is **Dual-mode** (for security), there is [User mode](Concepts/User%20mode.md) and [Kernel mode](Concepts/Kernel%20mode.md) that are distinguish by the **Mode bit** provided by the [CPU](CPU.md). When user code is running, mode bit is set on user. When kernel code is running, mode bit is set on kernel (privileged)

There is some instruction and memory that are designated as **privileged**. It can only be accessed when in [Kernel mode](Concepts/Kernel%20mode.md)

To switch from [User mode](Concepts/User%20mode.md) to [Kernel mode](Concepts/Kernel%20mode.md), the user program can make a [Trap](Interrupt.md) to ask the kernel to make something in [Kernel mode](Concepts/Kernel%20mode.md)

![](attachments/Pasted%20image%2020230611100245.png)