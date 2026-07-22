# Rust Fixme 2

## Category

General Skills

## Difficulty

Easy

## Description

The challenge provided a Rust program containing multiple syntax and ownership errors. The objective was to fix the code and successfully decrypt the hidden flag.

## Tools Used

- Rust
- cargo
- Linux Terminal

## Issues Found

The code contained several errors:

- Missing semicolon.
- Incorrect return statement.
- Immutable reference used where a mutable reference was required.
- Variable not declared as mutable.
- Incorrect argument passed to the function.

## Fixes Applied

### 1. Add Missing Semicolon

Original:

```rust
let key = String::from("CSUCKS")
```

Fixed:

```rust
let key = String::from("CSUCKS");
```

### 2. Use Mutable Reference

Original:

```rust
fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &String)
```

Fixed:

```rust
fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &mut String)
```

### 3. Correct Return Statement

Original:

```rust
ret;
```

Fixed:

```rust
return;
```

### 4. Declare Variable as Mutable

Original:

```rust
let party_foul = String::from("Using memory unsafe languages is a: ");
```

Fixed:

```rust
let mut party_foul = String::from("Using memory unsafe languages is a: ");
```

### 5. Pass Mutable Reference

Original:

```rust
decrypt(encrypted_buffer, &party_foul);
```

Fixed:

```rust
decrypt(encrypted_buffer, &mut party_foul);
```

## Build and Run

```bash
cargo build
cargo run
```

## Flag

```text
picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
```

## What I Learned

- Rust ownership and borrowing concepts.
- Mutable references (`&mut`).
- Variable mutability (`mut`).
- Error handling using `return`.
- Reading and fixing compiler errors.
- Building and running Rust programs with Cargo.

## Key Concepts

- Rust
- Ownership
- Borrowing
- Mutable References
- Compilation Errors
- Cargo