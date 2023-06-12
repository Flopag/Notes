# Contiguous allocation (an old method)

Main memory is segmented in two part :

- Operating system in privileged memory (low [Physical memory](../Physical%20address%20space.md)) 
- User [Processes](../Process.md) in non privileged memory (higher [Physical memory](../Physical%20address%20space.md))

Each process is contained in a single section of the memory (in one piece). To do it, [MMU](../MMU.md) uses two registers for each [Processes](../Process.md) to avoid them to write outside their memory :

- Realocation register : contains the value of the smallest [Physical address](../Physical%20address%20space.md) (beginning of the [Process](../Process.md) [Address space](../Address%20space.md))
- Limit register : contains the size of the [Process](../Process.md) [Address space](../Address%20space.md)

The MMU verifies if the given [Logical address](../Logical%20address%20space.md) is smaller than the limit register if not trap, if yes, transform this [Logical address](../Logical%20address%20space.md) to a [Physical address](../Physical%20address%20space.md) by adding the value of the realocation register 

![](attachments/Pasted%20image%2020230612090728.png)