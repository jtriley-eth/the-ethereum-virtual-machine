## Instructions Reference

### Table

| opcode | name                                    | stack input | stack output |
| ------ | --------------------------------------- | ----------- | ------------ |
| 0x00   | [STOP](./instruction-reference.md#stop) |             |              |
| 0x01   | [ADD](./instruction-reference.md#add)   | [a, b]      | [a + b]      |

### Reference


#### STOP

Exits the current context successfully.

When a call is executed on an address without code, the EVM returns `0x00` data which halts
execution.


#### ADD

Pops two values off the stack, adds them, then pushes the result to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000002 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000003 |


#### MUL

Pops two values off the stack, multiplies them, then pushes the result to the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000002 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000003 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000006 |


#### SUB

Pops two values off the stack, subtracts the second value from the first, then pushes the result to
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


#### DIV

Pops two values off the stack, divides the first value by the second, rounds toward zero, then
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


#### SDIV

Pops two values off the stack, divides the first value by the second, rounds toward zero, then
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


#### MOD

Pops two values off the stack, divides the first value by the second, then pushes the remainder to
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


#### SMOD

Pops two values off the stack, divides the first value by the second, then pushes the remainder to
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


#### EXP

Pops two values off the stack, the first value is raised to the power of the second value, then the
result is pushed to the stack.

> Note: If the `EXP` instruction output overflows, the remainder of the result modulo 2^256 will be
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


#### SIGNEXTEND

> TODO: FINISH THIS
