## Yul Example Contract

```js
object "Vault" {
    code {
        // -----------------------------------------------------------------------------------------
        // Constructor Logic
        datacopy(0, dataoffset("runtime"), datasize("runtime"))
        return(0, datasize("runtime"))
    }
    object "runtime" {
        code {
            // -------------------------------------------------------------------------------------
            // Function Selector Switch

            let selector := shr(0xe0, calldataload(0))

            switch selector

            // function deposit() public payable;
            case 0xd0e30db0 {
                // get deposit
                let deposit := get_deposit(caller())

                // set deposit to current deposit + msg.value
                set_deposit(add(deposit, callvalue()))

                // log deposit event
                log_deposit(caller(), callvalue())
            }

            // function withdraw() public;
            case 0x3ccfd60b {
                // assert the msg.value is zero
                if iszero(iszero(callvalue()) { revert(0, 0) }

                // get deposit
                let deposit := get_deposit(caller())

                // set deposit to zero
                set_deposit(0)

                // send the Ether to the caller with no calldata
                let success := call(gas(), caller(), deposit, 0, 0, 0, 0)

                // assert the call was successful
                if iszero(success) { revert(0, 0) }

                // log withdrawal event
                log_withdrawal(caller(), deposit)
            }

            // Revert if no function selector is found
            default { revert(0, 0) }

            // -------------------------------------------------------------------------------------
            // Storage
            function get_mapping(key, index) -> slot {
                // store in memory the key and index of the slot, then hash them.
                // docs.soliditylang.org/en/v0.8.15/internals/layout_in_storage.html
                mstore(0, key)
                mstore(32, index)
                let slot := keccak256(0, 64)
            }

            function get_deposit(account) -> deposit {
                // Load from storage the current deposit
                deposit := sload(mapping(account, 0))
            }

            function set_deposit(account, amount) {
                // Store in storage the new deposit
                sstore(mapping(account, 0), amount)
            }

            // -------------------------------------------------------------------------------------
            // Events

            // event Deposit(address indexed account, uint256 amount);
            function log_deposit(account, amount) {
                // keccak256("Deposit(address,uint256)")
                let hash := 0xe1fffcc4923d04b559f4d29a8bfc6cda04eb5b0d3c460751c2402c5c5cc9109c

                // store amount in memory since it is not "indexed"
                mstore(0, amount)

                // log with topics "hash" and "account", with the "data" being
                // at 0 in memory with a length of 32
                log2(0, 32, hash, account)
            }

            // event Withdrawal(address indexed account, uint256 amount);
            function log_withdrawal(account, amount) {
                // keccak256("Withdrawal(address,uint256)")
                let hash := 0x7fcf532c15f0a6db0bd6d0e038bea71d30d808c7d98cb3bf7268a95bf5081b65

                // store the amount in memory since it is not "indexed"
                mstore(0, amount)

                // log with topics "hash" and "account", with the "data" being
                // at 0 in memory with a length of 32
                log2(0, 32, hash, account)
            }
        }
    }
}
```
