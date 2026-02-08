The primary difference between RISC-V and the 360 is the **==presence==** of register-memory instructions in the latter architecture.


In a processor with more real registers, we want renaming to provide an even larger set of virtual registers, often ==numbering in t==he hundreds.

Once an instruction has issued and is waiting for a source operand, it refers to the operand by the reservation station number ==where the instruction that will write the register has been assigned==.


It can achieve high performance without requiring the compiler to target code to a specific pipeline structure, a valuable property in the era of shrink-wrapped mass market software.
 它能够在不依赖编译器为特定流水线结构生成优化代码的情况下实现高性能，这一特性在“即买即用”的大众软件时代尤为宝贵。
 ```
 - **shrink-wrapped mass market software**
    - 字面：“用塑料膜封好的大众市场软件”
    - 实际含义：**即买即用的商业化通用软件**
        - 如 Windows 上的 Office、Photoshop、Steam 游戏等
        - 用户买来就装，不管底层 CPU 架构

💡 为什么叫 "shrink-wrapped"？

- 早期软件以光盘形式销售，外层包裹着一层紧贴的透明塑料膜（shrunk when heated）
- 成为“盒装软件”的代名词
```


Branch prediction reduces the direct stalls attributable to branches, but for a processor executing multiple instructions per clock, just predicting branches accurately may not be sufficient to generate the desired amount of instruction-level parallelism



We can also try to handle exceptions as soon as they arise and all earlier branches are resolved, but this is more challenging in the case of exceptions than for branch mispredict and, because it occurs less frequently, not as critical.


There is an important difference in how stores are handled in a speculative processor versus in Tomasulo’s algorithm.


he EPIC approach, as embodied in the IA-64 architecture, extends many of the concepts of the early VLIW approaches, providing a blend of static and dynamic approaches.


The preceding VLIW code sequence requires at least eight FP registers, whereas the same code sequence for the base RISC-V processor can use as few as two FP registers or as many as five when unrolled and scheduled.



This requirement makes migrating between successive implementations, or between implementations with different issue widths, more difficult than it is for a superscalar design.

“It is not clear that a multiple-issue processor is preferred over a vector processor for such applications;” (Hennessy, p. 222)


Because the number of possibilities climbs as the square of the number of instructions that can be issued in a clock, the issue step is a likely bottleneck for attempts to go beyond four instructions per clock.


Should sufficient reservation stations not be available (such as when the next few instructions in the program are all of one instruction type), the bundle is broken, and only a subset of the instructions, in the original program order, is issued.


From a performance viewpoint, we can show how the concepts ==fit together with== an example.



“Notice that we need to ==have assigned r==eorder buffer entries for this logic to operate properly, and recall that all these updates happen in a single clock cycle in parallel, not sequentially.” (Hennessy, p. 225)


Because this is the first instruction in this issue bundle, it looks no different than what would normally happen for a load.
Because we assumed that the second operand of the FP instruction was from a prior issue bundle, this step looks ==like it would== in the single-issue case.
Of course, if further instructions in this issue bundle depended on the FP operation ==(as could happen== with a four-issue superscalar),


This example clearly shows how speculation can be advantageous when there are data-dependent branches, which otherwise would limit performance.

To reduce the branch penalty for our simple five-stage pipeline, as well as for deeper pipelines, we must know whether the ==as-yet-undecoded== instruction is a branch ==and, if so,== what the next program counter (PC) should be.


 Essentially, this amounts to recognizing that characterizing instruction fetch as a simple single pipe stage ==given the complexities of multiple issue== is no longer valid.

> is no longer valid 不修饰 complexities

本质上，这相当于认识到：在多发射架构如此复杂的背景下，仍将“指令获取”描述为一个简单的单级流水线阶段，已不再成立。

> 更自然流畅版：  
> 从根本上说，这意味着我们必须承认——面对多发射带来的种种复杂性，再把“取指令”看作一个简单单一的流水线阶段，已经不合时宜了。



The instruction fetch unit also provides buffering, essentially acting as an on-demand unit to provide instructions to the issue stage as needed and in the quantity needed.
随时按需、按量地将指令输送给发射阶段。



Both register renaming and reorder buffers continue to be used in high-end processors, which now ==feature the ability to== have as many as 100 or more instructions (including loads and stores waiting on the cache) in flight. 


==Whether renaming or a reorder buffer is used,== the key complexity bottleneck for a dynamically scheduled superscalar remains issuing bundles of instructions with dependences within the bundle