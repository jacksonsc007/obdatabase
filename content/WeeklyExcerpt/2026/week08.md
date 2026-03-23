One vector instruction can include ==scores== of independent operations ==yet be encoded== in the same number of bits as a conventional scalar instruction.


Each of the vector arithmetic units contains four execution pipelines, one per lane, which ==act in concert== to complete a single vector instruction.


Taking a higher-level perspective, vector load/store units play a similar role to prefetch units in scalar processors ==in that== both try to deliver data bandwidth by supplying processors with streams of data.


With his arms and legs crossed as he sat in midair, Subaru’s stern face caused Petra to recall the  events inside Subaru’s memories, in the Royal Capital where Al and Rem had crossed paths.

Although Petra did feel that Subaru’s reckless behavior back then was quite bad, she did not feel  completely ==disillusioned== towards him. However, Subaru himself remembered it as an utterly humiliating experience that made him ==squirm== just thinking about it. In fact, everyone who was  there must have looked down on Subaru’s reckless behavior, so the only person who would not  feel disillusioned by his actions==, if Petra were excluded,== would be Rem, who had been blindly devoted to him ==as far back as then.==



==Just like with all of us==, when Al-san sees Rem-neesama, his Memories should get all mixed  up.


sparse matrices are ==commonplace==, so it is important to have techniques to allow programs with sparse matrices to execute in vector mode.


However, as Section 4.7 shows, a memory system can deliver better performance by designing for this case and by using more hardware resources versus when architects have a laissez-faire attitude toward such unpredictable accesses.


As we will see in Section 4.4, all loads are gathers and all stores are scatters in GPUs in that no separate instructions restrict addresses to be sequential.


It is this dialogue between the compiler and the programmer, ==with each side== giving hints to the other on how to improve performance, that simplifies programming of vector computers.


Today, the main factor that affects the success ==with which== a program runs in vector mode is the structure of the program itself:


**英文原文：**  
_In general, the goal of these extensions ==has been to== accelerate carefully written libraries ==rather than== for the compiler to generate them (see Appendix H), but recent x86 compilers are trying to generate such code, particularly for floating-point-intensive applications._

**中文翻译：**  
总体而言，这些扩展指令的设计初衷是加速**人工精心编写的库函数**，而非由编译器自动生成（参见附录 H）；但近期的 x86 编译器正尝试自动生成此类代码，尤其是在浮点运算密集型应用中。

**the goal … has been to … rather than …**

- 典型对比结构：_A has been to do X rather than (to) do Y_
- 注意：_rather than_ 后可省略 _to_（尤其在正式/技术写作中），即 _rather than generate_ = _rather than to generate_。
- 此处强调设计意图的优先级：**人为优化 > 编译器自动优化**


Since the opcode determines the width of the SIMD register, every time the width doubles, ==so must the== number of SIMD instructions.


_The ==overarching issue==, however, is that due to the == == importance of backwards binary compatibility, once an architecture ==gets started on the SIMD path it’s very hard to get off it._==



Arithmetic intensity is the ==ratio== of floating-point operations ==per== byte of memory accessed.

At an arithmetic intensity of 0.25 FLOP/byte, the SX-9 is 10 faster ==at== 40.5 GFLOP/s ==versus== 4.1 GFLOP/s ==for== the Core i7.


Such ==affordability== and convenience makes high performance computing available to many. The interest in GPU computing ==blossomed== when this potential was combined with a programming language that made GPUs easier to program.


GPUs and CPUs do not go back in computer architecture ==genealogy== to a common ancestor; there is no ==“missing link”== that explains both.



CUDA is an elegant solution to the problem of representing parallelism in algorithms, not all algorithms, ==but enough to matter==. It seems to resonate in some way with the way we think and code, ==allowing== an easier, more natural expression of parallelism beyond the task level.

> CUDA 是一种优雅的方案，用于解决在算法中表达并行性的问题——虽非适用于所有算法，但已足以覆盖关键场景。它似乎在某种程度上契合了我们的思维方式与编程习惯，使我们能更轻松、更自然地表达**超越任务级**（task-level）的并行性。

- **not all algorithms, but enough to matter**
    - 省略句式（省略重复主谓）：= _not all algorithms [are covered], but [enough are covered] to matter_。
    - _enough to matter_：地道表达，意为“足够重要／有实际意义”；_matter_ 此处作动词，“有关系、起作用”。  
        🌟 类似用法：_good enough to use_, _simple enough to understand_。


