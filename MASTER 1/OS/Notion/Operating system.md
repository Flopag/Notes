# Operating system

An operating system is a software that acts as an intermediary between user programs and the computer hardware

In this class, the operating system is the [Kernel](Kernel.md)

OS generally distinguish users to determine who can do what tanks to :

- User IDs (name and number) permit to set the owner of a file/process
- Group ID permit to have multiple users for one file/process
- Privilege escalation permit too give privileges to users

## Operating System Structure

#### Monolithic Structure

The structure is divided by two separable parts :

- All [System program](System%20program.md)
- The [Kernel](Kernel.md)

![](attachments/Pasted%20image%2020230611112527.png)

#### Layered Approach

The operating system is divided into a number of layers (levels), each built on top of lower layers. The bottom layer (layer 0), is the hardware; the highest (layer N) is the user interface. Layers can only interact with layer around them

![](attachments/Pasted%20image%2020230611112714.png)

#### Microkernel System Structure

Microkernel is composed of many little [Kernel](Kernel.md) that communicates with message passing

It can use [LKM](LKM.md) to do it

![](attachments/Pasted%20image%2020230611112901.png)

#### Hybrid Systems

Hybrid systems is a composition of all others structures

Exemples :

- Linux is monolithic and modular (microkernel)
- Windows is monolithic and microkernel