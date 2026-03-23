Notice that the assembler ==relieves== the compiler and the assembly language programmer from the tedium of calculating addresses for branches, ==just as it does== for calculating data addresses for loads and stores

While easier to understand, this approach is not practical, since the clock cycle must be severely ==stretched to== accommodate the longest instruction


For example, the data memory must read on a load and write on a store.

When the clock input C is deasserted, the latch is said to be closed, and the value of the output (Q) is whatever value was stored the last time the latch was open.

Let’s start at the top by looking at which datapath elements each instruction needs, and then work our way down through the levels of abstraction.

The data memory must be written on store instructions;


![[Pasted image 20251229071409.png]]


The first design principle from Chapter 2—simplicity favors regularity—pays off here in specifying control.

“The control unit can set all but one of the control signals based solely on the opcode and funct fields of the instruction. The PCSrc control line is the exception.”


“this start-up and wind-down affects performance when the number of tasks is not large compared to the number of stages in the pipeline.”

“Our carefully scheduled pipeline plans would then be foiled.”

Although we could try to rely on compilers to remove all such hazards, the results would not be satisfactory. These dependences happen just too often and the delay is far too long to expect the compiler to ==rescue us from this dilemma==.

“If we cannot resolve the branch in the second stage, ==as is often the case for longer pipelines==, then we’d see an even larger slowdown if we stall on conditional branches.”


Such rigid approaches to branch prediction rely on ==stereotypical== behavior and don’t ==account for== the individuality of a specific branch instruction. Dynamic hardware predictors, ==in stark contrast==, make their guesses depending on the behavior of each conditional branch and may change predictions for a conditional branch over the life of a program.


==As in the case of== all other solutions to control hazards, longer pipelines exacerbate the problem, ==in this case by== raising the cost of misprediction.

For modern pipelines, structural hazards usually revolve around the floatingpoint unit, which may not be fully pipelined

There is less in this than meets the eye.
```
**表面上看到的比实际拥有的多。**  
或者说得更自然一点：  
👉 **事情看起来很吸引人，但实际上没那么大意义。**  
👉 **实情不如表面所见那样丰富。**

这是一句典型的英语习语（idiom），常用于揭示某种“**表里不一**”的情况。
```


“This ==walk-through== of the load instruction shows that any information needed in a later pipe stage must be passed to that stage via a pipeline register.”


“Just as store passed the register value from the ID/EX to the EX/MEM pipeline registers for use in the MEM stage, load must pass the register number ==from== the ID/EX ==through== EX/MEM ==to== the MEM/WB pipeline register for use in the WB stage.”


We start with a simple design that views the problem through rose-colored glasses.

so there is no separate write signal for the PC. By the same argument, there are no separate write signals for the pipeline registers (IF/ ID, ID/EX, EX/MEM, and MEM/WB),

It’s now time to take off the rose-colored glasses and look at what happens with real programs.

A notation that names the fields of the pipeline registers allows for a more precise notation of dependences.

Figure 4.52 shows a ==close-up== of the ALU and pipeline register before and after adding forwarding.


If the previous instruction is going to write to the register file, and the write register number matches the read register number of ALU inputs A or B, provided it is not register 0, then steer the multiplexor to pick the value instead from the pipeline register EX/MEM.