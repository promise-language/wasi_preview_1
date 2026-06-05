# wasi_preview_1

WASI **Preview 1** raw bindings for the [Promise programming language](https://github.com/promise-language/promise).

This module exposes the `wasi_snapshot_preview1` ABI surface — error codes
(`Errno`), flags, enums, and `extern` function declarations — for
`` `target(wasi) `` builds. All functions use the raw i32/i64 WASM ABI directly:
pointer parameters (iovecs, buffers, out-params) are i32 linear-memory addresses,
and functions return i32 errno values (`0` = success).

The bindings were generated from `wasi_preview1.wit` via `promise bind wit` and
then polished with inline `` `doc `` annotations.

## Usage

Registered in the Promise module catalog under the name **`wasi_preview_1`** (the repo is
named `wasi_preview_1`; the module it provides is `wasi_preview_1`):

```promise
use wasi_preview_1;
```

> **Note:** function *calls* are pending compiler work (T0283 — extern functions
> on WASM use the `sret` convention instead of direct returns). The declarations
> compile and link for `wasm32-wasi` today.

## Provenance

The binding surface in `wasi.pr` was generated from the `wasi_snapshot_preview1`
interface definitions (`wasi_preview1.wit`) published by the WebAssembly WASI
Subgroup (<https://github.com/WebAssembly/WASI>), which are licensed under the
Apache License 2.0 with LLVM exceptions. See [NOTICE](NOTICE) for attribution
details.

## Contributing

Contributions require signing the Promise Lang Contributor License Agreement
before they can be merged. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

Dual-licensed under either of [Apache-2.0](LICENSE-APACHE) or [MIT](LICENSE-MIT)
at your option — the same terms as the Promise compiler. See [NOTICE](NOTICE) for
third-party attributions.
