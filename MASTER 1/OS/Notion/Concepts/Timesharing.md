# Timesharing

Timesharing is an extension of Batch system ([Process](../Process.md) are switched when it is waiting) that switch [Process](../Process.md) more often

Some rules :

- Response time should be < 1 second
- Each user hat at least one program in memory (called [Process](../Process.md))
- if several [Processes](../Process.md) ready to run at the same time, use of [CPU scheduling](../Concepts/CPU%20scheduling.md)
- [Virtual memory](../Virtual%20address%20space.md) allows execution of processes not completely in memory