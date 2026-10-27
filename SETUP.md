# Rust setup

## Rust tools

- `rustc`: Rust's compiler, which turns Rust source code into executables or libraries.
- `rustup`: Installs, updates, and manages Rust toolchains, including compiler versions and related tools.
- `cargo`: Rust's build system and package manager, used to manage dependencies and build, run, and test projects.

## Install

Install Rust with rustup, which also installs rustc and Cargo:

```sh
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

After installation, load Rust into your current Bash shell (or open a new terminal) and check the installed versions:

```sh
source "$HOME/.cargo/env"
rustc --version
rustup --version
cargo --version
```

If `rustc` is not found, your terminal may not have loaded the updated `PATH`. Run the `source` command above or open a new terminal.

When copying commands from documentation, omit the leading `$`; it represents the shell prompt.

## Use Cargo

Run Cargo commands from the project folder containing `Cargo.toml`.

### Set up a project

For an existing folder without `Cargo.toml`, initialize Cargo once. It can use an existing `main.rs`:

```sh
cargo init --bin
```

This repository already has `Cargo.toml` configured to use the root `main.rs`, so you can skip initialization here.

To create a separate project in a new folder instead:

```sh
cargo new hello_rust
cd hello_rust
```

New projects use `src/main.rs` by default.

### Build and run in one command

```sh
cargo run
```

Cargo calls rustc to compile when needed, then runs the program automatically. It still creates an executable under `target/debug/` (`target/debug/rust-map` in this repository), but you do not need to run it separately.

### Other useful commands

| Command | Purpose |
| --- | --- |
| `cargo build` | Compile the project without running it. |
| `cargo check` | Check the code without producing an executable for the program. |
| `cargo test` | Build and run the project's tests. |
| `cargo build --release` | Create an optimized build under `target/release/`. |

### Project files

- `Cargo.toml`: Project settings and dependency declarations.
- `Cargo.lock`: Exact dependency versions resolved by Cargo; Cargo manages this file.
- `target/`: Generated executables and other build output.

See the official [Cargo guide](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html), [cargo init reference](https://doc.rust-lang.org/cargo/commands/cargo-init.html), [rustc guide](https://doc.rust-lang.org/rustc/what-is-rustc.html), and [rustup overview](https://doc.rust-lang.org/book/appendix-07-nightly-rust.html#rustup-and-the-role-of-rust-nightly).

## Uninstall

You can uninstall at any time with `rustup self uninstall`, and these changes will be reverted.
