# Chawpick Ide

A desktop app built with Rust and egui.

Stack: Rust + [egui](https://github.com/emilk/egui) / eframe 0.37.

## Run

```sh
cargo run
```

The first build downloads and compiles egui and takes a few minutes; later builds take seconds.

## Check before committing

```sh
cargo fmt --check
cargo clippy --all-targets -- -D warnings
cargo test
```

## Layout

Programs live in `apps/`, libraries in `crates/`. See [ARCHITECTURE.md](ARCHITECTURE.md) for the
full project tree and the layer rules.

## Where the name appears

Renaming the product means changing these, and nothing else:

- `crates/brand/src/lib.rs`: display name, machine name, GitHub repository
- `apps/chawpick-ide/`: the folder name and `name` in its `Cargo.toml`
- `Cargo.toml`: `repository`
- `README.md`, `AGENTS.md`, `ARCHITECTURE.md`

## License

Chawpick Ide — Copyright (C) 2026 Alttiplano

| What | License | File |
|---|---|---|
| The IDE: the app and every crate, unless its `Cargo.toml` says otherwise | GPL-3.0-or-later | [LICENSE-GPL](LICENSE-GPL) |
| Crates meant for others to reuse, marked `license = "MIT"` in their `Cargo.toml` (none yet) | MIT | [LICENSE-MIT](LICENSE-MIT) |

This program is free software: you can redistribute it and/or modify it under the terms of the
GNU General Public License as published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version. It is distributed in the hope that it will be
useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS
FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
