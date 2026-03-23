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


“It trades an increase in multithreaded throughput for a loss in the performance (as measured by latency) of a single thread.” (Hennessy, p. 243)

Because instructions from other threads will be issued only when a thread encounters a costly stall, coarse-grained multithreading ==relieves the need== to have thread-switching be essentially free and is much less likely to slow down the execution of any one thread.
Coarse-grained multithreading suffers, however, from a major drawback


Simultaneous multithreading is a ==variation on== fine-grained multithreading tha==t arises naturally when== fine-grained multithreading is implemented on top of a multiple-issue, dynamically scheduled processor.


Because instruction issue and execution are connected, a thread can issue only as many instructions as are ready. W


Although Figure 3.31 greatly simplifies the real operation of these processors, it does illustrate the potential performance advantages of multithreading in **==general and==** SMT in wider issue, dynamically scheduled processors.


this approach of translating the x86 instruction set into simple operations that are more easily pipelined was introduced in the Pentium Pro in 1997 ==and has been used since.==



==rarely can== significant performance be achieved by tuning only one part of the microarchitecture!



What quickly became clear was that the main limitation in exploiting ILP often turned out to be the memory system

The result was that these designs ==never came close to achieving== the peak instruction throughput despite the large transistor counts and extremely sophisticated and clever techniques.

One of the more surprising results of the past decade ==has been== in branch prediction.


“Nonetheless, it appears that the advantage gained by not misusing a prediction for one branch on another branch ==more than justifies== the allocation of bits to tags versus predictions.” (Hennessy, p. 262)


Wall’s study was not believed by some, but 10 years later, the reality had sunk in.


As 2000 began the focus on exploiting instruction-level parallelism was at its peak.


By 2005 Intel and all the other major processor manufacturers had revamped their approach to focus on multicore.


“and the responsibility for using the” (Hennessy, p. 264)
“processor efficiently would largely shift from the hardware to the software and the programmer.” (Hennessy, p. 265)


Even the expansion in SMT support seems to be more of a focus than is an increase in the ILP throughput:


Wall’s study was not believed by some, but 10 years later, the reality had sunk in, and the combination of modest performance increases with significant hardware resources and major energy issues coming from incorrect speculation forced a change in direction.


Between Heinkel and Felt, a considerably deadly rift had formed. In response to that issue, he  had worked out a countermeasure to stabilize it for the time being, but that had incurred  “Aldebaran’s” displeasure, and was nothing more than a temporary bandaid solution.



For the moment, it seemed Aldebaran and his group did not intend to inflict any further harm  onto Frufoo or much less, take her life.


“Of course, it would be a problem for Aldebaran ==were Roy to die at this time==, so he did intend to redo at every instance of failure and search for a way to ensure Roy did well.”


Engraving a curse mark isn’t as light a job as you’re thinking it to be.

Speaking further of the impression given by the curse mark based  on its impression, the one who taught Aldebaran how to engrave a curse mark and the nature of  them, would likely bestow the plight of a half-day long tedious lecture about it.


“As an example, should he ever seek to rely on Roy’s Authority as Gluttony like he just had, to keep him turned face-down as a card that could not be used immediately would be some excessively maladroit handling.” **中文翻译：**    
举例来说，倘若他今后还想像刚才那样，试图借助罗伊作为“暴食”（Gluttony）的权威来行事——比如强行让对方面朝下趴着，使其暂时无法被当作一张可立即使用的牌——这种做法将显得极其笨拙失当。  
  
---  
  
**要点解析：**  
  
1. **as an example**    
   → 常用引出例证的短语，相当于“例如”“举个例子”，正式书面语中常见。  
  
2. **should he ever seek to…**    
   → 倒装虚拟语气结构（= *if he should ever seek to…*），表示“万一/倘若他将来试图……”，用于表达假设性、较正式或文学性语境。    
   ✅ 注意：主句用倒装（助动词 *should* 提前），省略 *if* 是英语中较高级的修辞手法。  
  
3. **rely on Roy’s Authority as Gluttony**    
   → “依靠罗伊作为‘暴食’的权威”；    
   - *as Gluttony* 是同位语，说明 Roy 的身份/角色（可能来自某种卡牌/游戏设定，如《七宗罪》主题）；    
   - 此处 *Authority* 首字母大写，暗示是特定头衔或职位（专有名词化），非普通“权威”。  
  
4. **to keep him turned face-down**    
   → 动词不定式作目的状语；    
   - *keep + 宾语 + 过去分词* 表示“使某人/某物保持某种被动状态”；    
   - *face-down* 作形容词（连字符连接），意为“面朝下”，常用于纸牌、卡片语境（如“place the card face-down”）。  
  
5. **as a card that could not be used immediately**    
   → 比喻修辞：把人比作“一张暂时无法打出的牌”；    
   - *that could not be used immediately* 是定语从句，修饰 *card*；    
   - 此隐喻常见于策略游戏/卡牌游戏中，表示“暂被禁用/封印的角色”。  
  
6. **some excessively maladroit handling**    
   → “某种极度笨拙的处理方式”；    
   - *some* 在此为强调语气（略带贬义），非确指数量；    
   - *maladroit* 是较正式/文学词汇，意为“笨拙的、不灵巧的”，源自法语（*mal-* “坏” + *adroit* “灵巧”），比 *clumsy* 更书面；    
   - *handling* 此处为抽象名词，指“应对/处置方式”，而非字面“用手操作”。  
  
📌 **学习提示**：本句融合了虚拟语气、倒装、比喻修辞与专业术语（卡牌游戏语境），是典型的高阶英语写作句式，适合精读模仿。注意其正式程度与语境依赖性——日常口语中极少如此表达。  
  
需要我针对某一部分进一步拆解或提供类似例句吗？



“The interloper had appeared in quite literally the blink of an eye, and by making an entrance without having given any preface, his instincts did not even have the time to sound the alarm bells.”


The power wall ==leads== architects to ==value architectures== that can ==deliver== good performance without the energy and design complexity costs of highly out-of-order superscalar processors. 
> “功耗墙”（power wall）促使架构师更青睐那些**无需依赖高能耗、高设计复杂度的深度乱序超标量处理器**，却仍能提供良好性能的架构。

Vector instructions ==are a natural match to this trend== because architects can use them to increase performance of simple in-order scalar processors without greatly raising energy demands and design complexity. 
> 向量指令（vector instructions）天然契合这一趋势


In practice, developers can ==express== many of the programs that ran well on complex out-oforder designs more efficiently as data-level parallelism in the form of vector instructions, as Kozyrakis and Patterson (2002) showed.
> 实践中，正如Kozyrakis与Patterson（2002）所指出的，开发者可将许多原本在复杂乱序架构上运行良好的程序，更高效地改写为以**数据级并行性**（data-level parallelism）形式表达的向量指令。


The read and write ports, which total at least 16 read ports and 8 write ports, are connected to the functional unit inputs or outputs by a pair of crossbar switches.

one way to increase the register file bandwidth is to ==compose== it from multiple banks, which work well with relatively long vectors.


This restriction will be lifted shortly.


This reduction occurs because the vector operations work on 32 elements and the overhead instructions that constitute nearly half the loop on RV64G are not present in the RV64V code.


Vector architects call forwarding of elementdependent operations chaining, ==in that== the dependent operations are “chained” together.


