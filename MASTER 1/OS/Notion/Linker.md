# Linker

A liker is a program that combines all object files (compiled code) into a single binary executable file (**static liking**)

We don't want to make a binary executable with libraries in it. So we use **dynamically linked libraries** that is a library that is [Loaded](Loader.md) at the same time than the executable and then linked (**Dynamic linking**). This linking is done by **stub** (small piece of code) that will locate the appropriate library routine and replaces itself with the found address

![](attachments/Pasted%20image%2020230611111748.png)