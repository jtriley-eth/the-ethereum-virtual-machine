# The Ethereum Virtual Machine

This repository is intended to contain a full in depth explanation of the Ethereum Virtual Machine
and its execution environment for developers seeking lower level control than what is given in high
level languages.

This book is a work in progress and contributions in line with the
[contributing policy](CONTRIBUTING) are welcomed!

## Local Usage

To build this book locally, you will need `mdbook`.

Clone the repository:

```bash
git clone https://github.com/JoshuaTrujillo15/the-ethereum-virtual-machine/
```

Install [mdbook](https://lib.rs/crates/mdbook) - Rust crate for converting markdown to ebook :

```rust
cargo install mdbook
```

- If the above command throws an error it means you don't have the Rust compiler installed.
- Install [Rust](https://forge.rust-lang.org/infra/other-installation-methods.html)

_Install rust on Windows (WSL)_

```bash
 curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

_Install rust on Linux/MacOS_

```bash
curl https://sh.rustup.rs -sSf | sh -s -- --help
```

Enter this directory:

```bash
cd the-ethereum-virtual-machine
```

Start an `mdbook` server and automatically open the book in a browser.

```
mdbook serve --open
```
