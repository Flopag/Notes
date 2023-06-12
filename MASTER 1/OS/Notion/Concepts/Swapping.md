# Swapping

swapping into **swap space** : Use of [Secondary storage](../Secondary%20storage.md) (bigger than [Main memory](../Main%20memory.md)) where we keep copies of [Processes](../Process.md) that have been swapped out (go from [Main memory](../Main%20memory.md) to [Secondary storage](../Secondary%20storage.md))

A [Process](../Process.md) can be swapped temporarily out of memory to a [backing store](../Secondary%20storage.md), and then brought back into [Main memory](../Main%20memory.md) for continued execution

Swapping can use priority to know which [Process](../Process.md) must be swapped out (Roll out, roll in)

**Lazy swapper** (or pager) never swaps a [page](Paging.md) into [Main memory](../Main%20memory.md) unless [page](Paging.md) will be needed

Swapping is normally disable, it is started when the memory allocated is above a threshold and it is disabled when it is under

![](attachments/Pasted%20image%2020230612111701.png)

![](attachments/Pasted%20image%2020230612111831.png)