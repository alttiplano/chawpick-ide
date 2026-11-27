# Contributing to Chawpick IDE

Thanks for wanting to help. This guide is short on purpose: read all of it before opening your first PR.

## Quick links

- **Discord:** [discord.gg/Dx4YUqgrm9](https://discord.gg/Dx4YUqgrm9): questions, ideas and help
- **Issues:** [github.com/alttiplano/chawpick-ide/issues](https://github.com/alttiplano/chawpick-ide/issues/new): bugs and proposals
- **Architecture:** [ARCHITECTURE.md](ARCHITECTURE.md): how the code is organized
- **Code of Conduct:** [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)

## What do you want to do?

1. **Fix a bug or something small** → open a PR directly.
2. **Add a feature or change the interface** → open an issue or ask on Discord first, and wait for
   a go-ahead before writing code.
3. **A large refactor** → don't open a PR unless a maintainer asks for it.
4. **Ask a question** → Discord.
5. **Report a security issue** → email **security@alttiplano.com**. Never in a public issue.

Opening a PR doesn't guarantee it gets merged. Confirming the idea first gives you the best chance.

## What we accept most

- Bug fixes.
- Performance improvements, with before and after numbers.
- Fixes for a specific platform: Linux, Windows or macOS.
- Documentation and translations.
- Tests for code that doesn't have them yet.

## Getting started

You need Rust installed with [rustup](https://rustup.rs). The `rust-toolchain.toml` file picks the
exact version for you.

1. [Fork](https://github.com/alttiplano/chawpick-ide/fork) the repository.
2. Clone your fork and create a branch for your change from `dev`:

```sh
git clone https://github.com/YOUR-USERNAME/chawpick-ide.git
cd chawpick-ide
git remote add upstream https://github.com/alttiplano/chawpick-ide.git
git fetch upstream
git checkout -b my-change upstream/dev
```

### Run

**Linux**, the first time and after changing the name or the icon:

```sh
scripts/install-desktop.sh
```

Start the app (the first run takes a few minutes ⏱️):

```sh
cargo run
```

On Windows and macOS, `cargo run` is all you need.

## Before you open a PR

These three commands must pass:

```sh
cargo fmt --check
cargo clippy --all-targets -- -D warnings
cargo test
```

- **One topic per PR.** If you touch several things, split them: a small PR gets reviewed and merged
  sooner.
- **At most 2 open PRs at a time.** Finish one before starting another.
- **Open the PR against `dev`**, never against `main`.
- **Title:** `type: summary`, for example `fix: left panel loses its width`. Types: `feat`, `fix`,
  `perf`, `docs`, `refactor`, `test` and `chore`.
- **Short description:** what changes, why, and how you tested it.
- **Visual changes:** add before and after screenshots.

We merge with *squash*: your PR lands in `dev` as a single commit.

## Performance

Chawpick IDE has to feel fast. If your change can affect startup, typing, scrolling or memory,
measure before and after with `cargo run --release` and put the numbers in the PR.

- **Never block the window.** Slow work (network, disk) goes on a separate thread.
- **Every new dependency needs a reason.** Fewer dependencies mean faster builds and a lighter app.

## Project rules

The full rules are in [AGENTS.md](AGENTS.md) and [ARCHITECTURE.md](ARCHITECTURE.md). The most
important ones:

- **egui is only used in `crates/ui` and `apps/`.** The other crates don't draw.
- **Don't change the name, the icon or the version** (`crates/brand`, `assets/app-icon/`,
  `Cargo.toml`). The maintainer does that.

## AI tools

You can use AI to write code, but you are the author and you answer for every line:

- **Understand your code.** If you can't explain a change, don't send it.
- **Write your PR and your replies yourself.** We want to talk with you, not with a model. If you
  translate with AI, include your original text too.
- **No bots or autonomous agents** opening PRs, issues or comments.
- **No AI signatures** in commits or PRs. Remove lines like these before you submit:

```
Co-Authored-By: Claude <noreply@anthropic.com>
🤖 Generated with Claude Code
```

PRs that don't follow these rules will be closed.

## License

By contributing, you agree that your work is published under the license of the crate you touch:
[GPL-3.0-or-later](LICENSE-GPL) by default, or [MIT license](LICENSE) in crates whose `Cargo.toml` says
`license = "MIT"`.

---

<sub>Maintained by [Alttiplano](https://alttiplano.com).</sub>
