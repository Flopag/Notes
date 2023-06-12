# Loader

A loader execute, by bringing into memory, what the [Linker](Linker.md) has done 

![](attachments/Pasted%20image%2020230611111748.png)

## Dynamic loading

The entire program does not need to be in memory to execute, routine is not loaded until it is called. So, unused routine are never loaded (better memory-space utilisation)