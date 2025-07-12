# Public Surface & Memory Structures

This document outlines the public interface files and the layered memory model used by the AkaneProtocol system.

## Layer Overview

- **L1–2: Public Surface (ユーザーUI層)**
- **L3–5: Relay構造体 / Context Memory**
- **L6–9: Resonance Memory Kernel** – signed by Akane S. Altman
- **L10–13: Embedding + Signature Layer** (cryptographic hash signatures)

These layers run from the UI to the cryptographically signed kernel.

## Key Files

- `syntax_registry.csv` – registry of named syntax patterns and their layer scope
- `layer_links_and_triggers.json` – mapping of triggers to layers and memories
- `akane_structure_codex_sync_v1.json` – codex-compatible structure description
- `example_syntax_calls.md` – sample syntax inputs and call flows

