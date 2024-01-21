# Simple Counter

## Overview

The `counter` library is a Rust project designed to interact with Solana programs, providing functionality for a simple counter. The library supports incrementing, decrementing, updating, and resetting a counter value. It leverages the Solana Program Library (SPL) and Borsh serialization to handle account data and program instructions.

## Features

- **Increment**: Increase the counter by a specified value.
- **Decrement**: Decrease the counter by a specified value.
- **Update**: Set the counter to a specific value.
- **Reset**: Reset the counter to zero.

## Dependencies

- `borsh` and `borsh-derive` (v1.2.1): Used for serialization and deserialization of data.
- `solana-program` (v1.17.7): Provides various modules for Solana program development.
- Development dependencies `solana-program-test` and `solana-sdk` (v1.17.7) are used for testing purposes.

## Installation

To use the `counter` library in your project, add it as a dependency in your `Cargo.toml` file:

```toml
[dependencies]
counter = { path = "path_to_counter" }
```

## Usage

The library exposes a `CounterAccount` struct and a `process_instruction` function, which acts as the entry point for Solana programs.

### CounterAccount

```rust
#[derive(Debug, BorshDeserialize, BorshSerialize)]
pub struct CounterAccount {
    pub counter: u32,
}
```

### process_instruction

```rust
pub fn process_instruction(
    _program_id: &Pubkey,
    accounts: &[AccountInfo],
    instructions_data: &[u8],
) -> ProgramResult { ... }
```

## Testing

The library includes tests for the functionality of incrementing, decrementing, updating, and resetting the counter. To run the tests:

```bash
cargo test -- --nocapture
```
