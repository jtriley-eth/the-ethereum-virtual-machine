## Environment Variables

A number of instructions can read information about the current execution context's environment.
Some variables are related to the current transaction or block information, some may change as part
of the global state, and some may change given a different execution context.

---

### Transaction Variables

#### Origin

The EOA account that originally submitted the currently executing context's transaction.

Instruction: [ORIGIN](instruction-reference.md#origin)

Solidity: `tx.origin`

#### Gas Price

Price of the gas in the current transaction.

Instruction: [GASPRICE](instruction-reference.md#gasprice)

Solidity: `tx.gasprice`

#### Coinbase

The beneficiary address of the current transaction's block.

Instruction: [COINBASE](instruction-reference.md#coinbase)

Solidity: `block.coinbase`

#### Timestamp

The timestamp of the current transaction's block.

Instruction: [TIMESTAMP](instruction-reference.md#timestamp)

Solidity: `block.timestamp`

#### Number

The number of the current transaction's block.

Instruction: [NUMBER](instruction-reference.md#number)

Solidity: `block.number`

#### Difficulty

The current transaction's block's difficulty.

Instruction: [DIFFICULTY](instruction-reference.md#difficulty)

Solidity: `block.difficulty`

#### Gas Limit

The current transaction's block's gas limit.

Instructon: [GASLIMIT](instruction-reference.md#gaslimit)

Solidity: `block.gaslimit`

#### Base Fee

The current transaction's block's base fee.

Instruction: [BASEFEE](instruction-reference.md#basefee)

Solidity: `block.basefee`

---

### Context Variables

#### Address

The address of the currently executing account.

Instruction: [ADDRESS](instruction-reference.md#address)

Solidity: `address(this)`

#### Caller

The address that called the currently executing account.

Instruction: [CALLER](instruction-reference.md#caller)

Solidity: `msg.sender`

#### Call Value

The value, in wei, attached to the currently executing context.

Instruction: [CALLVALUE](instruction-reference.md#callvalue)

Solidity: `msg.value`
