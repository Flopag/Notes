# System call

A system call is a fonction of the [Kernel](Kernel.md) that can be called from [User mode](Concepts/User%20mode.md). that provide an [API](API.md) to the [Operating system](Operating%20system.md)

It is often accessed by using high-level [API](API.md) as malloc, or else

A number is associated with each system call that are stored in a table that link the number with a pointer pointing to the beginning of the system-call code

![](attachments/Pasted%20image%2020230611110156.png)

Three methods is used to pass parameters of the syscall to the [Operating system](Operating%20system.md) :

- pass the parameters in registers (but sometimes, more parameters than registers)
- Parameters stored in a block, or table, in memory, and address of block passed as a parameter in a register
- Parameters placed, or pushed, onto the stack by the program and popped off the stack by the operating system

Parameter passing via table :

![](attachments/Pasted%20image%2020230611110414.png)