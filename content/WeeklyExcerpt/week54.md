Doing so, however, requires that twice as many instructions be overlapped in execution, and this additional overlap increases the relative performance loss from data and control hazards.

In some VLIW designs, ==this has not been the case,== and recompilation was required when moving across different processor models; in other static issue processors, code would run correctly across different implementations, but often ==so poorly as to== make compilation effectively required.


When the result is completed, it is sent to any reservation stations waiting for this particular result as well as to the commit unit, which buffers the result until it is safe to put the result into the register file o==r, for a store,== into memory.


The buffer in the commit unit, often called the reorder buffer, is also used to supply operands, ==in much the same way as== forwarding logic does in a statically scheduled pipeline.


This style of execution is called an out-of-order execution, since the instructions can be executed in a different order than they were fetched.



Now that we have collided with the power wall, we are seeing designs with multiple processors per chip where the processors are not as deeply pipelined or as aggressively speculative as its predecessors.

The belief is that while the simpler processors are not as fast as their sophisticated brethren, they deliver better performance per Joule, so that they can deliver more performance per chip when ==designs are constrained more by energy than they are by the number of transistors==.


Floating-point and SIMD operations add a two more pipeline stages to the instruction execution section and feature one pipeline for multiply/divide/square root operations and one pipeline for other arithmetic operations.
```
#### 3. **and feature one pipeline for multiply/divide/square root operations**

- **feature**：这里作动词，意思是“具有，配备”
    - 常用于描述产品或系统的设计特点
    - ✅ 类似用法：
        
        > This processor features a dedicated AI accelerator.  
        > 这款处理器配备了专用的 AI 加速单元。
        
- **one pipeline for...**：一条专用于……的流水线
- **multiply/divide/square root operations**：乘法、除法、平方根操作
    - 这些都是耗时较长的复杂运算
    - 尤其是除法和开方，在硬件上实现成本高

💡 设计思想：  
把这些重操作集中到一条专用流水线中，避免阻塞其他轻量级运算
```