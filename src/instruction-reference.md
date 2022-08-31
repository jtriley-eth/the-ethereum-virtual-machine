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

Stack Input:

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

Pops three values off the stack and treats the first as an offset in memory to copy the current
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


#### GASPRICE

Pushes the current price, in wei, per gas of the current transaction to the stack.

Stack Output:


| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000FF |


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


#### RETURNDATASIZE

Pushes the size of the return data from the previous external call to the stack.

> Note: The `RETURNDATASIZE` opcode does not revert if no external calls have been executed in the
> current context, it will simply push zero to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |

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


#### COINBASE

Pushes the address of the current transaction's miner to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000F39FD6E51AAD88F6F4CE6AB8827279CFFFB92266 |


#### TIMESTAMP

Pushes the timestamp of the current context's block to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000080 |


#### NUMBER

Pushes the number of the current transaction's block to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000040000 |


#### DIFFICULTY

Pushes the mining difficulty of the current transaction's block to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000000270f4ed4e3000 |


#### GASLIMIT

Pushes the gas limit of the current transaction to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000FFFFFF |


#### CHAINID

Pushes the id of the current chain to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |


#### SELFBALANCE

Pushes the balance, in wei, of the address of the current execution context to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |


#### BASEFEE

Pushes the base fee, in wei, of the current transaction to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000010 |


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


#### MSTORE8

Pops two values off the stack and stores in memory the least-significant byte of the second value at
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


#### JUMP

Pops a value from the stack and writes the value to the current program counter.

> Note: The `JUMPI` opcode requires that the first stack value points to a byte in the current
> contract's bytecode that is explicitly `0x5b`. For more, read `JUMPDEST`.

Stack Input:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000001 |

Progam Counter After: 1


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


#### PC

Pushes the current program counter value to the stack. The value is the program counter _before_ it
is incremented.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |


#### MSIZE

Pushes the current memory size in bytes rounded up to the next 32 byte increment to the stack.

> Note: The `MSIZE` opcode size includes not just the size of memory written. This means even if
> memory has not been written to, calling `MLOAD` on the first slot of memory will make the `MSIZE`
> be 32 (`0x20`).

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000000 |


#### GAS

Pushes the gas remaining after this instruction's execution to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000000100 |


#### JUMPDEST

This does not affect the execution context, nor does it execute an instruction. This serves as the
byte that a `JUMP` or `JUMPI` instruction should write the program counter to.


#### PUSH1

Pads a one byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000000000FF |


#### PUSH2

Pads a two byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000000000000000FFFF |


#### PUSH3

Pads a three byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000000000FFFFFF |


#### PUSH4

Pads a four byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000000000FFFFFFFF |


#### PUSH5

Pads a five byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000000000FFFFFFFFFF |


#### PUSH6

Pads a six byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000000000FFFFFFFFFFFF |


#### PUSH7

Pads a seven byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000000000FFFFFFFFFFFFFF |


#### PUSH8

Pads an eight byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000000000FFFFFFFFFFFFFFFF |


#### PUSH9

Pads a nine byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000000000FFFFFFFFFFFFFFFFFF |


#### PUSH10

Pads a 10 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFF |


#### PUSH11

Pads an 11 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFF |


#### PUSH12

Pads a 12 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH13

Pads a 13 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH14

Pads a 14 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH15

Pads a 15 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH16

Pads a 16 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH17

Pads a 17 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH18

Pads an 18 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH19

Pads a 19 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH20

Pads a 20 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH21

Pads a 21 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH22

Pads a 22 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH23

Pads a 23 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH24

Pads a 24 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH25

Pads a 25 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH26

Pads a 26 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH27

Pads a 27 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH28

Pads a 28 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH29

Pads a 29 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x000000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH30

Pads a 30 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x0000FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH31

Pads a 31 byte value to 32 bytes and pushes the value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0x00FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |


#### PUSH32

Pushes a 32 byte value to the stack.

Stack Output:

| index | value                                                              |
| ----- | ------------------------------------------------------------------ |
| 0     | 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF |

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


#### LOG0

Pops two values off the stack, treats the first value as a memory offset and the second as the size
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

#### LOG1

Pops three values off the stack, treats the first as a memory offset, the second as the data size in
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


#### LOG2

Pops four values off the stack, treats the first as a memory offset, the second as the data size in
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


#### LOG3

Pops five values off the stack, treats the first as a memory offset, the second as a data size in
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


#### LOG4

Pops six values off the stack, treats the first as a memory offset, the second as a data size in
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


#### CREATE

Pops three values off the stack, treats the first as a value, in Ether, to send to the constructor
of the contract to be created, the second as an offset in memory where the future contract's
bytecode is stored, and the third as the size, in bytes of the contract to be deployed. It then
deploys the contract and pushes its address to the stack.

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


#### CALL

Pops seven values from the stack // TODO: this
