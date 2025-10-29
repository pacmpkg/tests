# Pacm Testing Suite

This directory contains the comprehensive testing suite for the `pacm` package manager. As part of the main `pacm` repository, these tests ensure the reliability and correctness of all core functionality.

## Overview

The `pacm` testing suite is organized as integration tests within the `tests/` directory of the Rust project. Each `.rs` file in this directory represents a separate test crate that validates specific components of the package manager.

## Test Structure

- `common/mod.rs` - Shared utilities and helpers for the test modules
- `cas_store.rs` - Tests for the content-addressable storage (CAS) functionality
- `fast_install.rs` - Tests for the fast installation algorithm
- `lockfile.rs` - Tests for lockfile serialization, deserialization, and synchronization with manifests
- `manifest.rs` - Tests for package manifest (package.json) reading and writing
- `resolver.rs` - Tests for semantic version range resolution and npm-style range parsing
- `manifest_updates.rs` - Tests for parsing package specifications and updating manifests

## Running Tests

To run the entire testing suite:

```bash
cargo test
```

To run specific test modules:

```bash
cargo test --test cas_store
cargo test --test fast_install
cargo test --test lockfile
cargo test --test manifest
cargo test --test resolver
cargo test --test manifest_updates
```

## Test Coverage

The testing suite covers:

- Lockfile binary format encoding/decoding
- Manifest JSON serialization
- NPM package range resolution
- Package specification parsing
- Integration between components

All tests use the `pacm` library as an external dependency, ensuring they validate the public API and integration points.

## Adding New Tests

When adding new functionality to `pacm`, corresponding tests should be added to the appropriate test file in this directory. For unit tests of internal modules, consider adding them directly to the source files with `#[cfg(test)]` blocks.