The name of their system is CUDA, ==for== Compute Unified Device Architecture.



Like many parallel systems, a compromise between productivity and performance is for CUDA to include intrinsics to give programmers explicit control over the hardware. 
```
如同许多并行系统一样，CUDA 在开发效率与性能之间采取的一种折中方案是：**通过提供内建函数（intrinsics），让程序员能显式控制硬件**。

这是一个典型的 **“be + for + 名词/代词 + to do”** 结构，用于表达**“某事是（由某主体）去做……”**，强调**责任、目的或安排**。它不是字面的“为……而存在”，而是英语中一种正式、客观的表达方式。

- **突出“动作的执行者”（CUDA）**：强调“是 CUDA 这个平台/工具链主动提供了 intrinsics”，而非被动发生。
- **体现设计意图**：暗示这是一种**有意识的架构决策**（design choice），而非偶然结果。
- 相比之下，若说：
    > _…a compromise is including intrinsics in CUDA._  
    > 语法虽可接受（动名词作表语），但弱化了“CUDA 作为主体”的主动性，且略显口语化。
```
The struggle between productivity on the one hand versus allowing the programmer to be able to express anything that the hardware can do on the other hand happens often in parallel computing. It will be interesting to see how the language evolves in this classic productivity-performance battle as well as to see whether CUDA becomes popular for other GPUs or even other architectural styles.


One obstacle to understanding GPUs ==has been== the jargon, with some terms even having misleading names. This obstacle ==has been== surprisingly difficult to overcome, as the many rewrites of this chapter can ==attest==.
```
理解GPU的一大障碍一直是术语（行话），其中一些术语的名称甚至具有误导性。这一障碍出人意料地难以克服——本章历经多次重写，便足以证明这一点。

**has been**（现在完成时）

- 此处连续使用两次 _has been_，强调“从过去持续至今”的状态（障碍一直存在，且影响仍在）。
- 注意：主语是单数 _one obstacle_ / _this obstacle_ → 动词用第三人称单数 _has_，而非 _have_。
- 技术写作中常用现在完成时表达“长期存在的问题/现象”




```


To try to ==bridge== the ==twin== goals of making the architecture of GPUs understandable and learning the many GPU terms with nontraditional definitions, our approach is to


Both styles have gather-scatter data transfers and mask registers, and GPU processors have even more registers ==than do== vector processors.


This reduction occurs because the vector operations work on 32 elements and the overhead instructions that ==constitute== nearly half the loop on RV64G are not present in the RV64V code.

ector architects call forwarding of elementdependent operations ==chaining==, in that the dependent operations are “chained” together.


“==Staying with the analogy of a== SIMD Processor as a vector processor, you could say that it has 16 lanes, the vector length is 32, and the chime is 2 clock cycles.” (Hennessy, p. 318)


_It has 60 blocks, with four spares to improve yield._
```
它包含60个功能块，另配有4个冗余备用块，以提高良率。

- **to improve yield**
    - 不定式短语表目的：**为了提高良率**。
    - **yield**（良率）：半导体制造中关键指标，指合格芯片占总生产芯片的比例（如 95% yield）。
    - 冗余设计（spares）是提升 yield 的常用手段：当某 block 因制造缺陷失效时，可用 spare 替换，使整 chip 仍可工作。
```


The latency of memory instructions is variable because of hits and misses in the caches and the TLB, thus the requirement of a scoreboard to determine when these instructions are complete.
```
- **the requirement of A**：名词性结构，相当于 _A is required_；更自然的说法也可用 _requiring a scoreboard_（现在分词作结果状语），但原文用名词短语更强调“需求”的客观存在。
```


Note that the number of lanes in a GPU SIMD Processor can ==be anything up to== the number of threads in a Thread Block, just as the number of lanes in a vector processor can vary between 1 and the maximum vector length.

```
- **can be anything up to…**
    - _anything up to X_：意为“最多可达 X，也可更少”，强调**上限约束而非固定值**。
    - 类似表达：_ranging from 1 to X_, _as many as X_.
    - 关键：不是“必须等于”，而是“≤ X”的灵活设计。
```