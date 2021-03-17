# Programming in Intrinsics

For now, we have the extended instructions integrated to the compiler infrastructure.
However, the high-level abstraction is still absent. For a quick proof of concept, manually
writing assembly code is probably a good short-term solution.

## Hardware Intrinsics

Hardware Intrinsics are essentially function wrappers of the inlined assembly code.
The format of an inlined assembly code should look like:

```
__asm__ __volatile__("mnemonic " "%0, %1, %2" : "=r"(a) : "r"(b), "i"(c) )
```

where:

1. The `"mnemonic"` is the name of the instruction;
2. `"%0, %1, %2"` is something like C-like printf/scanf, which describes the format of the arguments;
3. The strings (`"=r"`, `"r"` and `"i"`) affilicated with expressions (`a`, `b` and `c`) represents
   the values fed to this assembly instruction, where
   1. `"=r"` indicates the destination register; the expression fed to this register must be a left value;
      this **must** appear between to colons (`:`).
   2. `"r"` indicates the source register; for now, I only do `i64` integers; if a `float` or `double` is
      desired, probably we should use `reinterpret_cast`;
   3. `"i"` indicates an immediate value (constant); this value is a **signed** integer that matches the number
      of bits we discussed in last chapter; this value **must** be a compilation time constant.


You can use either macros of inlined function calls to wrap these assembly code. You can refer to
[this file](https://github.com/PolyArch/dsa-riscv-ext/blob/master/dsaintrin.h) for more details.
Here we adopt inline functions, because inlined functions allow us to setup default values for
some functions with a long argument list.


## Pitfalls to Avoid