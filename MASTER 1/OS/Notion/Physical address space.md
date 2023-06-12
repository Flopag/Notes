# Physical address space

Physical address space are the addresses seen by the memory unity (the true memory, can be RAM)

putting a program to physical address space takes some steps :

- Compile time : usually binds symbolic addresses into object module address space
- [Link time](Linker.md) : maps object module address spaces in [Logical address space](Logical%20address%20space.md)
- [Load time](Loader.md) : maps system lib, DLLs, heap, stack, etc into [Logical address space](Logical%20address%20space.md)
- Execution time : mapping to physical address delayed until use