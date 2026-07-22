# Rust Fixme 3

## Category

General Skills

## Difficulty

Easy

## Description

The challenge provided a Rust project containing a syntax error. The objective was to identify and fix the error in order to compile the program and obtain the flag.

## Tools Used

- Rust
- cargo
- Linux Terminal

## Analysis

While compiling the project:

```bash
cargo build
```

The compiler reported an error related to calling an unsafe function.

Original code:

```rust
let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);
```

The function `from_raw_parts()` is unsafe and must be called inside an unsafe block.

Fixed code:

```rust
let decrypted_slice = unsafe {
    std::slice::from_raw_parts(decrypted_ptr, decrypted_len)
};
```

## Build and Run

```bash
cargo build
cargo run
```

Output:

```text
Using memory unsafe languages is a: PARTY FOUL!
Here is your flag:
picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
```

## Flag

```text
picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
```

## What I Learned

- Basic Rust syntax.
- The purpose of the `unsafe` keyword.
- How Rust protects memory safety.
- Using `cargo build` and `cargo run`.
- Reading and fixing compiler errors.

## Key Concepts

- Rust
- Memory Safety
- Unsafe Blocks
- Compilation Errors