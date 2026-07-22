# Case study: dry run is a separate evidence tier

## Actual problem

The private operations kit had to support several serving shapes without turning an operator brief into an unsafe one-line launch. A resolved plan can still fail at model load, distributed membership, request handling, or teardown.

## Source-backed sequence

1. The v2.0 manual established the dry-run-first contract.
2. Runbooks were separated by serving shape and a test matrix was added.
3. Inventory and environment templates stayed examples; live values remain operator-owned.
4. Scripts were split into preflight, model-directory, smoke, benchmark, download, and link checks.
5. Systemd and RouterOS files remained templates requiring manual review.

## Failed hypotheses

- A valid shell command proves readiness: false.
- A model path in a template proves the artifact exists: false.
- A dry-run proves a live distributed launch: false.

## Bounded tests and acceptance gates

The source requires explicit intent, preflight evidence, model identity, readiness/request checks, and teardown evidence. Public validation is limited to links, JSON, and privacy.

## Result

The useful result is separation of evidence tiers. The public plan is a contract, not a deployment receipt.
