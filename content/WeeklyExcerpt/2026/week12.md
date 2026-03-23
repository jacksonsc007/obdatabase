Although the study did not compare the latest versions of CPUs and GPUs, it was the most in-depth comparison of the two styles ==in that== it explained the reasons behind the differences in performance.

This observation reinforces the importance of gather-scatter to vector and GPU architectures ==that is missing from== SIMD extensions.
```
这一观察进一步凸显了 **gather-scatter（聚集-散射）操作** 对向量架构与 GPU 架构的重要性——而该功能在传统 SIMD 扩展中却缺失。

**that is missing from SIMD extensions**

- 定语从句，修饰 _the importance_（更准确地说，是修饰整个名词短语 _the importance of gather-scatter…_），但语法上易误认为修饰 _architectures_ —— 实际是**后置修饰逻辑主语**，属“悬垂修饰”（dangling modifier）的常见学术用法（可接受，因语义清晰）。
- 更严谨改写：
    
    > _…the importance of gather-scatter—a capability missing from SIMD extensions—to vector and GPU architectures._
```


the start-up overhead for DAXPY is 158 clock cycles, which substantially increases the ==break-even point==.
Because the Cray-1 clock rate was also higher (even though the 205 was newer), the ==crossover point== was a vector length over 100.