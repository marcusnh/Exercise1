# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Concurrency is when means doing multiple tasks which start,run and completes in overlapping time periods. There is no order, the CPU only needs to be able to run to or more tasks at the same time. Parallelism is when multiple tasks run at the some time, for instance on multpcore processor. They are not he same thing. In a singel core CPU you may have concurrency but Not parallelism.  Concurrency takes advantage of CPU timeslicing, each task run part of its task and then goes to a waiting state. When the first task is in the waiting state, the CPU is assigned to a second task. So the task only virtually runs at the same time not physically, as it does with parallelism. 
 
 ### Why have machines become increasingly multicore in the past decade?
> Machines have become increasingly multicore in the past decade because they improve the performance of machines. Software algorithms that runs the programs becomes the bottle neck (Amdahl´s law)


 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 >Concurrent execution is when there might be conflicts between read and writing operations, which can occur with a multi-user system or DBSM:
- To apply Isolation through mutual exclusion between conflicting transactions
- To resolve read-write and write-write conflict issue
- To preserve database consistency through constantly preserving execution obstructions
- The system needs to control the interaction among the concurrent transactions. This control is achieved using concurrent-control schemes.
- Concurrency control helps to ensure serializability

 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > Creating concurrent programs makes the programmers life easier,harder, it depends on the problem. 
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > 
 - A process is a program that has been load into memory along with all the resources it needs to operate.  In single-threaded processes, the process contains one thread. The process and the thread are one and the same, and there is only one thing happening.In multithreaded processes, the process contains more than one thread, and the process is accomplishing a number of things at the same time 
 - A thread is a segment of a process. A process can have multiple threads, which are contained within the process. A thread have 3 states: running, ready, and blocked.

 - A green thread emulates a multithread environment  whitout relying on any operating system (OS) capabilities. It scheduled by a virtual machine instead of naitvely by the underlying operating system.

 - A coroutine is a subrutine that allow for multiple entry points for suspending and resuming execution at certain locations.Unlike subroutines, coroutines can exit by calling other coroutines, which may later return to the point where they were invoked in the original coroutine.
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > These commands creates a thread. 
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > GIL is a mutex (a lock) that protects  access to python objects. Preventing multiple threads from executing Python bytecodes at once. This is necessary mainly because pythons memory managment is not thread-safe.  As a result, two threads calling the same function may take twice the time as a singel thread calling the same function twice(worsening multithreaded programs)
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > The workaround is using a mulit-process approach where you use multiple processes in stead of threads. Each Python process gets its own Python interpreter and memory space so the GIL won’t be a problem. The module to is called "multiprocessing"
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > If n>=1 the function changes the current settings. Since GOMAXPROCS sets the maximum number of CPUs that can be executing simultaneously and returns the previous setting.
