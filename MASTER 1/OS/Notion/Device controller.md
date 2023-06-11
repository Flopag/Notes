# Device controller

A device controller controls a particular type of [I/O devices](I%20O%20devices.md) and has an [Operating system](Operating%20system.md) device driver to manage it

**Device controller informs the [CPU](CPU.md) that it has finished an operation by causing an [Interrupt](Interrupt.md)**

A device controller can transfers blocks of data to/from its buffer storage directly to the [Main memory](Main%20memory.md) without [CPU](CPU.md) intervention. So, it can send an [Interrupt](Interrupt.md) with the address to [Main memory](Main%20memory.md) where it has written something (more efficient that sending multiple [Interrupt](Interrupt.md))




