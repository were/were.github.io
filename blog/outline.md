# Being a Full-Stack Hacker: From ISA to Silicon

I am writing these blogs for Ph.D. students in software/hardware co-design area
to save some time of hacking the research infrastructures. Instead of learning
to the structure of each codebase from scratch, these blogs cover:
1. hints on finding the files you want to look at and modify to extend your functionality;
2. engineering tricks to improve the experience of development;
3. experiences to avoid the pitfalls in the existing codebase;
4. undocumented details to make you better understand how the origin project works.

To examplify the extension, these blogs will use my research infrasture,
[DSAGEN](https://github.com/polyarch/dsa-framework), as an paradigm of hacking.
Though my goal of research may not exactly yours (readers), I still believe
these experiences are useful and can be easily transfered.

## Contents

These blogs is stuck to the [RISC-V ISA](https://riscv.org/).

* RISCV ISA
  * [Extending the ISA](./isa.md)
* Gem5 Simulator
  * Decoder DSL
  * Execution Context
  * General-Purpose Pipeline
* LLVM
  * Extending the ISA
  * Hacking the Parser
  * Writing a Transformation Pass
* Chisel
  * TBD
* Chipyard
  * TBD

