# CPU scheduler

The CPU scheduler selects from among the [Process](Process.md) in [ready queue](Process%20scheduler.md), and allocates a [CPU core](Concepts/Multicore.md) to one of them (the allocation is made by the [Dispacher](Dispacher.md))

CPU scheduling decisions may take place when a [Process](Process.md) :

- Switches from running to waiting state (**non-preemptive** $\rightarrow$ once the [CPU](CPU.md) has been allocated to a [Process](Process.md), the [Process](Process.md) keeps the [CPU](CPU.md) until it releases)
- Switches from running to ready state (**preemptive** can result in race conditions)
- Switches from waiting to ready (**preemptive**)
- Terminates (**non-preemptive**)

Scheduling criteria :

- CPU utilisation : keep the [CPU](CPU.md) as busy as possible
- Throughput : number of [processes](Process.md) that complete their execution per time unit
- Turnaround time : amount of time to execute a particular [Process](Process.md)
- Waiting time : amount of time a [Process](Process.md) has been waiting in the [ready queue](Process%20scheduler.md)
- Response time : amount of time it takes from when a request was submitted until the first response is produced

When [Thread](Thread.md) are supported, [Threads](Thread.md) are scheduled, not [Process](Process.md)

## First-Come, First-Served (FCFS) scheduling

The [processes](Process.md) are running in the same order that their arrivals. That can leads to convoy effect (short [Process](Process.md) wait behind a long [Process](Process.md))

example of possible results :

![](attachments/Pasted%20image%2020230613145704.png)
![](attachments/Pasted%20image%2020230613145738.png)

## Shortest-Job-First (SJF) scheduling

The [processes](Process.md) are running in the order of their burst (little burst before). SJF is optimal but it is difficult to know in advance the burst of a [Process](Process.md)

![](attachments/Pasted%20image%2020230613150218.png)

## Shortest-remaining-time-first scheduling

Shortest-remaining-time-first scheduling is an opproximation of SJF using old burst time to guess what the next burst will be

![](attachments/Pasted%20image%2020230613150620.png)

## Round Robin (RR)

Each [Process](Process.md) gets a small unit of [CPU](CPU.md) time (**time quantum** q). After this time has elapsed, the [Process](Process.md) is preempted and added to the end of the [ready queue](Process%20scheduler.md). q must be should be greater than 80% of [CPU](CPU.md) bursts to avoid making to much [Context switch](Concepts/Context%20switch.md) (slow)

![](attachments/Pasted%20image%2020230613150918.png)

## Priority scheduling

A priority number is associated with each [Process](Process.md). The smaller this number is, the higher is the priority. The [CPU](CPU.md) is allocated to the [Process](Process.md) with the highest priority.

Low priority [Processes](Process.md) may never execute. To solve this issue, as time progress, increase the priority of the [Process](Process.md)

SJF is priority scheduling where priority is the inverse of predicted next [CPU](CPU.md) burst time

![](attachments/Pasted%20image%2020230613151854.png)

## Priority + RR scheduling

Run the [Process](Process.md) with the highest priority. [Process](Process.md) with the same priority run round-robin

![](attachments/Pasted%20image%2020230613151946.png)

## Multilevel Queue

separate queues for each priority and schedule the [Process](Process.md) in the highest-priority queue.

![](attachments/Pasted%20image%2020230613154220.png)

![](attachments/Pasted%20image%2020230613154250.png)

## Multilevel feedback queue

A [Process](Process.md) can move between the various queues. It is define by :

- The number of queues
- the Scheduling algorithms for each queue
- Method used to determine when to upgrade a [Process](Process.md)
- Method used to determine when to demote a [Process](Process.md)
- Method used to determine which queue a [Process](Process.md) will enter when that [Process](Process.md) needs service

Example :

![](attachments/Pasted%20image%2020230613154548.png)

## Multiple-processor scheduling

Symmetric multiprocessing (SMP) is where each [processor](Concepts/Multicore.md) is self scheduling. There is two ways to use [ready queues](Process%20scheduler.md) :

- One [ready queues](Process%20scheduler.md) for all [processor](Concepts/Multicore.md)
- One [ready queues](Process%20scheduler.md) per [processor](Concepts/Multicore.md)

![](attachments/Pasted%20image%2020230613155725.png)

If each [core](Concepts/Multicore.md) has more than one hardware [threads](Thread.md). The core can switch [Thread](Thread.md) when the running [Thread](Thread.md) has a memory stall

![](attachments/Pasted%20image%2020230613162442.png)

So, there is two level of scheduling :

- Scheduling by [CPU](CPU.md)
- Scheduling by [core](Concepts/Multicore.md)

![](attachments/Pasted%20image%2020230613162814.png)