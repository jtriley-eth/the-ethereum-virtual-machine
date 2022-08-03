## Execution Context

To call a contract, it must be called by its address. When called, an execution context is created.
This context contains information about the current call, accessible to the contract.

### Code

The code is the bytecode located at the address receiving the call. This code contains "opcodes", or
instructions to execute. A program counter points to the instruction to execute and increments on
each instruction's execution. The program counter can be overwritten by using the
[jump](./instruction-reference.md#jump) and [jumpi](./instruction-reference.md#jumpi) instructions.

### Context Data Locations

- Stack:
  - Cheap
  - Push to stack in 32 byte words
  - Pop from stack in 32 byte words
  - Clears at the end of the context
- Memory:
  - Linear
  - Less cheap
  - Store from stack in 32 or 1 byte words
  - Loads to stack in 32 byte words
  - Clears at the end of the context
- Storage:
  - Expensive af
  - Stores from stack in 32 byte words
  - Loads to stack in 32 byte words
  - Persists until explicitly freed
- Call Data:
  - The payload passed to the current contract consisting of the function selector and arguments
  - Loads to stack in 32 byte words
  - Copies to memory with any length and offset
  - Can NOT write to call data
- Return Data:
  - The data returned from the most recent contract called within the current context
  - If no external contract has been called in the current context, it defaults to zero
  - If the previous call reverted, the return data may contain error information
  - Can NOT write to return data

## External Calls

### `call`

The `call` instruction executes call data against a given address's code. It can forward gas for its
execution (up to 1/64 of the remaining gas), it can send Ether, it can send arbitrary data in the
form of call data, and it can access the data returned from the call.

### `staticcall`

The `staticcall` instruction is the same as `call` with 2 exceptions.

1. A `staticcall` results in any global state update, it will fail.
2. A `staticcall` can NOT send Ether, as it would update the global state.

### `delegatecall`

The `delegatecall` instruction executes call data against a given address's code, however, the
current execution context is preserved. This means variables such as `msg.sender` for a given
context will be the same as the `msg.sender` during the `delegatecall` within the sub-context.

If the code at the target address of a `delegatecall` updates Storage, it updates the storage of the
contract making the `delegatecall` instead of the target.

```

TX Origin: address 0x00..00

| address 0x00..01   | -------> CALL -------> | address 0x00..02   |
| ------------------ |                        | ------------------ |
| Contract1          |                        | Contract2          |
| ------------------ |                        | ------------------ |
| caller  = 0x00..00 |                        | caller  = 0x00..01 |
| address = 0x00..01 |                        | address = 0x00..02 |
| storage = 0x00..01 |                        | storage = 0x00..02 |



| address 0x00..01   | ----> STATICCALL ----> | address 0x00..02   |
| ------------------ |                        | ------------------ |
| Contract1          |                        | Contract2          |
| ------------------ |                        | ------------------ |
| caller  = 0x00..00 |                        | caller  = 0x00..01 |
| address = 0x00..01 |                        | address = 0x00..02 |
| storage = 0x00..01 |                        | storage = 0x00..02 |



| address 0x00..01   | ---> DELEGATECALL ---> | address 0x00..02   |
| ------------------ |                        | ------------------ |
| Contract1          |                        | Contract2          |
| ------------------ |                        | ------------------ |
| caller  = 0x00..00 |                        | caller  = 0x00..00 |
| address = 0x00..01 |                        | address = 0x00..01 |
| storage = 0x00..01 |                        | storage = 0x00..01 |

```
