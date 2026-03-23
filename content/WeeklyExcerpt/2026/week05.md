With register renaming, deallocating registers is more complex because before we free up a physical register, we must know that it no longer corresponds to an architectural register and that no further uses of the physical register ==are outstanding==.

In particular, dependent instructions in an issue bundle must be issued with the assigned virtual registers of the instructions ==on which== they depend.


Duplicating the functional units is straightforward ==assuming silicon capacity and power==; 
==the real complications arise== in the issue step and **correspondingly in** the commit step. 
The Commit step is the dual of the issue step, and the requirements are similar,

> 只要假设有足够的芯片面积和功耗预算，复制功能单元是直截了当的；真正的复杂性出现在“发射（issue）阶段”，相应地也体现在“提交（commit）阶段”。“提交”阶段是“发射”阶段的对偶，两者的需求也相似。

```
**assuming silicon capacity and power**

- “假设芯片面积和功耗足够”


```


“The complexity of the analysis required during the issue cycle grows as the square of the issue width, and a new processor is typically targeted to have a higher clock rate than in the last generation!” (Hennessy, p. 237)


Because register renaming and the reorder buffer approaches are ==duals==, the same complexities arise independent of the implementation scheme.

One of the significant advantages of speculation is its ability to uncover events that would otherwise stall the pipeline early, such as cache misses.


Finally, if speculation causes an exceptional event to occur, such as a cache or translation lookaside buffer (TLB) miss, the potential for significant performance loss increases, ==if that event would not have occurred without speculation==.


Speculating on multiple branches slightly complicates the process of speculation recovery but is straightforward otherwise
对多个分支进行推测会略微增加推测恢复过程的复杂性，但除此之外依然相当直接


“But, if speculation lowers the execution time by more than it increases the average power consumption, then the total energy consumed may be less.” (Hennessy, p. 238)


Value prediction could, ==if it were highly accurate==, eliminate data flow restrictions and achieve higher rates of ILP



Despite many researchers focusing on value prediction in the past 15 years in dozens of papers, the results have never been sufficiently attractive to justify general value prediction in real processors.
尽管过去 15 年中有许多研究人员在数十篇论文中聚焦于值预测，但其成果从未足够出色，不足以证明在真实处理器中广泛采用值预测是合理的。
```
- **to justify...**
    - 足以证明……是合理的 / 值得的
    - 固定搭配：_justify doing something_
```