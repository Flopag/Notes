# Process termination

When a process finished what it must do, it asks the [Operating system](../Operating%20system.md) to delete it (using `exit()` [System call](../System%20call.md) in UNIX). When the process is terminated, it returns the status data to its parent (via `wait()`) and its resources are de-allocated by the [Operating system](../Operating%20system.md)

Parent can terminate the execution of a children using `kill()` [System call](../System%20call.md)

If a parent terminate before its children and great-children, some [Operating system](../Operating%20system.md) will terminate them by itself (**cascading termination**)

If no parent is waiting a [Process](../Process.md), this [Process](../Process.md) is called **zombie**

If a [Process](../Process.md) terminate without waiting its children, these children are called **orphans** (linux re-parent them to init [Process](../Process.md))