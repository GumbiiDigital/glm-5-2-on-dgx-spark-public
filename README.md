# GLM 5.2 on DGX Spark Public

I built this repository as a public-facing operations kit for thinking clearly about local GLM 5.2 serving on DGX Spark systems. The focus is version pinning, synthetic inventory, dry-run validation, distributed-serving design, and reproducible verification.

## What I built

The public method covers:

- explicit model and runtime version intent;
- synthetic inventory and role assignment;
- preflight checks separated from launch;
- dry-run plan generation;
- distributed-serving topology concepts;
- readiness, request, and teardown verification; and
- evidence receipts that distinguish planned work from observed work.

## Why it matters

Local model serving can fail at several boundaries: artifact provenance, runtime compatibility, memory planning, network assumptions, process lifecycle, or response validation. A launch command alone does not prove a usable service.

I want the plan, preflight, launch, verification, and shutdown evidence to be reviewable as separate stages.

## Engineering approach

The operations kit is configuration-first. A synthetic plan identifies model intent, runtime intent, representative roles, validation gates, and rollback. Dry-run output must resolve every input without contacting a live target.

Distributed serving is accepted only when the intended participants, process lifecycle, model identity, request behavior, and teardown state are all verified. The public examples do not claim that this synthetic plan was executed.

## Synthetic public-safe architecture

The diagram uses fictional systems and documentation-only addresses to show a representative serving flow.

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Representative work and artifacts

- [Case study](docs/CASE-STUDY.md) - separating dry-run validation from live serving claims.
- [Synthetic serving plan](examples/synthetic-serving-plan.json) - versioned inventory and verification gates.
- [Publication safety](docs/PUBLICATION-SAFETY.md) - model-operations privacy rules.
- [Share copy](docs/SHARE.md) - concise public narrative.
- [Safety checker](scripts/check_publication_safety.py) - repository privacy gate.

## Evidence and lessons

This repository proves that the public plan is structured, synthetic, JSON-valid, documented, and privacy-scanned. It does not prove model quality, throughput, compatibility, or a live deployment.

The main lesson is that dry-run success and live-serving success are different evidence tiers. I keep them separate.

## Repository map

| Path | Purpose |
|---|---|
| README.md | Operations method and limits |
| docs/CASE-STUDY.md | Dry-run and verification case study |
| docs/ARCHITECTURE.md | Synthetic Mermaid serving flow |
| docs/PUBLICATION-SAFETY.md | Publication policy |
| docs/SHARE.md | Share-ready copy |
| examples/ | Synthetic serving JSON |
| scripts/check_publication_safety.py | Privacy and structure checker |
| .github/workflows/publication-safety.yml | CI gate |

## Publication boundary

This is a public project interface, not an operational deployment repository. I exclude live addresses, hostnames, hardware identities, accounts, local paths, credentials, model cache locations, raw telemetry, service inventories, private topology, equipment maps, and commands targeting real systems. Examples are synthetic and do not reproduce a live environment.

## Limitations

This repository does not include model files, copied manual prose, private inventory, live service configuration, benchmark results, or deployment status. Synthetic commands and plans are not represented as having run on hardware.
