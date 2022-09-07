## Context

To call a contract, it must be called by its address. When called, an execution context is created.
This context contains information about the current call, accessible to the contract.

### Code

The code is the bytecode located at the address receiving the call. This code contains "opcodes", or
instructions to execute. A program counter points to the instruction to execute and increments on
each instruction's execution. The program counter can be overwritten by using the
[JUMP](instruction-reference.md#jump) and [JUMPI](instruction-reference.md#jumpi) instructions.

### Calldata

The calldata is the data sent to the contract when called. It generally contains information about
which function to call and any arguments the function may need during its execution. Calldata can
not be written to, but a 32 byte word can be read from the calldata and pushed to the stack by the
[CALLDATALOAD](instruction-reference.md#calldataload) instruction and an arbitrary amount of
calldata can be copied to memory using the [CALLDATACOPY](instruction-reference.md#calldatacopy)
instruction.

Calldata, on "layer one" Ethereum is cheap, so calldata size is negligible. However, on some "layer
two" rollup solutions commit the calldata of each call to "layer one" storage, meaning calldata is
much more expensive on some "layer two" solutions.

### Returndata

Returndata is the data returned from the last external call within the current execution context.
When an external call is made, if the contract called returns any data, it will be accessible to the
current context using the [RETURNDATACOPY](instruction-reference.md#returndatacopy) instruction.
Returndata can not be written to, it can only be read from.

### Storage

Storage is persistent data storage and is the most expensive place to read and write data since this
permanently consumes memory resources of nodes until explicitly cleared. Contract storage is
essentially a hashmap where keys are mapped to values. Storage can be written using the
[SSTORE](instruction-reference.md#sstore) instruction and it can be read by using the
[SLOAD](instruction-reference.md#sload) instruction. Storage slots can only be written and read as
32 byte values.

Gas associated with storage is dynamic, in that the amount of gas consumed may differ based on the
current context. If a slot has been accessed in a given transaction, it is considered "warm", else
it is considered "cold".

### Memory

Memory is a temporary data storage location which is cleared at the end of an execution context.
It is only accessible in the currently executing context. Memory can be written with the
[MSTORE](instruction-reference.md#mstore) and [MSTORE8](instruction-reference.md#mstore8)
instructions and it can be read from with the [MLOAD](instruction-reference.md#mload) instruction.
Memory can be written to in increments of 32 bytes or eight bytes (using `MSTORE8`). Memory can also
be written to and read from by specific instructions.

The gas associated with memory is dynamic, there is a static base cost for any read or write of
memory and there is a dynamic cost that scales quadratically as memory expands. This dynamic cost is
increased not just by writing new memory but also reading previously unaccessed memory.

- [CALLDATACOPY](instruction-reference.md#calldatacopy)
- [CODECOPY](instruction-reference.md#codecopy)
- [EXTCODECOPY](instruction-reference.md#extcodecopy)
- [RETURNDATACOPY](instruction-reference.md#returndatacopy)
- [LOG0](instruction-reference.md#log0)
- [LOG1](instruction-reference.md#log1)
- [LOG2](instruction-reference.md#log2)
- [LOG3](instruction-reference.md#log3)
- [LOG4](instruction-reference.md#log4)
- [CREATE](instruction-reference.md#create)
- [CALL](instruction-reference.md#call)
- [CALLCODE](instruction-reference.md#callcode)
- [RETURN](introduction.md#return)
- [DELEGATECALL](instruction-reference.md#delegatecall)
- [CREATE2](instruction-reference.md#create2)
- [STATICCALL](instruction-reference.md#staticcall)
- [REVERT](instruction-reference.md#revert)

### Stack

The stack is also a temporary data storage location that only persists to the end of an execution
context. It is accessible only in the currently executing context. The stack can be pushed to and
popped from by nearly every instruction. It is pushed to and popped from in increments of 32 bytes.

There is no dynamic cost for expanding the stack, but there is a finite depth of 1024 words.
