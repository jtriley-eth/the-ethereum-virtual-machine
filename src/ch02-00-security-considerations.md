## Security Considerations

Since Yul gives the developer more low level control, there are a number of security considerations
that must be taken into account as well as the well known smart contract weaknesses.

### Yul Contracts

- Memory overwrites
- Storage overwrites
- Storage mapping collisions in non-standard patterns
- Not checking `call`, `staticcall`, and `delegatecall` success
- Hard coding `retOffset` and `retSize` in external calls when the address is not known code
  - This may lead to clipped returndata if the contract returns unexpected data
- Not asserting the `msg.value` is zero
- Function selector switch not reverting in `default` case
- Internal functions not using the `return` instruction
- Unchecked arithmetic
- Reentrancy locks not being unlocked before the `return` instruction is executed

### Solidity Contracts (Assembly Blocks)

- Memory overwrites
- Memory reserve slot overwrites

### Instruction-Level Unexpected Behavior

At the instruction level, there are a few cases where the EVM may not behave as expected. The
following is a comprehensive list of instructions with potentially unexpected behavior.

#### Division Behavior

Division occurs in the [`div`](./instruction-reference.md#div),
[`sdiv`](./instruction-reference.md#sdiv), [`mod`](./instruction-reference.md#mod),
[`smod`](./instruction-reference.md#smod), [`addmod`](./instruction-reference.md#addmod),
and [`mulmod`](./instruction-reference.md#mulmod) opcodes.

In these instructions, division by zero does not revert, they treat the quotient as zero.

#### Arithmetic Overflow and Underflow

Arithmetic overflows may be caused by the [`add`](./instruction-reference.md#add),
[`mul`](./instruction-reference.md#mul), [`addmod`](./instruction-reference.md#addmod),
[`mulmod`](./instruction-reference.md#mulmod), and [`exp`](./instruction-reference.md#exp) opcodes.

In these instructions, an overflow will result in the output modulo `2**256 - 1`.

Arithmetic underflows may be caused by the [`sub`](./instruction-reference.md#sub) opcode.

In this instruction, an underflow will roll over and result in the output plus `2**256 - 1`.

#### Binary Overflow and Underflow

Binary overflows may be caused by [`shl`](./instruction-reference.md#shl) while underflows may be
caused by [`shr`](./instruction-reference.md#shr) and [`sar`](./instruction-reference.md#sar).

In these instructions, the bits that overflow or underflow are not preserved.

#### Non-Existent Storage and Accounts

If an account does not exist, that is to say it has never been interatcted with, never had ether
sent to it, and no code deployed to it, the opcodes [`balance`](./instruction-reference.md#balance)
and [`extcodehash`](./instruction-reference.md#extcodehash) push a zero to the stack.

If a storage slot does not exist, that is to say it has never been written to before, calling
[`sload`](./instruction-reference.md#sload) will simply push a zero to the stack.

Copying external non-existent external code via
[`extcodecopy`](./instruction-reference.md#extcodecopy) simply copy zeros to memory.

Making external calls to both non-contract accounts via [`call`](./instruction-reference.md#call`),
[`callcode`](./instruction-reference.md#callcode),
[`delegatecall`](./instruction-reference.md#delegatecall), and
[`staticcall`](./instruction-reference.md#staticcall) will always push a one to the stack,
indicating success.

#### Out of Bounds

Instructions including [`byte`](./instruction-reference.md#byte),
[`calldataload`](./instruction-reference.md#calldataload), and
[`mload`](./instruction-reference.md#mload) push a value to the stack that, if out of bonuds, will
push zero instead. That is to say using `byte` with an index greater than 32, `calldataload` on a
slot greater than `calldatasize`, and `mload` on a slot greater than `msize` all push a zero to the
stack. Note that using `mload` in this way results in another effect,
[discussed below](#memory-expansions).

Instructions including [`calldatacopy`](./instruction-reference.md#calldatacopy),
[`codecopy`](./instruction-reference.md), [`extcodecopy`](./instruction-reference.md#extcodecopy),
[`call`](./instruction-reference.md#call), [`callcode`](./instruction-reference.md#callcode),
[`delegatecall`](./instruction-reference.md#delegatecall), and
[`staticcall`](./instruction-reference.md#staticcall) can all copy data into memory and if the
area from which they're copying data is not sufficiently large, the rest of the data to copy is just
zeros.

The exception here is [`returndatacopy`](./instruction-reference.md#returndatacopy), which does
revert on an out of bounds access.

#### Memory Expansions

Some instructions can expand memory. Since memory expansion costs quadratic gas relative to its
current size, each of these instructions can expand memory when the read or write is greater than
the current `msize`.

[`calldatacopy`](./instruction-reference.md#calldatacopy),
[`codecopy`](./instruction-reference.md#codecopy),
[`extcodecopy`](./instruction-reference.md#extcodecopy),
[`returndatacopy`](./instruction-reference.md#returndatacopy),
[`mload`](./instruction-reference.md#mload), [`mstore`](./instruction-reference.md#mstore),
[`mstore8`](./instruction-reference.md#mstore8), [`log0`](./instruction-reference.md#log0),
[`log1`](./instruction-reference.md#log1), [`log2`](./instruction-reference.md#log2),
[`log3`](./instruction-reference.md#log3), [`log4`](./instruction-reference.md#log4),
[`call`](./instruction-reference.md#call), [`callcode`](./instruction-reference.md#callcode),
[`delegatecall`](./instruction-reference.md#delegatecall),
[`staticcall`](./instruction-reference.md#staticcall),
[`return`](./instruction-reference.md#return), and [`revert`](./instruction-reference.md#revert).

#### External Calls

External calls using the [`call`](./instruction-reference.md#call),
[`callcode`](./instruction-reference.md#callcode),
[`delegatecall`](./instruction-reference.md#delegatecall), and
[`staticcall`](./instruction-reference.md#staticcall) instructions will only forwward `63/64` of the
remaining gas in the current context. This was implemented in the Tangerine Whistle Fork in response
to out-of-gas attacks.
