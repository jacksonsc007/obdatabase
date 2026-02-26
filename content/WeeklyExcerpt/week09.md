Although there is some similarity between the x86 microarchitecture and PTX, ==in that== both translate to an internal form (microinstructions for x86), the difference is that this translation happens in hardware at runtime during execution on the x86 ==versus== in software and load time on a GPU.

The resulting performance sometimes ==belies== that simple abstraction.

As previously mentioned, in the ==surprisingly common== case that the individual lanes ==agree on== the predicated branch—such as branching on a parameter value that is the same for all lanes so that all active mask bits are 0s or all are 1s—the branch skips the THEN instructions or the ELSE instructions.

“Conditional execution is a case where ==GPUs do in runtime hardware what== vector architectures do at compile time.”

Although it will depend on the speed of the scalar processor versus the vector processor, the ==crossover point== when it’s better to use scalar might be when less than 20% of the mask bits are 1s.

Thus the efficiency ==with which== GPUs execute conditional statements ==comes down to== how frequently the ==branches will diverge==. For example, one calculation of eigenvalues has deep conditional nesting, but measurements of the code show that around 82% of clock cycle issues have between 29 and 32 out of the 32 mask bits set to 1, so GPUs execute this code more efficiently than ==one might expect.==

It felt like somehow Summer imagined that if she kept it light and moved on quickly, Tom woudn't be affected by it at all. Which is only a conclusion she could have come to if she, like Tom, was imagining him as the person she wanted him to be instead of who he was.
