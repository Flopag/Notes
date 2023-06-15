# Virtualisation

Virtualisation is a way to run multiple [Operating system](../Operating%20system.md) instances (isolated from each other) on the same hardware. Each instance has independent "root" and "system view"

There is three types of virtualisation :

- Emulation
- Container-based virtualisation
- System virtualisation

## Emulation

Simply emulate the computer and the OS

Advantages :
- Simple to make

Disadvantages :
- Very slow

## Container-based OS Virtualisation

Each virtual environment (VE) is seen by the [Kernel](../Kernel.md) as a group of [processes](../Process.md)

Kernel needs to supper duplicate resources (as root directory and multiple [Process](../Process.md) trees)

So, the host see the init [Process](../Process.md) of a VE as a simple process in its [Process](../Process.md) tree and the root of a VE as a simple folder

Network virtualisation is made by virtual interface (as software ethernet switches)

Advantages :
- Fast
- lightweight

Disadvantages :
- All VE must be with the same [Kernel](../Kernel.md) (but can have different distribution, for example : ubuntu debian)

![](attachments/Pasted%20image%2020230612210346.png)

## System virtualisation

Gives a virtual view of the hardware to the VMs

![](attachments/Pasted%20image%2020230612210448.png)

In system virtualisation, [Kernel mode](Kernel%20mode.md) is no more a privilege mode, the hypervisor takes this permission :

![](attachments/Pasted%20image%2020230612210747.png)

When a VM [Kernel](../Kernel.md) want to make a privilege operation, it send a [trap](../Interrupt.md) to the hypervisor and the [Interrupt handler](../Interrupt%20handler.md) of the hypervisor will do it in privilege mode.

Advantages :
- Easy if all instruction that modify resource configuration are privileged (because hypervisor will then have control to sensitive instruction)

Disadvantages :
- On x86, not all control sensitive instruction are privileged (these will not [trap](../Interrupt.md)) so VMs could change some system configuration at will
- The guest [Operating system](../Operating%20system.md) runs in a [Virtual address space](../Virtual%20address%20space.md) is set up by the hypervisor. So, [Physical address space](../Physical%20address%20space.md)  of these VM are [Virtual address space](../Virtual%20address%20space.md). The mapping is managed by  the hypervisor

### System virtualisation, Binary rewriting

To avoid privileged issues, privileged instruction and jumps (needs to scan target location) are emulated

When these instruction are execute, their are replaced by other one thanks to breakpoint registers

![](attachments/Pasted%20image%2020230612214455.png)

Advantages :
- No hardware support required
- Runs original code

Disadvantages :
- Permormance penalty (but better than emulation)
- Require on-the-fly x86-to-x86 binary compile (to execute breakpoints)

### System virtualisation : paravirtualisation

Ignore issues with non-privileged instructions, let the guest [Operating system](../Operating%20system.md) deal with them

Hypervisor exposes a set of hypercalls (similar to [System call](../System%20call.md) but for hypervisor)

same principle as binary rewriting but instruction replacement happens at compile-time

![](attachments/Pasted%20image%2020230612215244.png)

Advantages :
- No hardware support required
- Performance

Disadvantages :
- Require to modify guest [Kernel](../Kernel.md)

### Two types of hypervisors

![](attachments/Pasted%20image%2020230612215751.png)

Advantages of hosted :
- Avoid code duplication: scheduler, [Virtual address memory](../Virtual%20address%20space.md), drivers, etc already in host [Operating system](../Operating%20system.md)

Disadvantages of hosted :
- Hypervisor has less control on performance