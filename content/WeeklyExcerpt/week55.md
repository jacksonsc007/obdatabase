Because of the dependence, we must preserve what is called program order—that is, the order that the instructions would execute in if executed sequentially one at a time as determined by the original source program.


“The goal of both our software and hardware techniques is to exploit parallelism by preserving program order only where it affects the outcome of the program.” (Hennessy, p. 173)


“A WAR hazard occurs either when there are some instructions that write results early in the instruction pipeline and other instructions that read a source late in the pipeline, or when instructions are reordered, as we will see in this chapter.” (Hennessy, p. 174)


we must preserve what is called program order—that is, the order that the instructions would execute in if executed sequentially one at a time as determined by the original source program.


This example serves both to illustrate an important technique as well as to motivate the more powerful program transformations described in Appendix H.


In our example, we made many such changes, which to us, as human beings, were obviously allowable. In practice, this process must be performed in a methodical fashion either by a compiler or by hardware.