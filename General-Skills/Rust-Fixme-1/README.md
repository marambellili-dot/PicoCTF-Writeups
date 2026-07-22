# Rust Fixme 1

## Category

General Skills

## Difficulty

Easy

## Description

The challenge provided a Rust program containing several syntax errors. The objective was to identify the errors, fix the code, compile the project and recover the flag.

## Tools Used

- Rust
- Cargo
- Linux Terminal

## Issues Found

The compiler reported three main errors:

- Missing semicolon.
- Incorrect return statement.
- Incorrect formatting in `println!`.

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

### 2. Correct Return Statement

Original:

```rust
ret;
```

Fixed:

```rust
return;
```

### 3. Fix println Formatting

Original:

```rust
println!(
    ":?",
    String::from_utf8_lossy(&decrypted_buffer)
);
```

Fixed:

```rust
println!(
    "{}",
    String::from_utf8_lossy(&decrypted_buffer)
);
```

## Build and Run

```bash
cargo build
cargo run
```

Output:

```text
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
```

## Flag

```text
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
```

## What I Learned

- Basic Rust syntax.
- Importance of semicolons.
- Using `return` correctly.
- Formatting output with `println!`.
- Reading compiler error messages.
- Building Rust projects with Cargo.

## Key Concepts

- Rust
- Cargo
- Compilation Errors
- Debugging
- Output Formatting