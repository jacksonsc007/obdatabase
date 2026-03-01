Although there is some similarity between the x86 microarchitecture and PTX, ==in that== both translate to an internal form (microinstructions for x86), the difference is that this translation happens in hardware at runtime during execution on the x86 ==versus== in software and load time on a GPU.

The resulting performance sometimes ==belies== that simple abstraction.

As previously mentioned, in the ==surprisingly common== case that the individual lanes ==agree on== the predicated branch—such as branching on a parameter value that is the same for all lanes so that all active mask bits are 0s or all are 1s—the branch skips the THEN instructions or the ELSE instructions.

“Conditional execution is a case where ==GPUs do in runtime hardware what== vector architectures do at compile time.”

Although it will depend on the speed of the scalar processor versus the vector processor, the ==crossover point== when it’s better to use scalar might be when less than 20% of the mask bits are 1s.

Thus the efficiency ==with which== GPUs execute conditional statements ==comes down to== how frequently the ==branches will diverge==. For example, one calculation of eigenvalues has deep conditional nesting, but measurements of the code show that around 82% of clock cycle issues have between 29 and 32 out of the 32 mask bits set to 1, so GPUs execute this code more efficiently than ==one might expect.==

It felt like somehow Summer imagined that if she kept it light and moved on quickly, Tom woudn't be affected by it at all. Which is only a conclusion she could have come to if she, like Tom, was imagining him as the person she wanted him to be instead of who he was.

“The argument follows Little’s Law from queuing theory: the longer the latency, the more threads need to run during a memory access, which in turn requires more registers.”
```
**The argument follows Little’s Law from queuing theory**

- _follows_：此处意为“依据／遵循”，非字面“跟随”；学术写作中常用 _follow X_ 表“以X为理论基础”。
    - 类似表达：_is grounded in…_, _is derived from…_
```


Now that the veil has been lifted, we can see that GPUs are really just multithreaded SIMD Processors, although they have more processors, more lanes per processor, and more multithreading hardware ==than do traditional multicore computers==.


As with any virtual memory system, care must be taken to avoid excessive page movement.

Along with the quirky jargon of GPUs, these similarities have contributed to the confusion in architecture circles about how novel GPUs really are.
> 加之 GPU 领域特有的古怪术语，这些相似性进一步加剧了体系结构学界对 GPU 真正创新程度的困惑。


“This difference is why we use “SIMD Processor” as the more descriptive term because it is closer to a SIMD design than it is to a traditional vector processor design.”


The scalar processor can be slower than a vector processor for floating-point computations in a vector computer, but not ==by the same ratio== as the system processor versus a multithreaded SIMD Processor (given the overhead).


	
If you ever need any help, just let me know. 如果你什么时候需要帮助，就告诉我。