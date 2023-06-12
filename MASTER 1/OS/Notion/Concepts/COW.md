# Copy-on-Write (COW)

COW allows both parent and child [processes](../Process.md) to initially share the same [frames](Paging.md) in [Main memory](../Main%20memory.md). If a [Process](../Process.md) (parent or child) want to modifies a shared [page](Paging.md), this will copy this [page](Paging.md) and be no more a shared [page](Paging.md)

![](attachments/Pasted%20image%2020230612142533.png)