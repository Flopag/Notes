# Page replacement

There is two types of replacement :

- **Global replacement** : [Process](../Process.md) selects a replacement [frame](Paging.md) from the set of all [frames](Paging.md). So, one [Process](../Process.md) can take a [frame](Paging.md) from another [Process](../Process.md)
- **Local replacement** : Each [Process](../Process.md) selects from only its own set of [allocated](Frames%20allocation.md) [frames](Paging.md)

Page replacement is activated either when the free [frame](Paging.md) is empty or when the free [frame](Paging.md) falls below a certain threshold

![](attachments/Pasted%20image%2020230612153126.png)

## Basic page replacement

1. Find the location of the desired [page](Paging.md) on [Main memory](../Main%20memory.md)
2. Find a free [frame](Paging.md) :
	- If there is a free [frame](Paging.md), use it
	- If there is no free [frame](Paging.md), use a page replacement algorithm to select a victim [frame](Paging.md)
	- Write victim [frame](Paging.md) to  if **dirty** (dirty if the frame as been modify)
3. Bring the desired page into [Secondary storage](../Secondary%20storage.md) the (newly) free [frame](Paging.md)
4. update the [Page table](../Page%20table.md)
5. Continue the [Process](../Process.md) by restarting the instruction that caused the [trap](../Interrupt.md)

![](attachments/Pasted%20image%2020230612144803.png)

## Page replacement algorithm

- **First-In-First-Out (FIFO)** algorithm
- **Most frequently Used (MFU)** algorithm : same as LRU but inverted
- **Least Recently Used (LRU)** algorithm : Replace [page](Paging.md) that has not been used in the most amount of time. Implementation :
	- Implementation with counter :
		- Every [page](Paging.md) entry in the [Page table](../Page%20table.md) has a counter
		- Every time a [page](Paging.md) is hit, copy the current clock in its counter
		- When a [page](Paging.md) needs to be change, target the [page](Paging.md) with the lowest counter
	- Implementation with stack :
		- Keep a stack op [page](Paging.md) number
		- on hit, move the [page](Paging.md) on the top ob the stack
		- When a [page](Paging.md) needs to be change, target [page](Paging.md) that is at the bottom
- **LRU approximation algorithm** (because LRU is slow), implementation :
	- Use of reference bit :
		- initially = 0
		- When hit, bit set to 1
		- When a [page](Paging.md) needs to be change, target a random [page](Paging.md) with the bit set to 0
	- Second chance algorithm :
		- same use of reference bit but more
		- Use a FIFO to look to the reference bit of [pages](Paging.md)
		- When a [page](Paging.md) needs to be change, target a [pages](Paging.md) following the FIFO and :
			- set reference bit to 0 if reference bit = 0 then continue searching
			- target it if reference bit = 1
	- Second chance algorithm (improvement) :
		- same as the basis one but use the dirty bit to be more revalent
		- When a [page](Paging.md) needs to be change, target a [pages](Paging.md) following the FIFO and :
			- best page to replace if (0,0) $\rightarrow$ (reference bit, dirty bit)
			- not quire as good (must write before remplacement) if (0,1)
			- probably will be used again if (1,0)
			- probably will be used again soons and need to write out before if (1,1)
- **Page buffering Algorithms** :
	- Keep a pool of free [frames](Paging.md)
	- keep list of modified [pages](Paging.md)
	- keep free [frames](Paging.md) contents intact and note what is in them (in case of reallocation)
- **Optimal algorithm** : Replace [page](Paging.md) that will not used for longest period of time (we can't read the future)
