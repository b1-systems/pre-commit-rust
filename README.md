# Rust hooks for pre-commit

[Rust](https://www.rust-lang.org) tools package for [pre-commit](https://pre-commit.com).

## Usage

Install pre-commit:
`pip install pre-commit`

Create .pre-commit-config.yaml in your main project dir with the following content:
```yaml
- repo: https://github.com/doublify/pre-commit-rust
  rev: v1.0
  hooks:
  - id: fmt
  - id: clippy
  - id: cargo-check
  - id: cargo-test
```
Choose plugins and their order from the above list as needed.

Then run:

```
$ pre-commit install
$ pre-commit run --all-files
```

After that you it will be checked before each commit.

## Passing arguments to rustfmt

```yaml
-   repo: https://github.com/doublify/pre-commit-rust
    rev: master
    hooks:
    -   id: fmt
        args: ['--verbose', '--', '--edition', '2018' ]
```

Note: Cargo fmt picks up "edition" automatically from Cargo.toml, so specificying this isn't necessary in most cases.
