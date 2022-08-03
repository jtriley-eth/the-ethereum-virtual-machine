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
