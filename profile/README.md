<div align="center">

# Media Lane Protocol

**A transport for real-time interactive media over links that are slow, lossy, or both.**

[![Spec](https://img.shields.io/badge/spec-v1-blue)](https://github.com/medialaneprotocol/mlp)
[![License: Apache-2.0](https://img.shields.io/badge/spec-Apache--2.0-green)](https://github.com/medialaneprotocol/mlp/blob/main/LICENSE)
[![Impl: PolyForm NC](https://img.shields.io/badge/impl-PolyForm%20NC-orange)](https://github.com/medialaneprotocol/mlp-core/blob/main/LICENSE)

</div>

---

## What MLP is

A lane carries three kinds of traffic at once — **control**, **media**, and **feedback** — and keeps them apart. It moves content it does not interpret, paces it under a rate it measured, and always knows what each receiver may be stale in.

- A **sender** knows, for every receiver, exactly which parts of the surface that receiver may be missing, and repairs exactly those.
- A **receiver** either holds an object whole or refuses it, and says which base it does hold.
- **Nothing in the protocol interprets the content** — a codec plugs in without the protocol learning anything about it.

## Repositories

| Repository | Language | What it holds |
|---|---|---|
| [`mlp`](https://github.com/medialaneprotocol/mlp) | Markdown | The normative specification (v1, stable) |
| [`mlp-core`](https://github.com/medialaneprotocol/mlp-core) | Rust | Sans-IO reference implementation + `mlp-core` CLI |
| [`mlp-ts`](https://github.com/medialaneprotocol/mlp-ts) | TypeScript | Browser reference implementation + receiver machine |
| [`mlp-proto`](https://github.com/medialaneprotocol/mlp-proto) | Protobuf | Wire schema of the class bodies |
| [`mlp-conformance`](https://github.com/medialaneprotocol/mlp-conformance) | Shell | Conformance corpus + reproducibility gate |
| [`mlp-harness`](https://github.com/medialaneprotocol/mlp-harness) | Rust | Deterministic link model + invariants |
| [`mlp-demo`](https://github.com/medialaneprotocol/mlp-demo) | Rust | Demo: a session that heals a loss |

## Status

- **Protocol:** v1, stable. One accepted version — a peer speaking another is refused with a typed reason.
- **Implementation:** in development, moving tag `v0.1.0`.
- **Wire format:** frozen by the specification.

## Quick start

```bash
# Rust core
cargo build --release -p mlp-core
./target/release/mlp-core limits

# TypeScript (browser)
npm install && npm test
```

## License

- Specification & wire schemas: **Apache-2.0**
- Reference implementations: **PolyForm Noncommercial 1.0.0** (commercial use requires a separate license)

## Links

- 📖 [Specification](https://github.com/medialaneprotocol/mlp/blob/main/spec/README.md)
- 🛠️ [CLI docs](https://github.com/medialaneprotocol/mlp-core/blob/main/docs/cli.md)
- 🤝 [Contributing](https://github.com/medialaneprotocol/mlp/blob/main/CONTRIBUTING.md)
- 🔒 [Security policy](https://github.com/medialaneprotocol/mlp/blob/main/SECURITY.md)
