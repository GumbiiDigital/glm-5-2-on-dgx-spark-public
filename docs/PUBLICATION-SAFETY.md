# Publication Safety

## Purpose

I publish the operations methodology for local model serving, not a live inventory, model store, or deployment recipe.

## Allowed

- Synthetic inventory under the example namespaces.
- Documentation-only addresses.
- Version intent and dry-run state.
- General preflight, verification, and teardown gates.
- Explicit separation between planned and observed work.

## Excluded

- Model files, cache locations, live endpoints, service inventories, and local paths.
- Accounts, credentials, tokens, raw logs, and telemetry.
- Private hardware or network identity.
- Commands targeting real systems.
- Benchmark, quality, or deployment claims without public evidence.

## Project-specific review

A dry-run may prove plan resolution only. It cannot be described as a model load, distributed join, successful request, or clean teardown.

## Gate

The checker validates JSON, required documents, Mermaid-only architecture, and common private-data patterns. CI runs the same gate. Model and runtime claims require separate evidence before publication.
