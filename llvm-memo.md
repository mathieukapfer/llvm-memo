
source: https://jonathan2251.github.io/lbd/index.html

source: https://jonathan2251.github.io/lbd/llvmstructure.html

# processor description

## instruction

 - A (arithmetic & logic instruction
 - L load from/to memory
 - J jump

## registers

 - GPR
 - PC, LR
 - Status register

## stage of execution

 - instruction fetch
 - instruction decode
 - execution
 - cache <-> pipeline
 - pipeline <-> register

## interrupt vector
 - reset
 - error
 - interrupt

# llvm structure

## llvm = three phase compiler

 - front end        <= source code  [parser]
 - common Optimiser                 [code gen]
 - backend          => machine code [code gen]

## step 1: parser

source code => front end => IR

IR = (intermediate Representation)
   = low-level RISC-like virtual instruction set (sub, add, call, cmp, ...)
   + strongly typed with a simple type system (i32, i32*, i32**, ...)

 - uses an infinite set of temporaries named with a % character.

The optimizer isn’t constrained by either a specific source language or a specific target machine.

cmd
  *.ll => llvm-as => *.bc
  *.bc => llvm-dis => *.ll

## step 2 & 3: code gen

### LLVM’s Target Description Files: .td

### LLVM Code Generation Sequence

https://jonathan2251.github.io/lbd/llvmstructure.html#id63

- lowering
- legalization
- instruction selection
- scheduling
- SSA-based optimisation
- register allocation
- poste allocation
- pro/epilog insertion
- peehome optimisation
- assembly printing
