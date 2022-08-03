## Yul Basics

### Variables

Variables are declared with the `let` keyword and assigned with the `:=` operator.

Example:
```js
let a := 1
```

### Conditional

Conditional code blocks can be defined with the `if`/`else` control flow OR a `switch` statement.

#### `if` and `else`

Both `if` and `else`:
```js
if expression {
    // expression is true (1)
} else {
    // expression is false (0)
}
```

Omitting `else`:
```js
if expression {
    // expression is true (1)
}
```

#### `switch`

Switch with cases and a default fallback:
```js
switch value

case match_0 {
    // value is match_0
}

case match_1 {
    // value is match_1
}

default {
    // value is none of the above cases
}
```

### Functions

Functions are defined by a name, argument name(s), and return name(s).
> Notice that "return" is not the `return` instruction, but rather it is the value(s) that persist
> at the end of the function's execution.
>
> At compile time, Yul functions are simply code blocks that are jumped to and from using `jump`,
> `jumpi`, and `jumpdest` instructions.


Multiply `a` and `b`, then divide the result by `c`:
```js
function muldiv(a, b, c) -> result {
    result := div(mul(a, b), c)
}
```


### Loops

The `for` loop is comparable to other langauges. It includes a block of code where an iterator can
be defined, a condition can be checked before each iteration, and a block of code that can
manipulate the iterator on each iteration.

Loop ten times, multiplying a "result" by two
```js
let result := 1

for { let i := 0 } lt(i, 11) { add(i, 1) } {
    result := mul(result, 2)
}
```

### Events

Events can be logged using the `logN` instructions. When logging an event, the first topic (if any)
is the event "hash" which is the `keccak256` hash of the signature.

> Signature:    event Transfer(address,address,uint256)
>
> Hash:         0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef

Log a transfer from a `sender` to a `receiver` for 100 wei.

```js
let hash := 0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef
let sender := 0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266
let receiver := 0x70997970c51812dc3a010c7d01b50e0d17dc79c8
let amount := 100

let memory_offset := 0
let memory_size := 32

// store the `amount` in memory at offset 0
mstore(memory_offset, amount)

// log using the hash, sender, receiver, the memory offset to `amount`, and the
// memory size to log.
log3(memory_offset, memory_size, hash, sender, receiver)
```

### Return

Returning from the current context can be done by storing the data to return in memory, then calling
the return instruction with the offset and size in memory to return.

```js
let balance := 100
let memory_offset := 0
let memory_size := 32

// store the balance in memory at offset 0
mstore(memory_offset, balance)

// return 32 bytes of data starting offset 0 in memory
return(memory_offset, memory_size)
```

### Revert

To revert the current context, do the same as you would with a `return` instruction. If you intend
to omit an error message, you can do the following.

```js
revert(0, 0)
```

### Calls

To call another contract, you will need to store the intended call data in memory, then pass to the
`call` (or `staticcall` or `delegatecall`) instruction the gas to forward, the target address, the
offset in memory where the call data starts, the call data length, and optionally the return data
size and offset to which it should be copied in memory (if you know the return data size ahead of
time).

> NOTE: Each external call instruction returns a boolean to indicate whether or not the call
> reverted (1 if success, 0 if revert).

> Notice that the standard set by Solidity for calling functions is to hash the function signature,
> then prepend the first four bytes to the intended call data.
> 
> Signature:    function balanceOf(address)
>
> Selector:     0x722713f70
```js
let WETH := 0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2
let account := 0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266
let balance_of_selector := 0x70a0823100000000000000000000000000000000000000000000000000000000

let selector_offset := 0
let account_offset := 4

let call_data_offset := 0
let call_data_length := 36

mstore(selector_offset, balance_of_selector)
mstore(account_offset, account)

// MEMORY LAYOUT
// |    | balanceOf | account                                                          |
// | 0x | 70a08231  | 000000000000000000000000f39fd6e51aad88f6f4ce6ab8827279cfffb92266 |

let success := staticcall(gas(), WETH, call_data_start, call_data_end, 0, 0)

// We can overwrite the memory at slot 0 because it's no longer needed
let return_data_memory_offset := 0

returndatacopy(return_data_memory_offset, 0, returndatasize())

let balance_of := mload(return_data_memory_offset)
```

### Object

A Yul contract is a single `object` whose block contains a `code` block and any other sub-`object`s
that represent code that can be deployed by the root object. A full contract would be an `object`
with a `code` block containing the "constructor" logic and a sub-`object` that contains the runtime
bytecode of the contract to be deployed to the chain.

A contract whose runtime bytecode returns an inconspicuous number:
```js
object "NumberReturnooor" {
    code {
        // constructor logic

        // get offset and size of "runtime" object's code
        let runtime_offset := dataoffset("runtime")
        let runtime_size := datasize("runtime")

        // store the bytecode in memory
        let memory_offset := 0
        datacopy(memory_offset, runtime_offset, runtime_size)

        return(memory_offset, runtime_size)
    }

    object "runtime" {
        code {
            let memory_offset := 0
            let memory_size := 32

            mstore(memory_offset, 420)
            return(memory_offset, memory_size)
        }
    }
}
```

### Use In Solidity

In Solidity, Yul can be written inside of `assembly` code blocks.

When writing Yul in Solidity, there are some important standard patterns in Solidity that must be
followed to prevent unintended behavior.

#### Storage

When storing a value in Soldiity, it will occupy a slot starting at slot zero. Values are padded to
32 bytes.

```js
// Solidity
contract Example {
    uint256 value = 1;
}

// Yul
sstore(0, 1)

// Storage
0   :   0x0000000000000000000000000000000000000000000000000000000000000001
```

When two values can fit in the same slot, they are lower-order aligned and packed.

