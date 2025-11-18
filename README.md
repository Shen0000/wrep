# wrep

A simple and fast command-line tool to search for patterns in files, inspired by grep. Adapted from [**Command Line Applications in Rust**](https://rust-cli.github.io/book/tutorial/index.html)

## Description

`wrep` is a lightweight file search utility written in Rust that allows you to search for text patterns within files. It reads a file and displays all lines that contain the specified pattern.

## Installation

### From Source

Clone the repository and build with Cargo:

```sh
git clone https://github.com/Shen0000/wrep
cd wrep
cargo build --release
```

The compiled binary will be available at `target/release/wrep`.

### Using Cargo Install

```sh
cargo install wrep
```

## Usage

```sh
wrep <PATTERN> <FILE>
```

### Arguments

- `<PATTERN>` - The text pattern to search for
- `<FILE>` - The path to the file to search in

### Examples

Search for the word "error" in a log file:

```sh
wrep error /var/log/app.log
```

Search for "TODO" in a source file:

```sh
wrep TODO src/main.rs
```

### Output

`wrep` outputs all lines from the file that contain the search pattern. Each matching line is printed to stdout exactly as it appears in the file.

## Error Handling

If the specified file doesn't exist or cannot be read, `wrep` will display an error message:

```
Error: could not read file `<filepath>`
```

## Development

### Running Tests

Run the unit tests:

```sh
cargo test
```

Run integration tests:

```sh
cargo test --test cli
```

### Project Structure

- [`src/main.rs`](src/main.rs) - Command-line interface and argument parsing
- [`src/lib.rs`](src/lib.rs) - Core pattern matching logic
- [`tests/cli.rs`](tests/cli.rs) - Integration tests


## License

MIT
