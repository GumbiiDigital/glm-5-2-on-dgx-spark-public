# GLM 5.2 on DGX Spark

I built this operations kit to make local GLM 5.2 serving reviewable before it is run. The private source baseline is c57b65e. It contains the v2.0 manual, several runbook shapes, environment and inventory templates, RouterOS snippets, systemd templates, and validation scripts.

## What I built

1. A dry-run-first operations manual and runbook set.
2. Explicit model/runtime intent instead of moving latest references.
3. Inventory, environment, systemd, and RouterOS templates separated from live values.
4. Preflight, API smoke, benchmark, model-directory, download, and link-validation scripts.
5. A test matrix covering the documented serving shapes.
6. Evidence templates that distinguish planned, observed, and unknown results.

## Recorded results

| Observation | Source evidence | Status |
|---|---|---|
| Baseline c57b65e | private HEAD | Historical |
| v2.0 manual and five runbook shapes | source docs/runbooks | Historical inventory |
| Inventory and environment files are examples | README and `*.example` files | Safety rule |
| Preflight, smoke, benchmark, download, and model-directory checks are tracked | source scripts | Historical inventory |
| Test matrix was added in a later commit | source history | Historical process |

## Why it matters

Serving can fail at artifact provenance, runtime compatibility, memory planning, process lifecycle, or request validation. A launch command is not a usable-service receipt.

## Engineering approach

Plan, preflight, launch, request verification, and teardown are separate. Systemd and RouterOS files are templates for operator review, not automatic apply. Credentials and model paths belong outside the repository.

## Sanitized architecture boundary

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md).

## Repository map

- [docs/CASE-STUDY.md](docs/CASE-STUDY.md)
- [docs/SERVING-OPERATIONS-RECORD.md](docs/SERVING-OPERATIONS-RECORD.md)
- [docs/PUBLICATION-SAFETY.md](docs/PUBLICATION-SAFETY.md)
- [examples/synthetic-serving-plan.json](examples/synthetic-serving-plan.json)
- The private source contains runbooks for several serving shapes; this public branch records their evidence boundary rather than publishing live runbooks.

## Evidence rules and limits

These are historical source-backed observations. No model files, live inventory, credentials, cache paths, deployment status, or benchmark results are included. Dry-run validity does not prove live compatibility.
