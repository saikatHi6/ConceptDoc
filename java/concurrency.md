##wait-free: 

Wait-free is a stronger condition which means that every thread is guaranteed to make progress over an arbitrary period of time, regardless of the timing/ordering of thread execution; and so we can say that the threads finish independently. All wait-free programs are lock-free.

##Lock-free: 

If a program is lock-free, it basically means that at least one of its threads is guaranteed to make progress over an arbitrary period of time. If a program deadlocks, none of its threads (and therefore the program as a whole) cannot make progress - we can say it's not lock-free. Since lock-free programs are guaranteed to make progress, they are guaranteed to complete (assuming finite execution without exceptions).

[Wait-free & Lock-free](https://www.ibm.com/developerworks/java/library/j-jtp11234/)
