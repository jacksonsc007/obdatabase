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