
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
