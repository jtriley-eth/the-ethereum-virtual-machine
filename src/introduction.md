## Introduction

The Ethereum Virtual Machine is a stack-based state-machine with persistent data storage, a
relatively simple, turing-complete instruction set, and immutable smart contract code.

### Ether

Ethereum's native currency is Ether, which can be transferred between any two accounts and it can be
used to pay transaction fees.

### Account Model

In Ethereum, there are two kinds of accounts, externally-owned accounts (EOA) and contract accounts.
Both EOAs and contracts have 20 byte addresses and to determine whether an account is a contract
account, one can check for the existence of code at that account.

This generalized account model makes it simple for both contracts and EOAs to hold Ether.

### Gas

As a Turing machine, the EVM is succeptible to something called the Halting Problem. The Halting
Problem is the inability to determine whether an arbitrary program with arbitrary inputs will
terminate or execute forever. The EVM's solution to the halting problem is setting a deterministic
limit on how much "gas" or computation a program can consume. Every instruction in the EVM has a
non-zero amount of gas associated with it, so the more computation a program uses, the more gas it
uses. Gas is payable, in Ether, by the externally-owned account (EOA) that signed and submitted the
transaction at the time of execution.

### Stack Machine

A stack is an abstract data-type which adds and removes items according to the "Last In, First Out"
pattern. Items are added to the stack by pushing and they are removed by popping. Each instruction
has a number of pushes and pops associated with its execution. Currently, the EVM supports a stack
depth of 1024 words at a time. Each word is 32 bytes, or 256 bits, in size.
