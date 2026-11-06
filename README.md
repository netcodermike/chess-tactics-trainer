# Chess Tactics Trainer

Practice a small curated set of coordinate-move checking exercises on a desktop chessboard.

[![Build and verify](https://github.com/netcodermike/chess-tactics-trainer/actions/workflows/verify.yml/badge.svg)](https://github.com/netcodermike/chess-tactics-trainer/actions/workflows/verify.yml)

**Language:** Java · **Platform:** Windows, macOS, Linux desktop · **App type:** Desktop tactics puzzle trainer

First-release learning implementation, with explicit scope below. This is one independently runnable app, not a placeholder in a combined repository.

## Features

- Three illustrated positions
- Coordinate answer entry
- Explanations and answer reveal
- Session solved counter

## Requirements

JDK 17+ and Swing for desktop use; self-tests run headlessly. No external packages.

## Quick start

```sh
git clone https://github.com/netcodermike/chess-tactics-trainer.git
cd chess-tactics-trainer
javac -d build src/App.java
java -cp build App
```

Commands run from the repository root. Lines marked for a particular operating system apply only there. Language tools are prerequisites, not installed by the app. Close desktop windows normally; terminal/server apps stop with Ctrl+C unless their usage notes say otherwise.

## Example workflow

Hover squares to read coordinates, enter the requested checking move, inspect feedback, reveal an answer, and cycle through all three puzzles.

## Architecture, configuration, and data

App.java contains fixed 8×8 board records, expected origin/destination coordinates, and explanations for queen/knight/rook checks. Swing draws Unicode pieces and accepts normalized coordinate strings. Each puzzle counts solved only once per session. Tests verify board shape and answer normalization. No engine or external chess service is used.

## Verification

Build with the quick-start command where needed, then run:

```sh
java -cp build App --self-test
```

Manual acceptance: Hover squares to read coordinates, enter the requested checking move, inspect feedback, reveal an answer, and cycle through all three puzzles. Also test malformed inputs and an unwritable output destination.

See [validation record](docs/VALIDATION.md) for observed checks and their limits. CI results verify only what the workflow runs; they do not establish native GUI correctness or production readiness.

## Limitations and next steps

A tiny introductory exercise set, not a legal-move engine, comprehensive tactics database, mate evaluator, or unique-best-move judge. Alternative legal checking moves are not accepted unless they match the authored answer. No drag movement, opponent AI, progress persistence, or rated difficulty. Unicode piece rendering depends on fonts.

## Troubleshooting

Use the exact platform/toolchain above. Preserve originals and use synthetic fixtures first. Errors are displayed in the UI or stderr. A headless machine can run the model tests but cannot verify native GUI/audio behavior. Output paths are chosen explicitly; keep backups of important data.

## Source map

- `src/App.java`

## Development and license

Read [contributing](CONTRIBUTING.md) before changing the app, and [security/privacy](SECURITY.md) before supplying private data. Use synthetic fixtures for tests. No telemetry, paid API key, or account is required by the app itself. Dependencies, when present, are stated in Requirements.

[MIT license](LICENSE), copyright 2026 netcodermike.
