# Multicore

Multicore is the concept of using multiple core (processor) of the [CPU](../CPU.md) for a signle [Process](../Process.md) using [Thread](../Thread.md)

Parallelism implies a system has resources perform more than one task simultaneously. There is two types of parallelism :

- Data parallelism : distributes subsets of the same data across multiple cores, same operation on each
- Task parallelism : distributing [Threads](../Thread.md) across cores, each thread performing unique operation

![](attachments/Pasted%20image%2020230611165925.png)