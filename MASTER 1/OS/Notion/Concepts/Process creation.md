# Process creation

Parent process creates children processes, which, in turn create other processes, forming a tree of processes

![](attachments/Pasted%20image%2020230611143814.png)

Resource sharing options:

- Parent and children share **all** resources
- Children share **subset** of parent’s resources
- Parent and child share **no** resources

Execution options :

- Parent and children execute concurrently
- Parent waits until children terminate

[Address space](../Address%20space.md) options :

- Child duplicate of parent
- Child has a program loaded into it

Example in UNIX :

- `fork()` clone the caller into a new [Process](../Process.md)
- `exec()` replace the [Process](../Process.md) memory space with a new program
- `wait()` waiting for the child to [terminate](Process%20termination.md)

![](attachments/Pasted%20image%2020230611144232.png)