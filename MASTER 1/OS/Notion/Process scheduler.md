# Process scheduler

The process scheduler selects among available processes for next execution on one [CPU](CPU.md). It's goal is to maximise [CPU](CPU.md) use

To do its job, it puts [PCB](PCB.md) in **scheduling queues** :

- Ready queue : set of all [Processes](Process.md) residing in main memory, ready and waiting to execute
- Wait queues : set of [Processes](Process.md) waiting for an event

![](attachments/Pasted%20image%2020230611141348.png)

![](attachments/Pasted%20image%2020230611141413.png)