```js
// Solidity
contract Example {
    uint128 a = 1;
    uint128 b = 2;
    uint8 c = 3;
    uint8 d = 4;
}

// Yul
sstore(0, 0x0100000000000000000000000000000002)
sstore(1, 0x0304)

// Storage
0   :   0x0000000000000000000000000000000100000000000000000000000000000002
1   :   0x0000000000000000000000000000000000000000000000000000000000000304
```

When storing data in a mapping, the slot for a given value is computed by padding the key to 32
bytes, concatenated with the "index", then hashing the two. The "index" is the mapping's position
in storage.

```js
// Solidity
contract Example {
    mapping(address => uint256) account_map;

    constructor() {
        addresss alice = address(0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266)
        account_map[alice] = 1;
    }
}

// Yul
mstore(0, 0xf39fd6e51aad88f6f4ce6ab8827279cfffb92266)
mstore(32, 0)
let slot := keccak(0, 64)
// keccak(0x000000000000000000000000f39fd6e51aad88f6f4ce6ab8827279cfffb922660000000000000000000000000000000000000000000000000000000000000000)
sstore(slot, 1)

// Storage
0x723077b8a1b173adc35e5f0e7e3662fd1208212cb629f9c128551ea7168da722 : 0x0000000000000000000000000000000000000000000000000000000000000001
```

When storing a statically sized array, the elements are tightly packed and the next variable will
use a new slot.

```js
// Solidity
contract Example {
    uint256[2] values = [1, 2];
    uint256 a = 3;
}

// Yul
sstore(0, 1)
sstore(1, 2)
sstore(2, 3)

// Storage
0   :   0x0000000000000000000000000000000000000000000000000000000000000001
1   :   0x0000000000000000000000000000000000000000000000000000000000000002
2   :   0x0000000000000000000000000000000000000000000000000000000000000003
```

When storing a dynamically sized array, the length of the array is stored at the storage index. The
elements of the array are stored starting at the keccak hash of the storage index. Elements are
tightly packed if they are less than 16 bytes (128 bits).

```js
// Solidity
contract Example {
    uint256 a = 1;
    uint256[] arr;

    constructor() {
        arr.push(2);
        arr.push(3);
    }
}

// Yul
mstore(0, 1)
let arr_start_slot := keccak(0, 32)
// keccak(0x0000000000000000000000000000000000000000000000000000000000000001)
sstore(0, 1)
sstore(arr_start_slot, 2)
sstore(add(arr_start_slot, 1), 3)

// Storage
0                                                                   :   0x0000000000000000000000000000000000000000000000000000000000000001
1                                                                   :   0x0000000000000000000000000000000000000000000000000000000000000001
0xb10e2d527612073b26eecdfd717e6a320cf44b4afac2b0732d9fcbe2b7fa0cf6  :   0x0000000000000000000000000000000000000000000000000000000000000002
0xb10e2d527612073b26eecdfd717e6a320cf44b4afac2b0732d9fcbe2b7fa0cf7  :   0x0000000000000000000000000000000000000000000000000000000000000003
```

#### Memory

In Solidity, the first four slots (128 bytes; 4096 bits) of memory are reserved.

000 - 063 : scratchspace for hashing methods
064 - 095 : free memory pointer
096 - 128 : zero slot

The scratchspace can be safely manipulated during an inline assembly block.

The free memory pointer points to the next free slot in memory. When a word is stored in memory,
Solidity ensures this is incremented. If you store a value in memory at where the free memory
pointer points, be sure to increment the memory pointer to ensure the rest of the Solidity code can
handle it.

The zero slot should never be written to.

When a dynamic array is stored in memory, the first array slot should be the array's length, then
each element occupies its own slot.

```js
// Solidity
contract Example {
    function example() public pure {
        uint8[] memory arr = new uint8[](3);
        arr[0] = 1;
        arr[1] = 2;
        arr[2] = 3;
    }
}

// Yul
let mem_ptr := mload(64)

let arr_len := 3
let element_0 := 1
let element_1 := 2
let element_2 := 3

mstore(mem_ptr, arr_len)                // store length
mstore(add(mem_ptr, 32), element_0)     // store element 0
mstore(add(mem_ptr, 64), element_1)     // store element 1
mstore(add(mem_ptr, 96), element_2)     // store element 2
mstore(64, add(mem_ptr, 128))           // store new memory pointer (mem_ptr + 128)

// Memory
0x00 : 0x0000000000000000000000000000000000000000000000000000000000000000  // scratchspace
0x20 : 0x0000000000000000000000000000000000000000000000000000000000000000  // scratchspace
0x40 : 0x0000000000000000000000000000000000000000000000000000000000000100  // free mem ptr
0x60 : 0x0000000000000000000000000000000000000000000000000000000000000000  // zero slot
0x80 : 0x0000000000000000000000000000000000000000000000000000000000000003  // length
0xa0 : 0x0000000000000000000000000000000000000000000000000000000000000001  // element 0
0xc0 : 0x0000000000000000000000000000000000000000000000000000000000000002  // element 1
0xe0 : 0x0000000000000000000000000000000000000000000000000000000000000003  // element 2
```

#### Call Data

Calldata is defined by the Soldity ABI specification. The function selector, which is the first
four bytes of the hash of the function signature, occupies the first four bytes of calldata, while
each argument, regardless of size, is padded to 32 bytes and appended to the calldata.

```js
// Solidity
contract Example {
    function balanceOf(address account) public view returns (uint256) {
        return _balance[account];
    }
}

// Yul
let selector := shr(224, calldataload(0))
let account := calldataload(4)
// ...

// Call Data
0x70a08231000000000000000000000000f39fd6e51aad88f6f4ce6ab8827279cfffb92266
```

