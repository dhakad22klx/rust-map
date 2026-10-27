# Rust setup

## Install

Install Rust with rustup:

```sh
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

After installation, load Rust into your current Bash shell(or just open fresh terminal) and check the installed versions:

```sh
source "$HOME/.cargo/env"
rustc --version
cargo --version
```

If `rustc` is not found, your terminal may not have loaded the updated `PATH`. Run the `source` command above or open a new terminal.

When copying commands from documentation, omit the leading `$`; it represents the shell prompt.

## Uninstall

You can uninstall at any time with `rustup self uninstall`, and these changes will be reverted.
