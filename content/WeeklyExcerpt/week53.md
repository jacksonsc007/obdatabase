As we said in Section 4.5, one case where forwarding cannot save the day is when an instruction tries to read a register following a load instruction that writes the same register.

The next two lines check to see if the destination register field of the load in the EX stage matches ==either source register of== the instruction in the ID stage.



Provided these registers are preserved, the instruction in the IF stage will continue to be read using the same PC,

These benign control values are percolated forward at each clock cycle with the proper effect: no registers or memories are written if the control values are all 0.


The reasons are that control hazards are relatively simple to understand, they occur less frequently than data hazards, and ==there is nothing as effective against control hazards== as forwarding is against data hazards.

To discard instructions, we merely change the original control values to 0s, ==much as we did== to stall for a load-use data hazard.

The selector can operate similarly to a 1- or 2-bit predictor, ==favoring whichever== of the two predictors has been more accurate


“A processor with imprecise exceptions might put 58hex into SEPC and ==leave it up to== the operating system to determine which instruction caused the problem.”


There are two main ways to implement a multiple-issue processor, ==with the major difference being== the division of work between the compiler and the hardware.