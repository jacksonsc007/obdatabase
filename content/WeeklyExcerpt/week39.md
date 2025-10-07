By deferring the copying of the pages in private objects ==until the last possible moment==, copy-on-write makes the most efficient use of scarce physical memory.

Further, if the user of this program wanted to read a file that was larger than MAXN, ==the only recourse== would be to recompile the program with a larger value of MAXN.


Madness arrives crowds, sanity returns one by one

As we will see, there is a tension between maximizing throughput and utilization.

A significant disadvantage is that the cost of any operation that requires a search of the free list, such as placing allocated blocks, will be linear in the total number of allocated and free blocks in the heap.

Immediate coalescing is straightforward and can be performed in constant time, but with some request patterns it can introduce a form of thrashing where a block is repeatedly coalesced and then split soon thereafter.


To help you clear this hurdle, we will work through the implementation of a simple allocator based on an implicit free list with immediate boundary-tag coalescing.


Second, even if we ==were to know== that p was a pointer, there would be no obvious way for isPtr to determine whether p points to some location in the payload of an allocated block.



However, it is conservative ==in the sense that== it may incorrectly mark blocks that are actually unreachable, and thus it may fail to free some garbage.


. If we are lucky, the program will crash immediately. But more likely we will be ==left scratching our heads ==when the program produces an incorrect answer much later in its execution.


Memory leaks are slow, silent killers that occur when programmers ==inadvertently== create garbage in the heap by forgetting to free allocated blocks.
内存泄漏是缓慢而无声的程序杀手，当程序员忘记释放内存块而在堆中无意制造垃圾时，便会悄然发生。


The Rio package provides convenient, robust, and efficient I/O in applications such as network programs that ==are subject to short counts==.

Most C programmers use standard I/O exclusively throughout their careers,== never bothering with== the lower-level Unix I/O functions


This is not a problem for sequential programs, but closing an already closed descriptor in a threaded program is a recipe for disaster
这对于顺序执行的程序来说不成问题，但在多线程程序中关闭一个已经关闭的描述符无异于自取灭亡。


To help us keep the different caches in the memory hierarchy straight, we will use the term SRAM cache to denote the L1, L2, and L3 cache memories between the CPU and main memory, and the term DRAM cache to denote the VM system’s cache that caches virtual pages in main memory.

