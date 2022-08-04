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

Pops three values off the stack, adds the first two, divides the sum by the third, then pushes the
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

Pops three values off the stack, multiplies the first two, divides the product by the third, then
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


#### SIGNEXTEND

Pops two values off the stack, the first value specifies a number of bytes minus one, the second
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


#### LT

Pops two values off the stack and checks if the first value is less than the second value. It pushes
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


#### GT

Pops two values off the stack and checks if the first value is greater than the second value. It
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


#### SLT

Pops two values off the stack and checks if the first value is less than the second value. It pushes
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


#### SGT

Pops two values off the stack and checks if the first value is greater than the second value. It
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


#### EQ

Pops two values off the stack and checks if the values are equal. It pushes one to the stack if the
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


#### ISZERO

Pops one value off the stack and pushes one if the value is zero or it pushes zero if the value is
non-zero.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |


#### AND

Pops two values off the stack and pushes the result of a bitwise `AND` operation of the two values.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000011 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |


#### OR

Pops two values off the stack and pushes the result of a bitwise `OR` operation of the two values.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000010 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000011 |


#### XOR

Pops two values off the stack and pushes the result of a bitwise `XOR` operation of the two values.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000011 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000010 |


#### NOT

Pops one value off the stack and pushes the result of a bitwise `NOT` operation of the value.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000FF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF00 |


#### BYTE

Pops two values off the stack and uses the first value as an index of which byte to extract from the
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


#### SHL

Pops two values off the stack and bitwise shifts the second value to the left a number of bits equal
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


#### SHR

Pops two values off the stack and bitwise shifts the second value to the right a number of bits
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


#### SAR

Pops two values off the stack and bitwise shifts the second value to the right a number of bits
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


#### SHA3

Pops two values off the stack and uses the Keccak-256 algorithm to hash data from memory starting at
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


#### ADDRESS

Pushes the address of the currently executing contract to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |


#### BALANCE

Pops one value off the stack, treats it as an address, and pushes the balance of the address in wei
to the stack.

> Note: The `BALANCE` opcode does not revert if the account does not exist, it simply pushes zero to
> the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0XBB29998E000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CF |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |


#### ORIGIN

Pushes the address of the transaction sender to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |


#### CALLER

Pushes the address of the account that called the current execution context to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |


#### CALLVALUE

Pushes the value of the current call in wei to the stack

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |


#### CALLDATALOAD

Pops one value off the stack and uses it as an offset in calldata from which a 32 byte word is
loaded and pushes onto the stack.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xf8a8fd6d00000000000000000000000000000000000000000000000000000000 |


#### CALLDATASIZE

Pushes the size of the current calldata, in bytes, to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000004 |


#### CALLDATACOPY

Pops three values off the stack and treats the first as an offset in memory to copy calldata to, the
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


| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 1     | 0x0000000000000000000000000000000000000000000000000000000000000000 |
| 2     | 0x0000000000000000000000000000000000000000000000000000000000000020 |


#### CODESIZE

Pushes the size of the code in the currently executing contract, in bytes, to the stack.

Stack Output:


| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000FF |


#### CODECOPY

> TODO.

