Notice that the assembler ==relieves== the compiler and the assembly language programmer from the tedium of calculating addresses for branches, ==just as it does== for calculating data addresses for loads and stores

While easier to understand, this approach is not practical, since the clock cycle must be severely ==stretched to== accommodate the longest instruction


For example, the data memory must read on a load and write on a store.

When the clock input C is deasserted, the latch is said to be closed, and the value of the output (Q) is whatever value was stored the last time the latch was open.

Let’s start at the top by looking at which datapath elements each instruction needs, and then work our way down through the levels of abstraction.

The data memory must be written on store instructions;


![[Pasted image 20251229071409.png]]

