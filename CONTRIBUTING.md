# Contributing to hanzo CLI

We welcome contributions in the form of bug reports, feature requests,
and pull requests (PRs). This document describes how you can
contribute to the hanzo CLI — a Rust project.

## Bug Reports and Feature Requests

Please submit bug reports and feature requests as GitHub issues.
This helps us keep track of them and discuss potential solutions.

## Pull Requests

We appreciate your pull requests. For small changes, feel free to
submit a PR directly. If you are considering a large or significant
change, please discuss it in a GitHub issue before submitting the PR.
This will save both you and the maintainers time, and it helps to
ensure that your contributions can be integrated smoothly.

## Setting up a Development Environment

### Clone the Repository

```bash
git clone https://github.com/hanzoai/cli
cd cli
```

### Build

The hanzo CLI is written in Rust. Install the [Rust toolchain](https://rustup.rs/)
then build:

```bash
cargo build --release --bin hanzo --locked
```

This produces a single static binary at `target/release/hanzo`.

### Install Locally

To install the CLI into your local `~/.cargo/bin`:

```bash
cargo install --path . --locked
```

### Run Tests

Run the full test suite:

```bash
cargo test --workspace --locked --no-fail-fast
```

Run tests for a specific crate:

```bash
cargo test -p hanzo-event --locked
```

### Run Linter

```bash
cargo clippy --locked --all-targets -- -D warnings
```

### Formatting

```bash
cargo fmt --all -- --check
```

## Coding Standards

### Rust Style

The project follows standard Rust conventions. Run `cargo fmt` and
`cargo clippy` before submitting a PR to ensure your code matches the
project style.

### Testing

When contributing new features or making changes to existing code,
ensure that you write appropriate tests to maintain code coverage.
Test files live alongside source in each crate (e.g. `tests/`,
`src/**/*.rs`).

## CI

GitHub Actions runs `cargo test`, `cargo clippy`, and `cargo fmt --check`
on every push and pull request to `main`. Make sure all three pass
before requesting review.

## Licensing

Before contributing a PR, please review our
[Individual Contributor License Agreement](https://dev.chat/docs/legal/contributor-agreement.html).