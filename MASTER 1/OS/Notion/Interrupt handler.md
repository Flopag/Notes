# Interrupt handler

The interrupt handler is a program part of the [Operating system](Operating%20system.md) that contains all code needed to handle [Interrupt](Interrupt.md). 

A segments of its code determine what action should be taken for each type of [Interrupt](Interrupt.md) using a interrupt vector that contains pointers to the right the code to use

One interrupt handler per [Operating system](Operating%20system.md). Handling an [Interrupt](Interrupt.md) disables other futur [Interrupt](Interrupt.md) in the time it process the current one

