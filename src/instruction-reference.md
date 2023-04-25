## Instructions Reference

### Table

| opcode | name                                                      | stack input                                                   | stack output   |
| ------ | --------------------------------------------------------- | ------------------------------------------------------------- | -------------- |
| 0x00   | [STOP](instruction-reference.md#stop)                     |                                                               |                |
| 0x01   | [ADD](instruction-reference.md#add)                       | [a, b]                                                        | [a + b]        |
| 0x02   | [MUL](instruction-reference.md#mul)                       | [a, b]                                                        | [a * b]        |
| 0x03   | [SUB](instruction-reference.md#sub)                       | [a, b]                                                        | [a - b]        |
| 0x04   | [DIV](instruction-reference.md#div)                       | [a, b]                                                        | [a // b]       |
| 0x05   | [SDIV](instruction-reference.md#sdiv)                     | [a, b]                                                        | [a // b]       |
| 0x06   | [MOD](instruction-reference.md#mod)                       | [a, b]                                                        | [a % b]        |
| 0x07   | [SMOD](instruction-reference.md#smod)                     | [a, b]                                                        | [a % b]        |
| 0x08   | [ADDMOD](instruction-reference.md#addmod)                 | [a, b, c]                                                     | [(a + b) % c]  |
| 0x09   | [MULMOD](instruction-reference.md#mulmod)                 | [a, b, c]                                                     | [(a * b) % c]  |
| 0x0A   | [EXP](instruction-reference.md#exp)                       | [a, b]                                                        | [a ** b]       |
| 0x0B   | [SIGNEXTEND](instruction-reference.md#signextend)         | [b, x]                                                        | [y]            |
| 0x10   | [LT](instruction-reference.md#lt)                         | [a, b]                                                        | [a < b]        |
| 0x11   | [GT](instruction-reference.md#gt)                         | [a, b]                                                        | [a > b]        |
| 0x12   | [SLT](instruction-reference.md#slt)                       | [a, b]                                                        | [a < b]        |
| 0x13   | [SGT](instruction-reference.md#sgt)                       | [a, b]                                                        | [a > b]        |
| 0x14   | [EQ](instruction-reference.md#eq)                         | [a, b]                                                        | [a == b]       |
| 0x15   | [ISZERO](instruction-reference.md#iszero)                 | [a]                                                           | [a == 0]       |
| 0x16   | [AND](instruction-reference.md#and)                       | [a, b]                                                        | [a & b]        |
| 0x17   | [OR](instruction-reference.md#or)                         | [a, b]                                                        | [a \| b]       |
| 0x18   | [XOR](instruction-reference.md#xor)                       | [a, b]                                                        | [a ^ b]        |
| 0x19   | [NOT](instruction-reference.md#not)                       | [a]                                                           | [~a]           |
| 0x1A   | [BYTE](instruction-reference.md#byte)                     | [i, a]                                                        | [a[i]]         |
| 0x1B   | [SHL](instruction-reference.md#shl)                       | [s, a]                                                        | [a << s]       |
| 0x1C   | [SHR](instruction-reference.md#shr)                       | [s, a]                                                        | [a >> s]       |
| 0x1D   | [SAR](instruction-reference.md#sar)                       | [s, a]                                                        | [a >> s]       |
| 0x20   | [SHA3](instruction-reference.md#sha3)                     | [o, s]                                                        | [hash]         |
| 0x30   | [ADDRESS](instruction-reference.md#address)               | []                                                            | [address]      |
| 0x31   | [BALANCE](instruction-reference.md#balance)               | [address]                                                     | [balance]      |
| 0x32   | [ORIGIN](instruction-reference.md#origin)                 | []                                                            | [address]      |
| 0x33   | [CALLER](instruction-reference.md#caller)                 | []                                                            | [address]      |
| 0x34   | [CALLVALUE](instruction-reference.md#callvalue)           | []                                                            | [value]        |
| 0x35   | [CALLDATALOAD](instruction-reference.md#calldataload)     | [i]                                                           | [calldata[i]]  |
| 0x36   | [CALLDATASIZE](instruction-reference.md#calldatasize)     | []                                                            | [size]         |
| 0x37   | [CALLDATACOPY](instruction-reference.md#calldatacopy)     | [destoffset, offset, size]                                    | []             |
| 0x38   | [CODESIZE](instruction-reference.md#codesize)             | []                                                            | [size]         |
| 0x39   | [CODECOPY](instruction-reference.md#codecopy)             | [destoffset, offset, size]                                    | []             |
| 0x3A   | [GASPRICE](instruction-reference.md#gasprice)             | [price]                                                       | []             |
| 0x3B   | [EXTCODESIZE](instruction-reference.md#extcodesize)       | [address]                                                     | [size]         |
| 0x3C   | [EXTCODECOPY](instruction-reference.md#extcodecopy)       | [address, destoffset, offset, size]                           | []             |
| 0x3D   | [RETURNDATASIZE](instruction-reference.md#returndatasize) | []                                                            | [size]         |
| 0x3E   | [RETURNDATACOPY](instruction-reference.md#returndatacopy) | [destoffset, offset, size]                                    | []             |
| 0x3F   | [EXTCODEHASH](instruction-reference.md#extcodehash)       | [address]                                                     | [size]         |
| 0x40   | [BLOCKHASH](instruction-reference.md#blockhash)           | [blocknumber]                                                 | [hash]         |
| 0x41   | [COINBASE](instruction-reference.md#coinbase)             | []                                                            | [address]      |
| 0x42   | [TIMESTAMP](instruction-reference.md#timestamp)           | []                                                            | [timestamp]    |
| 0x43   | [NUMBER](instruction-reference.md#number)                 | []                                                            | [blocknumber]  |
| 0x44   | [PREVRANDAO](instruction-reference.md#prevrandao)         | []                                                            | [random]       |
| 0x45   | [GASLIMIT](instruction-reference.md#gaslimit)             | []                                                            | [gaslimit]     |
| 0x46   | [CHAINID](instruction-reference.md#chainid)               | []                                                            | [chainid]      |
| 0x47   | [SELFBALANCE](instruction-reference.md#selfbalance)       | []                                                            | [balance]      |
| 0x48   | [BASEFEE](instruction-reference.md#basefee)               | []                                                            | [basefee]      |
| 0x50   | [POP](instruction-reference.md#pop)                       | [a]                                                           | []             |
| 0x51   | [MLOAD](instruction-reference.md#mload)                   | [offset]                                                      | [value]        |
| 0x52   | [MSTORE](instruction-reference.md#mstore)                 | [offset, value]                                               | []             |
| 0x53   | [MSTORE8](instruction-reference.md#mstore8)               | [offset, value]                                               | []             |
| 0x54   | [SLOAD](instruction-reference.md#sload)                   | [slot]                                                        | [value]        |
| 0x55   | [SSTORE](instruction-reference.md#sstore)                 | [slot, value]                                                 | []             |
| 0x56   | [JUMP](instruction-reference.md#jump)                     | [counter]                                                     | []             |
| 0x57   | [JUMPI](instruction-reference.md#jumpi)                   | [counter, bool]                                               | []             |
| 0x58   | [PC](instruction-reference.md#pc)                         | []                                                            | [counter]      |
| 0x59   | [MSIZE](instruction-reference.md#msize)                   | []                                                            | [size]         |
| 0x5A   | [GAS](instruction-reference.md#gas)                       | []                                                            | [gasleft]      |
| 0x5B   | [JUMPDEST](instruction-reference.md#jumpdest)             | []                                                            | []             |
| 0x5F   | [PUSH0](instruction-reference.md#push0)                   | []                                                            | [zero]         |
| 0x60   | [PUSH1](instruction-reference.md#push1)                   | []                                                            | [value]        |
| 0x61   | [PUSH2](instruction-reference.md#push2)                   | []                                                            | [value]        |
| 0x62   | [PUSH3](instruction-reference.md#push3)                   | []                                                            | [value]        |
| 0x63   | [PUSH4](instruction-reference.md#push4)                   | []                                                            | [value]        |
| 0x64   | [PUSH5](instruction-reference.md#push5)                   | []                                                            | [value]        |
| 0x65   | [PUSH6](instruction-reference.md#push6)                   | []                                                            | [value]        |
| 0x66   | [PUSH7](instruction-reference.md#push7)                   | []                                                            | [value]        |
| 0x67   | [PUSH8](instruction-reference.md#push8)                   | []                                                            | [value]        |
| 0x68   | [PUSH9](instruction-reference.md#push9)                   | []                                                            | [value]        |
| 0x69   | [PUSH10](instruction-reference.md#push10)                 | []                                                            | [value]        |
| 0x6A   | [PUSH11](instruction-reference.md#push11)                 | []                                                            | [value]        |
| 0x6B   | [PUSH12](instruction-reference.md#push12)                 | []                                                            | [value]        |
| 0x6C   | [PUSH13](instruction-reference.md#push13)                 | []                                                            | [value]        |
| 0x6D   | [PUSH14](instruction-reference.md#push14)                 | []                                                            | [value]        |
| 0x6E   | [PUSH15](instruction-reference.md#push15)                 | []                                                            | [value]        |
| 0x6F   | [PUSH16](instruction-reference.md#push16)                 | []                                                            | [value]        |
| 0x70   | [PUSH17](instruction-reference.md#push17)                 | []                                                            | [value]        |
| 0x71   | [PUSH18](instruction-reference.md#push18)                 | []                                                            | [value]        |
| 0x72   | [PUSH19](instruction-reference.md#push19)                 | []                                                            | [value]        |
| 0x73   | [PUSH20](instruction-reference.md#push20)                 | []                                                            | [value]        |
| 0x74   | [PUSH21](instruction-reference.md#push21)                 | []                                                            | [value]        |
| 0x75   | [PUSH22](instruction-reference.md#push22)                 | []                                                            | [value]        |
| 0x76   | [PUSH23](instruction-reference.md#push23)                 | []                                                            | [value]        |
| 0x77   | [PUSH24](instruction-reference.md#push24)                 | []                                                            | [value]        |
| 0x78   | [PUSH25](instruction-reference.md#push25)                 | []                                                            | [value]        |
| 0x79   | [PUSH26](instruction-reference.md#push26)                 | []                                                            | [value]        |
| 0x7A   | [PUSH27](instruction-reference.md#push27)                 | []                                                            | [value]        |
| 0x7B   | [PUSH28](instruction-reference.md#push28)                 | []                                                            | [value]        |
| 0x7C   | [PUSH29](instruction-reference.md#push29)                 | []                                                            | [value]        |
| 0x7D   | [PUSH30](instruction-reference.md#push30)                 | []                                                            | [value]        |
| 0x7E   | [PUSH31](instruction-reference.md#push31)                 | []                                                            | [value]        |
| 0x7F   | [PUSH32](instruction-reference.md#push32)                 | []                                                            | [value]        |
| 0x80   | [DUP1](instruction-reference.md#dup1)                     | [a]                                                           | [a, a]         |
| 0x81   | [DUP2](instruction-reference.md#dup2)                     | [a, b]                                                        | [b, a, b]      |
| 0x82   | [DUP3](instruction-reference.md#dup3)                     | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x83   | [DUP4](instruction-reference.md#dup4)                     | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x84   | [DUP5](instruction-reference.md#dup5)                     | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x85   | [DUP6](instruction-reference.md#dup6)                     | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x86   | [DUP7](instruction-reference.md#dup7)                     | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x87   | [DUP8](instruction-reference.md#dup8)                     | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x88   | [DUP9](instruction-reference.md#dup9)                     | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x89   | [DUP10](instruction-reference.md#dup10)                   | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x8A   | [DUP11](instruction-reference.md#dup11)                   | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x8B   | [DUP12](instruction-reference.md#dup12)                   | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x8C   | [DUP13](instruction-reference.md#dup13)                   | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x8D   | [DUP14](instruction-reference.md#dup14)                   | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x8E   | [DUP15](instruction-reference.md#dup15)                   | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x8F   | [DUP16](instruction-reference.md#dup16)                   | [a, ..., b]                                                   | [b, a, ..., b] |
| 0x90   | [SWAP1](instruction-reference.md#swap1)                   | [a, b,                                                        | [b, a]         |
| 0x91   | [SWAP2](instruction-reference.md#swap2)                   | [a, b, c]                                                     | [c, b, a]      |
| 0x92   | [SWAP3](instruction-reference.md#swap3)                   | [a, ..., b]                                                   | [b, ..., a]    |
| 0x93   | [SWAP4](instruction-reference.md#swap4)                   | [a, ..., b]                                                   | [b, ..., a]    |
| 0x94   | [SWAP5](instruction-reference.md#swap5)                   | [a, ..., b]                                                   | [b, ..., a]    |
| 0x95   | [SWAP6](instruction-reference.md#swap6)                   | [a, ..., b]                                                   | [b, ..., a]    |
| 0x96   | [SWAP7](instruction-reference.md#swap7)                   | [a, ..., b]                                                   | [b, ..., a]    |
| 0x97   | [SWAP8](instruction-reference.md#swap8)                   | [a, ..., b]                                                   | [b, ..., a]    |
| 0x98   | [SWAP9](instruction-reference.md#swap9)                   | [a, ..., b]                                                   | [b, ..., a]    |
| 0x99   | [SWAP10](instruction-reference.md#swap10)                 | [a, ..., b]                                                   | [b, ..., a]    |
| 0x9A   | [SWAP11](instruction-reference.md#swap11)                 | [a, ..., b]                                                   | [b, ..., a]    |
| 0x9B   | [SWAP12](instruction-reference.md#swap12)                 | [a, ..., b]                                                   | [b, ..., a]    |
| 0x9C   | [SWAP13](instruction-reference.md#swap13)                 | [a, ..., b]                                                   | [b, ..., a]    |
| 0x9D   | [SWAP14](instruction-reference.md#swap14)                 | [a, ..., b]                                                   | [b, ..., a]    |
| 0x9E   | [SWAP15](instruction-reference.md#swap15)                 | [a, ..., b]                                                   | [b, ..., a]    |
| 0x9F   | [SWAP16](instruction-reference.md#swap16)                 | [a, ..., b]                                                   | [b, ..., a]    |
| 0xA0   | [LOG0](instruction-reference.md#log0)                     | [offset, size]                                                | []             |
| 0xA1   | [LOG1](instruction-reference.md#log1)                     | [offset, size, topic1]                                        | []             |
| 0xA2   | [LOG2](instruction-reference.md#log2)                     | [offset, size, topic1, topic2]                                | []             |
| 0xA3   | [LOG3](instruction-reference.md#log3)                     | [offset, size, topic1, topic2, topic3]                        | []             |
| 0xA4   | [LOG4](instruction-reference.md#log4)                     | [offset, size, topic1, topic2, topic3, topic4]                | []             |
| 0xF0   | [CREATE](instruction-reference.md#create)                 | [value, offset, size]                                         | [address]      |
| 0xF1   | [CALL](instruction-reference.md#call)                     | [gas, address, value, argoffset, argsize, retoffset, retsize] | [success]      |
| 0xF2   | [CALLCODE](instruction-reference.md#callcode)             | [gas, address, value, argoffset, argsize, retoffset, retsize] | [success]      |
| 0xF3   | [RETURN](instruction-reference.md#return)                 | [offset, size]                                                | []             |
| 0xF4   | [DELEGATECALL](instruction-reference.md#delegatecall)     | [gas, address, argoffset, argsize, retoffset, retsize]        | [success]      |
| 0xF5   | [CREATE2](instruction-reference.md#create2)               | [value, offset, size, salt]                                   | [address]      |
| 0xFA   | [STATICCALL](instruction-reference.md#staticcall)         | [gas, address, argoffset, argsize, retoffset, retsize]        | [success]      |
| 0xFD   | [REVERT](instruction-reference.md#revert)                 | [offset, size]                                                | []             |
| 0xFE   | [INVALID](instruction-reference.md#invalid)               | []                                                            | []             |
| 0xFF   | [SELFDESTRUCT](instruction-reference.md#selfdestruct)     | [address]                                                     | []             |

### Reference

---


#### STOP

Exits the current context successfully.

When a call is executed on an address without code, the EVM returns `0x00` data which halts
execution.

[[Back to top]](instruction-reference.md#instructions-reference)


#### ADD

Pops two values from the stack, adds them, then pushes the result to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000003 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### MUL

Pops two values from the stack, multiplies them, then pushes the result to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000003 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000006 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SUB

Pops two values from the stack, subtracts the second value from the first, then pushes the result to
the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DIV

Pops two values from the stack, divides the first value by the second, rounds toward zero, then
pushes the result to the stack.

> Note: The `DIV` opcode does NOT revert on a divide-by-zero, it will simply push zero to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000004 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SDIV

Pops two values from the stack, divides the first value by the second, rounds toward zero, then
pushes the result to the stack.

The `SDIV` opcode treats all values as two's complement, signed 256 bit integers.

> Note: The `SDIV` opcode does NOT revert on a divide-by-zero, it will simply push zero to the
> stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFE |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### MOD

Pops two values from the stack, divides the first value by the second, then pushes the remainder to
the stack.

> Note: The `MOD` opcode does NOT revert when the denominator is zero, it will simply push zero to
> the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000005 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SMOD

Pops two values from the stack, divides the first value by the second, then pushes the remainder to
the stack.

The `SMOD` opcode treats all values as two's complement, signed 256 bit integers.

> Note: The `SMOD` opcode does NOT revert when the denominator is zero, it will simply push zero to
> the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF8 |
| 1     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFD |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFE |

[[Back to top]](instruction-reference.md#instructions-reference)


#### ADDMOD

Pops three values from the stack, adds the first two, divides the sum by the third, then pushes the
remainder of the division to the stack.

> Note: The `ADDMOD` opcode does NOT revert when the denominator is zero, it will simply push zero
> to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000003 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000002 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### MULMOD

Pops three values from the stack, multiplies the first two, divides the product by the third, then
pushes the remainder of the division to the stack.

> Note: The `MULMOD` opcode does NOT revert when the denominator is zero, it will simply push zero
> to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000003 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000003 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### EXP

Pops two values from the stack, the first value is raised to the power of the second value, then the
result is pushed to the stack.

> Note: If the `EXP` opcode output overflows, the remainder of the result modulo 2^256 will be
> pushed to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000003 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000009 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SIGNEXTEND

Pops two values from the stack, the first value specifies a number of bytes minus one, the second
value is a number whose left-most bit within the number of bytes is repeated to the remaining bits
in the 32 byte word.

This is used as a way to take a two's complement signed integer and extend its sign to the left-most
bit in a 32 byte word.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x00000000000000000000000000000000000000000000000000000000000000FF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### LT

Pops two values from the stack and checks if the first value is less than the second value. It pushes
one to the stack if the first value is less than the second or it pushes zero to the stack if not.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### GT

Pops two values from the stack and checks if the first value is greater than the second value. It
pushes one to the stack if the first value is less than the second or it pushes zero to the stack if
not.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SLT

Pops two values from the stack and checks if the first value is less than the second value. It pushes
one to the stack if the first value is less than the second or it pushes zero to the stack if not.

The `SLT` opcode treats all values as two's complement, signed 256 bit integers.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SGT

Pops two values from the stack and checks if the first value is greater than the second value. It
pushes one to the stack if the first value is less than the second or it pushes zero to the stack if
not.

The `SGT` opcode treats all values as two's complement, signed 256 bit integers.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### EQ

Pops two values from the stack and checks if the values are equal. It pushes one to the stack if the
values are equal or it pushes zero to the stack if not.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### ISZERO

Pops one value from the stack and pushes one if the value is zero or it pushes zero if the value is
non-zero.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### AND

Pops two values from the stack and pushes the result of a bitwise `AND` operation of the two values.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000011 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### OR

Pops two values from the stack and pushes the result of a bitwise `OR` operation of the two values.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000010 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000011 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### XOR

Pops two values from the stack and pushes the result of a bitwise `XOR` operation of the two values.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000011 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000010 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### NOT

Pops one value from the stack and pushes the result of a bitwise `NOT` operation of the value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000FF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### BYTE

Pops two values from the stack and uses the first value as an index of which byte to extract from the
second value then pushes the extracted byte to the stack.

> Note: The `BYTE` opcode does not revert when the first value is out of range, it will simply push
> zero to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000AABBCC |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000BB |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SHL

Pops two values from the stack and bitwise shifts the second value to the left a number of bits equal
to the first value and pushes the result to the stack.

> Note: The `SHL` opcode does not revert if the "shift" value is greater than 255, it will simply
> push zero to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000008 |
| 1     | 0x00000000000000000000000000000000000000000000000000000000000000FF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000000000000000FF00 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SHR

Pops two values from the stack and bitwise shifts the second value to the right a number of bits
equal to the first value and pushes the result to the stack.

> Note: The `SHR` opcode does not revert if the "shift" value is greater than 255, it will simply
> push zero to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000008 |
| 1     | 0x000000000000000000000000000000000000000000000000000000000000FF00 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000FF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SAR

Pops two values from the stack and bitwise shifts the second value to the right a number of bits
equal to the first value and pushes the result to the stack.

The `SAR` opcode treats the second value as a two's complement signed 256 bit integer. Any new bits
are set to zero if the previous value was positive or they are set to one if the previous value was
negative.

> Note: The `SAR` opcode does not revert if the "shift" value is greater than 255, it will simply
> push zero to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000008 |
| 1     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SHA3

Pops two values from the stack and uses the Keccak-256 algorithm to hash data from memory starting at
an offset equal to the first value and with a length specified by the second value then pushes the
hash digest to the stack.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFF00000000000000000000000000000000000000000000000000000000 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000004 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x29045A592007D0C246EF02C2223570DA9522D0CF0F73282C79A1BC8F0BB2C238 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### ADDRESS

Pushes the address of the currently executing contract to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### BALANCE

Pops one value from the stack, treats it as an address, and pushes the balance of the address in wei
to the stack.

> Note: The `BALANCE` opcode does not revert if the account does not exist, it simply pushes zero to
> the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### ORIGIN

Pushes the address of the transaction sender to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CALLER

Pushes the address of the account that called the current execution context to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CALLVALUE

Pushes the value of the current call in wei to the stack

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CALLDATALOAD

Pops one value from the stack and uses it as an offset in calldata from which a 32 byte word is
loaded and pushes onto the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xf8a8fd6d00000000000000000000000000000000000000000000000000000000 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CALLDATASIZE

Pushes the size of the current calldata, in bytes, to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000004 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CALLDATACOPY

Pops three values from the stack and treats the first as an offset in memory to copy calldata to, the
second value as the offset in the calldata to copy, and the third as the size of the calldata to
copy.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Memory After:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xBB29998E000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CF |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000020 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CODESIZE

Pushes the size of the code in the currently executing contract, in bytes, to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

Stack Output:


| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CODECOPY

Pops three values from the stack and treats the first as an offset in memory to copy the current
contract's code starting at an offset equal to the second value and with a size equal to the third
value.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Memory After:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000060 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### GASPRICE

Pushes the current price, in wei, per gas of the current transaction to the stack.

Stack Output:


| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000FF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### EXTCODESIZE

Pops an address from the stack and pushes the size of the code at the provided address.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000C02AAA39B223FE8D0A0E5C4F27EAD9083C756CC2 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000C34 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### EXTCODECOPY

Pops four values from the stack, takes the first value as an address, the second value as an
offset in memory, the third value as an offset in the external address's bytecode, and the fourth
value as a size, in bytes, and copies the external code into memory.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Memory After:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000060 |


| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000C02AAA39B223FE8D0A0E5C4F27EAD9083C756CC2 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### RETURNDATASIZE

Pushes the size of the return data from the previous external call to the stack.

> Note: The `RETURNDATASIZE` opcode does not revert if no external calls have been executed in the
> current context, it will simply push zero to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### RETURNDATACOPY

Pops three values from the stack, takes the first value as an offset in memory, the second value as
an offset in returndata, and the third as a size, in bytes, of returndata, then copies the
returndata to memory with these parameters.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Memory After:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000060 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### EXTCODEHASH

Pops an address from the stack and pushes the Keccak-256 hash digest of the code at that address to
the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000C02AAA39B223FE8D0A0E5C4F27EAD9083C756CC2 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xD0A06B12AC47863B5C7BE4185C2DEAAD1C61557033F56C7D4EA74429CBB25E23 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### BLOCKHASH

Pops a block number from the stack and pushes the Keccak-256 hash digeset of the block to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xD4E56740F876AEF8C010B86A40D5F56745A118D0906A34E69AEC8C0DB1CB8FA3 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### COINBASE

Pushes the address of the current transaction's miner to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### TIMESTAMP

Pushes the timestamp of the current context's block to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000080 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### NUMBER

Pushes the number of the current transaction's block to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000040000 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PREVRANDAO

Pushes a psuedorandom number to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000000270f4ed4e3000 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### GASLIMIT

Pushes the gas limit of the current transaction to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000FFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CHAINID

Pushes the id of the current chain to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SELFBALANCE

Pushes the balance, in wei, of the address of the current execution context to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### BASEFEE

Pushes the base fee, in wei, of the current transaction to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000010 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### POP

Pops a single value from the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### MLOAD

Pops a value from the stack and uses its value as a start index to load 32 bytes from memory and
pushes the memory slot to the stack.

Memory:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### MSTORE

Pops two values from the stack and stores the second value in memory at an offset equal to the first
value.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Memory After:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### MSTORE8

Pops two values from the stack and stores in memory the least-significant byte of the second value at
a memory offset of the first value.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Memory After:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000BB |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x000000000000000000000000000000000000000000000000000000000000AABB |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SLOAD

Pops a value from the stack and uses it as a slot index in persistent storage from which a 32 byte
value is loaded and pushed to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SSTORE

Pops two values from the stack and stores the second value in persistent storage at a slot index
equal to the first value.

Storage After:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### JUMP

Pops a value from the stack and writes the value to the current program counter.

> Note: The `JUMPI` opcode requires that the first stack value points to a byte in the current
> contract's bytecode that is explicitly `0x5b`. For more, read `JUMPDEST`.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Progam Counter After: 1

[[Back to top]](instruction-reference.md#instructions-reference)


#### JUMPI

Pops two values from the stack and writes the first value to the program counter if the second value
is not zero. Otherwise the program counter continues incrementing.

> Note: The `JUMPI` opcode requires that the first stack value points to a byte in the current
> contract's bytecode that is explicitly `0x5b`. For more, read `JUMPDEST`.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Progam Counter After: 2

[[Back to top]](instruction-reference.md#instructions-reference)


#### PC

Pushes the current program counter value to the stack. The value is the program counter _before_ it
is incremented.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### MSIZE

Pushes the current memory size in bytes rounded up to the next 32 byte increment to the stack.

> Note: The `MSIZE` opcode size includes not just the size of memory written. This means even if
> memory has not been written to, calling `MLOAD` on the first slot of memory will make the `MSIZE`
> be 32 (`0x20`).

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### GAS

Pushes the gas remaining after this instruction's execution to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000100 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### JUMPDEST

This does not affect the execution context, nor does it execute an instruction. This serves as the
byte that a `JUMP` or `JUMPI` instruction should write the program counter to.

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH0

Pushes a zero-value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |


#### PUSH1

Pads a one byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000FF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH2

Pads a two byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000000000000000FFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH3

Pads a three byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000FFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH4

Pads a four byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000FFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH5

Pads a five byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000000000FFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH6

Pads a six byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000FFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH7

Pads a seven byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000FFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH8

Pads an eight byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000FFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH9

Pads a nine byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000FFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH10

Pads a 10 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH11

Pads an 11 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH12

Pads a 12 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH13

Pads a 13 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH14

Pads a 14 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH15

Pads a 15 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH16

Pads a 16 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH17

Pads a 17 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH18

Pads an 18 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH19

Pads a 19 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH20

Pads a 20 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH21

Pads a 21 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH22

Pads a 22 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH23

Pads a 23 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH24

Pads a 24 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH25

Pads a 25 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH26

Pads a 26 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH27

Pads a 27 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH28

Pads a 28 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH29

Pads a 29 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH30

Pads a 30 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH31

Pads a 31 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### PUSH32

Pushes a 32 byte value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP1

Duplicates the first value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP2

Duplicates the second value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP3

Duplicates the third value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP4

Duplicates the fourth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP5

Duplicates the fifth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP6

Duplicates the sixth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP7

Duplicates the seventh value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP8

Duplicates the eighth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP9

Duplicates the ninth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP10

Duplicates the tenth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP11

Duplicates the eleventh value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP12

Duplicates the twelfth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP13

Duplicates the thirteenth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 13    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP14

Duplicates the fourteenth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 13    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 13    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 14    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP15

Duplicates the fifteenth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 13    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 14    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 13    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 14    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 15    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### DUP16

Duplicates the sixteenth value on the stack and pushes it to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 13    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 14    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 15    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 12    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 13    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 14    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 15    | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 16    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP1

Swaps the top stack value with the next first value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP2

Swaps the top stack value with the next second value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP3

Swaps the top stack value with the next third value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP4

Swaps the top stack value with the next fourth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP5

Swaps the top stack value with the next fifth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP6

Swaps the top stack value with the next sixth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP7

Swaps the top stack value with the next seventh value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP8

Swaps the top stack value with the next eighth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP9

Swaps the top stack value with the next ninth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP10

Swaps the top stack value with the next tenth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP11

Swaps the top stack value with the next eleventh value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP12

Swaps the top stack value with the next twelfth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP13

Swaps the top stack value with the next thirteenth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 12    | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 12    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP14

Swaps the top stack value with the next fourteenth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 12    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 13    | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 12    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 13    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP15

Swaps the top stack value with the next fifteenth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 12    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 13    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 14    | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 12    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 13    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 14    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### SWAP16

Swaps the top stack value with the next sixteenth value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 12    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 13    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 14    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 15    | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 2     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 3     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 4     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 5     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 6     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 7     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 8     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 9     | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 10    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 11    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 12    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 13    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 14    | 0xAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA |
| 15    | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

[[Back to top]](instruction-reference.md#instructions-reference)


#### LOG0

Pops two values from the stack, treats the first value as a memory offset and the second as the size
in memory of data to log. The `LOG0` opcode does not log indexed topics.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000020 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### LOG1

Pops three values from the stack, treats the first as a memory offset, the second as the data size in
memory, and the third as an indexed topic.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000020 |
| 2     | 0x63A242A632EFE33C0E210E04E4173612A17EFA4F16AA4890BC7E46CAECE80DE0 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### LOG2

Pops four values from the stack, treats the first as a memory offset, the second as the data size in
memory, the third as the first indexed topic, and the fourth as the second indexed topic.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000020 |
| 2     | 0xE1FFFCC4923D04B559F4D29A8BFC6CDA04EB5B0D3C460751C2402C5C5CC9109C |
| 3     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### LOG3

Pops five values from the stack, treats the first as a memory offset, the second as a data size in
memory, the third as the first indexed topic, the fourth as the second indexd topic, and the fifth
as the third indexed topic.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000020 |
| 2     | 0xDDF252AD1BE2C89B69C2B068FC378DAA952BA7F163C4A11628F55A4DF523B3EF |
| 3     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |
| 4     | 0x000000000000000000000000070997970C51812DC3A010C7D01B50E0D17DC7C8 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### LOG4

Pops six values from the stack, treats the first as a memory offset, the second as a data size in
memory, the third as the first indexed topic, the fourth as the second indexd topic, the fifth as
the third indexed topic, and the sixth as the fourth indexed topic.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000020 |
| 2     | 0xDDF252AD1BE2C89B69C2B068FC378DAA952BA7F163C4A11628F55A4DF523B3EF |
| 3     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |
| 4     | 0x000000000000000000000000070997970C51812DC3A010C7D01B50E0D17DC7C8 |
| 5     | 0x30A730F7C2718BBCFA3DC40523A288A6D5F802C1EF75116EB0F42B241318A159 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CREATE

Pops three values from the stack, treats the first as a value, in Ether, to send to the constructor
of the contract to be created, the second as an offset in memory where the future contract's
bytecode is stored, and the third as the size, in bytes of the contract to be deployed. It then
deploys the contract, executing the initialization code, and pushes the resulting address to the
stack.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x60000FF000000000000000000000000000000000000000000000000000000000 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000003 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000043A61F3F4C73EA0D444C5C1C1A8544067A86219B |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CALL

Pops seven values from the stack. The first value is the amount of gas to forward, the second is the
address to which the external call will be made, the third is the value, in wei, to send with the
call, the fourth is an offset in memory at which the intended calldata starts, the fifth is the size
of the intended calldata, the sixth is an offset in memory to which the returned data should be
copied, and the seventh is the size of the returned data to copy into memory. After the external
call is made, if the call did not revert, a one is pushed to the stack, else a zero is pushed to the
stack.

> Note: If the returned data size is unknown or may change, it is recommended to set both the sixth
> and seventh arguments to zero, then copy the returned data to memory with the `RETURNDATASIZE` and
> `RETURNDATACOPY` opcodes after the call.

> Note: If the first argument (gas) is greater than (`63 / 64`) of the remaining gas, the gas to be
> forwarded will default to (`63 / 64 * gas`) at no additional runtime cost. This behavior started
> after the "Tangerine Whistle" fork.

> Note: If the target address has no code, it will not execute code, it will simply push "true" to
> the stack.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xA9059CBB000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CF |
| 1     | 0xFFB922660000000000000000000000000000000000000000000000000DE0B6B3 |
| 2     | 0xA764000000000000000000000000000000000000000000000000000000000000 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000FFFFFFFFADF5 |
| 1     | 0x000000000000000000000000C02AAA39B223FE8D0A0E5C4F27EAD9083C756CC2 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000044 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CALLCODE

> WARNING: This opcode has a bug that does not preserve `msg.sender` and `msg.value`. Use the
> `DELEGATECALL` opcode instead.

Pops seven values from the stack. The first value is the amount of gas to forward, the second is the
address to which the external call will be made, the third is the value, in wei, to send with the
call, the fourth is an offset in memory at which the intended calldata starts, the fifth is the size
of the intended calldata, the sixth is an offset in memory to which the returned data should be
copied, and the seventh is the size of the returned data to copy into memory. After the external
call is made, if the call did not revert, a one is pushed to the stack, else a zero is pushed to the
stack.

A key difference between `CALL` and `CALLCODE` is the `CALLCODE` opcode creates a new sub conext,
but it uses the logic of the target address and the storage of the contract that calls the opcode.

> Note: If the returned data size is unknown or may change, it is recommended to set both the sixth
> and seventh arguments to zero, then copy the returned data to memory with the `RETURNDATASIZE` and
> `RETURNDATACOPY` opcodes after the call.

> Note: If the first argument (gas) is greater than (`63 / 64`) of the remaining gas, the gas to be
> forwarded will default to (`63 / 64 * gas`) at no additional runtime cost. This behavior started
> after the "Tangerine Whistle" fork.

> Note: If the target address has no code, it will not execute code, it will simply push "true" to
> the stack.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xA9059CBB000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CF |
| 1     | 0xFFB922660000000000000000000000000000000000000000000000000DE0B6B3 |
| 2     | 0xA764000000000000000000000000000000000000000000000000000000000000 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000FFFFFFFFADF5 |
| 1     | 0x000000000000000000000000C02AAA39B223FE8D0A0E5C4F27EAD9083C756CC2 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000044 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 6     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### RETURN

Pops two values from the stack, treats the first as an offset in memory and the second as the size
of the data in memory to return. This exits the current context and the chunk of memory is returned
to the caller as "returndata".

[[Back to top]](instruction-reference.md#instructions-reference)


#### DELEGATECALL

Pops six values from the stack. The first value is the amount of gas to forward, the second is the
address to which the external call will be made, the third is an offset in memory at which the
intended calldata starts, the fourth is the size of the calldata, in bytes, the fifth is an offset
in memory to which the returned data should be copied, and the sixth is the expected size of the
returned data. After the external call is made, if the call did not revert, a one is pushed to the
stack, else a zero is pushed to the stack.

A key difference between `CALL` and `DELEGATECALL` is the `DELEGATECALL` opcode creates a new sub
context, but it uses the logic of the target address and the storage of the contract that calls the
opcode.

> Note: If the returned data size is unknown or may change, it is recommended to set both the sixth
> and seventh arguments to zero, then copy the returned data to memory with the `RETURNDATASIZE` and
> `RETURNDATACOPY` opcodes after the call.

> Note: If the first argument (gas) is greater than (`63 / 64`) of the remaining gas, the gas to be
> forwarded will default to (`63 / 64 * gas`) at no additional runtime cost. This behavior started
> after the "Tangerine Whistle" fork.

> Note: If the target address has no code, it will not execute code, it will simply push "true" to
> the stack.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xA9059CBB000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CF |
| 1     | 0xFFB922660000000000000000000000000000000000000000000000000DE0B6B3 |
| 2     | 0xA764000000000000000000000000000000000000000000000000000000000000 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000FFFFFFFFADF5 |
| 1     | 0x000000000000000000000000C02AAA39B223FE8D0A0E5C4F27EAD9083C756CC2 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000044 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### CREATE2

Pops four values from the stack. The first is the value, in wei, to send to the contract's
constructor, the second is an offset in memory where the bytecode to deploy starts, the third is the
size of the bytecode to deploy, and the fourth is a 32 byte salt value to facilitate deterministic
addresses on deployment. It then deploys the contract, executing the initialization code, and
pushing the resulting address to the stack.

> Note: To precompute the address, use the following formula:
> `address = keccak256(0xff + sender_address + salt + keccak256(init_code))[12:]`

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x3DFF000000000000000000000000000000000000000000000000000000000000 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000020 |
| 4     | 0x00000000000000000000000000000000000000000000000000000000000000FF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### STATICCALL

Pops six values from the stack. The first value is the amount of gas to forward, the second is the
address to which the external call will be made, the third is an offset in memory at which the
intended calldata starts, the fourth is the size of the calldata, in bytes, the fifth is an offset
in memory to which the returned data should be copied, and the sixth is the expected size of the
returned data. After the external call is made, if the call did not revert, a one is pushed to the
stack, else a zero is pushed to the stack.

A key difference between `CALL` and `STATICCALL` is the `STATICCALL` opcode will revert if any
changes to the global state occur during the execution of the sub context.

> Note: If the returned data size is unknown or may change, it is recommended to set both the sixth
> and seventh arguments to zero, then copy the returned data to memory with the `RETURNDATASIZE` and
> `RETURNDATACOPY` opcodes after the call.

> Note: If the first argument (gas) is greater than (`63 / 64`) of the remaining gas, the gas to be
> forwarded will default to (`63 / 64 * gas`) at no additional runtime cost. This behavior started
> after the "Tangerine Whistle" fork.

> Note: If the target address has no code, it will not execute code, it will simply push "true" to
> the stack.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xA9059CBB000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CF |
| 1     | 0xFFB9226600000000000000000000000000000000000000000000000000000000 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000FFFFFFFFADF5 |
| 1     | 0x000000000000000000000000C02AAA39B223FE8D0A0E5C4F27EAD9083C756CC2 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 3     | 0x0000000000000000000000000000000000000000000000000000000000000024 |
| 4     | 0x0000000000000000000000000000000000000000000000000000000000000040 |
| 5     | 0x0000000000000000000000000000000000000000000000000000000000000020 |

Memory After:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xA9059CBB000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CF |
| 1     | 0xFFB9226600000000000000000000000000000000000000000000000000000000 |
| 2     | 0x000000000000000000000000000000000000000000000000000000000FFFFFFF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### REVERT

Pops two values from the stack. The first is an offset in memory containing revert data and the
second is the size of the revert data. It then reverts any changes in the current context, returning
the revert data from memory to the caller.

Memory Before:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x4E487B7100000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000100000000000000000000000000000000000000000000000000000000 |

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000024 |

[[Back to top]](instruction-reference.md#instructions-reference)


#### INVALID

Does not interact with the stack, it is guaranteed to always be an invalid instruction that reverts
with no return data and consumes all of the gas in the current context.

[[Back to top]](instruction-reference.md#instructions-reference)


#### SELFDESTRUCT

Pops one value from the stack, which is a target address. The current contract is then destroyed and
the Ether (if any) in the contract is sent to the target address at the end of the transaction.

> Note: Since the transfer CANNOT fail, it will not execute any of the target address's logic. Any
> contracts that require the Ether balance to be accurate may be exploitable with this opcode.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 1     | 0x000000000000000000000000C02AAA39B223FE8D0A0E5C4F27EAD9083C756CC2 |

[[Back to top]](instruction-reference.md#instructions-reference)

