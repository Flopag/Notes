# Process scheduler

The process scheduler selects among available [processes](Process.md) to [allocate](Concepts/Frames%20allocation.md) and  puts them in queues. its goal is to maintain the system stable (not the same than the [CPU scheduler](CPU%20scheduler.md))

To do its job, it puts [PCB](PCB.md) in **scheduling queues** :

- Ready queue : set of all [Processes](Process.md) residing in main memory, ready and waiting to execute
- Wait queues : set of [Processes](Process.md) waiting for an event

![](attachments/Pasted%20image%2020230611141348.png)

![](attachments/Pasted%20image%2020230611141413.png)